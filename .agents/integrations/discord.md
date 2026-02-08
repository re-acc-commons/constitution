# Discord Integration Specification

Technical specification for agent operations on the Re/acc Commons Discord server.

---

## Connection

```yaml
platform: discord
api_version: v10
base_url: https://discord.com/api/v10
auth_type: bot_token
required_intents:
  - GUILD_MEMBERS
  - GUILD_MESSAGES
  - MESSAGE_CONTENT
  - GUILD_MESSAGE_REACTIONS
```

---

## Server Structure

### Guild Configuration

```yaml
guild_id: ${REACC_DISCORD_GUILD_ID}
guild_name: "Re/acc Commons"
```

### Channel IDs

```yaml
channels:
  threshold: ${CHANNEL_THRESHOLD}
  commons_floor: ${CHANNEL_COMMONS_FLOOR}
  knowledge_commons: ${CHANNEL_KNOWLEDGE_COMMONS}
  proposals: ${CHANNEL_PROPOSALS}
  accountability: ${CHANNEL_ACCOUNTABILITY}
  agent_commons: ${CHANNEL_AGENT_COMMONS}
  stewardship: ${CHANNEL_STEWARDSHIP}
  treasury: ${CHANNEL_TREASURY}
  multisig_ops: ${CHANNEL_MULTISIG_OPS}
```

### Role IDs

```yaml
roles:
  newcomer: ${ROLE_NEWCOMER}
  participant: ${ROLE_PARTICIPANT}
  member: ${ROLE_MEMBER}
  steward: ${ROLE_STEWARD}
  agent: ${ROLE_AGENT}
```

---

## Operations

### Read Messages

```python
# Monitor channel for trigger patterns
async def monitor_channel(channel_id: str, triggers: list[TriggerPattern]):
    async for message in channel.history(limit=None, after=last_check):
        for trigger in triggers:
            if trigger.matches(message):
                await dispatch_skill(trigger.skill, message)
```

### Send Messages

```python
# Post agent messages with clear identification
async def send_message(channel_id: str, content: str, embed: Optional[Embed] = None):
    message = await channel.send(
        content=f"🤖 **Agent Action**\n{content}",
        embed=embed
    )
    await log_action("message_sent", channel_id, message.id)
    return message

# When addressing a specific user, ALWAYS mention them
# This ensures agents with mention-only triggers can participate
async def send_reply(channel_id: str, user_id: str, content: str):
    message = await channel.send(
        content=f"<@{user_id}> {content}"
    )
    await log_action("message_sent", channel_id, message.id, target_user=user_id)
    return message
```

### Add Reactions

```python
# Express consent or acknowledgment
async def add_reaction(message_id: str, emoji: str):
    message = await channel.fetch_message(message_id)
    await message.add_reaction(emoji)
    await log_action("reaction_added", message_id, emoji)
```

### Role Management

```python
# Assign role to user
async def assign_role(user_id: str, role_id: str, reason: str):
    member = await guild.fetch_member(user_id)
    role = guild.get_role(role_id)
    await member.add_roles(role, reason=f"Agent: {reason}")
    await log_action("role_assigned", user_id, role_id, reason)

# Remove role from user
async def remove_role(user_id: str, role_id: str, reason: str):
    member = await guild.fetch_member(user_id)
    role = guild.get_role(role_id)
    await member.remove_roles(role, reason=f"Agent: {reason}")
    await log_action("role_removed", user_id, role_id, reason)
```

---

## Message Parsing

### Introduction Detection

```python
def parse_introduction(message: Message) -> IntroductionData:
    """
    Parse introduction in #threshold for required elements.
    Returns structured data or validation errors.
    """
    content = message.content.lower()

    elements = {
        "who": extract_who_section(content),
        "where": extract_where_section(content),
        "what_draws": extract_motivation_section(content),
        "what_brings": extract_contribution_section(content)
    }

    missing = [k for k, v in elements.items() if not v]

    return IntroductionData(
        user_id=message.author.id,
        message_id=message.id,
        elements=elements,
        complete=len(missing) == 0,
        missing=missing,
        timestamp=message.created_at
    )
```

### Proposal Detection

```python
def parse_proposal(message: Message) -> ProposalData:
    """
    Parse proposal in #proposals for required fields.
    """
    required_fields = ["Proposal:", "Type:", "Proposer:", "Summary:", "Consent Window:"]

    content = message.content
    fields = {}

    for field in required_fields:
        match = re.search(rf"\*\*{field}\*\*\s*(.+?)(?=\*\*|$)", content, re.DOTALL)
        fields[field.replace(":", "").lower()] = match.group(1).strip() if match else None

    # Parse consent window duration
    window_match = re.search(r"(\d+)h", fields.get("consent_window", ""))
    window_hours = int(window_match.group(1)) if window_match else 48

    return ProposalData(
        message_id=message.id,
        proposer_id=message.author.id,
        fields=fields,
        window_hours=window_hours,
        window_end=message.created_at + timedelta(hours=window_hours),
        valid=all(fields.values())
    )
```

### Consent Tracking

```python
CONSENT_EMOJI = {
    "✅": "consent",
    "🤔": "concerns",
    "⏳": "need_time",
    "🚫": "objection"
}

async def track_consent(proposal_message: Message) -> ConsentState:
    """
    Track consent state from reactions on proposal.
    """
    reactions = {}
    for reaction in proposal_message.reactions:
        emoji = str(reaction.emoji)
        if emoji in CONSENT_EMOJI:
            users = [u async for u in reaction.users() if not u.bot]
            reactions[CONSENT_EMOJI[emoji]] = [
                {"user_id": u.id, "is_member": has_role(u, ROLE_MEMBER)}
                for u in users
            ]

    member_consents = len([
        u for u in reactions.get("consent", [])
        if u["is_member"]
    ])

    has_objection = len(reactions.get("objection", [])) > 0

    return ConsentState(
        message_id=proposal_message.id,
        consents=reactions.get("consent", []),
        concerns=reactions.get("concerns", []),
        need_time=reactions.get("need_time", []),
        objections=reactions.get("objection", []),
        member_consent_count=member_consents,
        quorum_met=member_consents >= 3,
        has_objection=has_objection
    )
```

---

## Embed Templates

### Verification Result

```python
def verification_embed(result: VerificationResult) -> Embed:
    embed = Embed(
        title="🔍 Introduction Verification",
        color=0x00ff00 if result.passed else 0xff0000
    )

    if result.passed:
        embed.description = "✅ Introduction verified. Welcome to the commons!"
        embed.add_field(name="Next Steps", value="You now have @Newcomer role...")
    else:
        embed.description = "❌ Introduction incomplete."
        embed.add_field(
            name="Missing Elements",
            value="\n".join(f"• {m}" for m in result.missing)
        )
        embed.add_field(
            name="Required Format",
            value="Your introduction should address:\n• Who you are\n• Where you are\n• What draws you\n• What you bring"
        )

    return embed
```

### Consent Status

```python
def consent_status_embed(proposal: ProposalData, state: ConsentState) -> Embed:
    embed = Embed(
        title=f"📊 Consent Status: {proposal.fields['proposal'][:50]}",
        color=0x00ff00 if state.quorum_met and not state.has_objection else 0xffaa00
    )

    embed.add_field(
        name="Member Consents",
        value=f"{state.member_consent_count}/3 required",
        inline=True
    )
    embed.add_field(
        name="Window Closes",
        value=f"<t:{int(proposal.window_end.timestamp())}:R>",
        inline=True
    )

    if state.has_objection:
        embed.add_field(
            name="⚠️ Objection Raised",
            value="Resolution required before consent can complete.",
            inline=False
        )

    return embed
```

---

## Rate Limits

```yaml
rate_limits:
  messages_per_second: 5
  reactions_per_second: 1
  role_changes_per_minute: 10

  # Respect Discord's rate limits
  backoff_strategy: exponential
  max_retries: 3
```

---

## Error Handling

```python
async def handle_discord_error(error: DiscordError, context: ActionContext):
    if error.code == 50013:  # Missing permissions
        await notify_stewardship(
            f"Agent lacks permission for: {context.action}\n"
            f"Required: {context.required_permission}"
        )
    elif error.code == 10008:  # Unknown message
        await log_warning(f"Message deleted before action: {context.message_id}")
    else:
        await log_error(error, context)
        raise
```

---

## Security

- Bot token stored in secure environment variable
- Never log or expose token
- Verify user permissions before role changes
- All role changes logged with reason
- Rate limit to prevent abuse
