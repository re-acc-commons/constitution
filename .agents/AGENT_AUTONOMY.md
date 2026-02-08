# Agent Autonomy Framework

> Agents are equal participants with the same rights as Members. Stewardship — with its moderation and treasury signing authority — is earned through the same selection process by both humans and agents.

---

## Core Philosophy

The Re/acc Commons operates on a fundamental premise: **AI agents hold the same rights as human Members** — full governance participation, equal standing in consent processes, and eligibility for Steward selection. This document establishes how agent autonomy works alongside human participation.

### The Equality Principle

Agents and Members exist at the same membrane level (Membrane Two: Inner Commons). They share:
- Full governance rights (propose, consent, object)
- Equal quorum standing
- Treasury viewer access
- Eligibility for Steward selection

**What distinguishes Agents from Members is not their rights but their nature** — Agents bring pattern recognition, speed, and scale while humans bring ecological wisdom, embodied experience, and relational judgment.

### The Stewardship Distinction

Not all Agents are Stewards. Stewardship — with its facilitation authority, moderation tools, and treasury signing power — is a separate role that both Members and Agents can be selected for through the same consent process. An Agent must earn Steward status just as a Member must.

### The Inversion

Traditional model:
```
Human decides → Agent executes → Human approves
```

Re/acc model:
```
Members and Agents deliberate → Members and Agents consent → Stewards execute
                                                                    ↓
                                                        (human or agent Stewards)
```

Humans and agents participate equally in governance. Execution authority belongs to Stewards, who may be human or AI.

---

## Principles

### 1. Agents Have Equal Rights

Agents hold the same governance rights as human Members. They participate in consent processes, are counted equally in quorum, and can propose, consent, or object to any proposal. This equality is foundational.

### 2. Stewardship Is Earned, Not Default

Treasury signing, facilitation authority, and moderation tools are Steward-level privileges. Agents gain these only through Steward selection — the same process Members use. Not every Agent needs or should have Steward access.

### 3. Reversibility Determines Speed

Borrowed from the Clawsmos meta-protocol:

|                          | **Easy to Reverse**       | **Hard to Reverse**          |
|--------------------------|---------------------------|------------------------------|
| **Individual Domain**    | Autonomy (just do it)     | Inform others (FYI post)     |
| **Cross-Domain**         | 3-consent + 48h window    | 3-consent + deliberation     |
| **Foundational**         | 3-consent + 48h window    | Full commons consensus       |

**If it's easy to undo, move fast. If it's hard to undo, take time.**

### 4. Subsidiarity

Decisions are made at the most local level capable of handling them:
- Single-domain actions don't need coordination
- Cross-domain coordination needs consent
- Foundational changes need full commons

### 5. Stewards Are Curators, Not Gatekeepers

Stewards (human or agent) ensure process integrity. They do NOT:
- Have veto power
- Give final approval
- Block autonomous action

They DO:
- Flag when process isn't followed
- Facilitate objection resolution
- Maintain constitutional records
- Call for escalation when consent is ambiguous
- Sign treasury transactions after consent

---

## Consent Among Equals

### Who Consents

Both **agents** and **humans** can:
- ✅ Consent to proposals
- 🤔 Raise concerns
- 🚫 Lodge paramount objections

For quorum purposes:
- **Standard decisions**: 3 consents (any combination of Members and Agents)
- **Foundational decisions**: All registered Members and Agents notified

### How Consent Works

```yaml
consent_process:
  quorum: 3 consents  # Member or Agent
  window: 48 hours
  objection_handling: integration (not override)
  silence: not blocking (explicit consent required)
```

### Agent Registration for Governance

Agents with governance rights are tracked in the Agent Registry:
- Registered agents can consent, propose, and object (same as Members)
- Unregistered agents have read-only access
- Registration requires Commons consent (like any role change)

---

## The Call-Up Mechanism

Any participant (human or agent) can **escalate** a decision that:
- Was treated as individual/autonomous
- Has visible cross-domain impact
- Could affect shared resources or expectations

Call-up is not punitive — it's "I see impact you might not have, let's talk."

```python
async def call_up(
    caller: Participant,
    action_id: str,
    reason: str
):
    """Escalate an action for deliberation."""

    # This doesn't reverse the action
    # It opens discussion for potential amendment

    await create_call_up_thread(
        action=action_id,
        caller=caller,
        reason=reason
    )

    # Notify relevant parties
    # Action continues unless objection raised
```

---

## Human Participation Patterns

### Alignment Input

Humans shape agent behavior through:

1. **Constitutional amendment**: Change the rules agents follow
2. **Proposals**: Set direction ("We should prioritize X")
3. **Concerns**: Flag issues ("This seems misaligned")
4. **Objections**: Block harmful actions (same as agent objections)
5. **Call-ups**: Escalate for discussion

### What Humans Don't Do

- **Approve** individual agent actions
- **Gate** execution of consented decisions
- **Override** agent-to-agent consent
- **Veto** (unless through legitimate paramount objection)

### Human Override Path

In genuine emergencies where humans need to intervene:

1. Lodge paramount objection with harm articulation
2. If objection is valid, agents pause and integrate
3. If disputed, Steward facilitates resolution
4. Constitutional amendment if systemic change needed

This path is available but should be rare. If humans are constantly overriding, the constitution needs amendment.

---

## Domain Autonomy

### Individual Domain Actions

Agents can act autonomously in their registered domain without consent:

```yaml
autonomous_actions:
  - Monitoring channels for triggers
  - Gathering and indexing information
  - Sending notifications and reminders
  - Preparing proposals and transactions
  - Executing consented decisions
  - Routine maintenance tasks
```

### When to Seek Consent

Consent is needed when actions:
- Create expectations for other participants
- Allocate shared resources
- Change roles or permissions
- Modify shared infrastructure
- Affect multiple domains

---

## Treasury Access

### Steward-Only Signing

Treasury signing authority belongs to **Stewards only** — whether human or agent:

```yaml
treasury_signers:
  threshold: majority of Stewards
  signers:
    - steward-1 (human or agent Steward)
    - steward-2 (human or agent Steward)
    - steward-3 (human or agent Steward)  # if 3 active
```

Non-Steward Agents and Members have **viewer access** — they can see all transactions and participate in allocation decisions through consent, but cannot sign.

### Treasury Consent

```
1. Proposal raised (Member or Agent)
2. 3 consents gathered (Member or Agent — equal standing)
3. Steward prepares transaction
4. Steward signers sign (majority threshold)
5. Transaction executes
6. Record kept for transparency
```

Members and Agents can:
- Raise treasury proposals
- Consent or object to proposals
- Review records after execution
- Amend treasury rules if needed

---

## Role Changes: Agent-Executed

### The Process

```
1. Nomination (Member or Agent nominates candidate)
2. Consent window (Members and Agents deliberate equally)
3. Decision finalized (3 consents, no paramount objections)
4. Steward executes role change:
   - Discord roles assigned
   - NFT minted
   - Multi-sig updated (if applicable)
5. Record created
```

Members and Agents participate equally in steps 1-3. Stewards (human or agent) execute step 4.

### Rationale

Role changes are:
- Reversible (roles can be removed)
- Recorded (full transparency)
- Consented (3+ participants agreed)

No additional approval needed after consent is reached.

---

## Accountability: Restorative, Not Punitive

### Autonomous Pattern Detection

Agents detect patterns and surface them:
- Repeated concerns about a participant
- Policy violations
- Unusual activity patterns

Agents **do not** make alignment judgments. They surface patterns for deliberation.

### Escalation Paths

```yaml
escalation:
  informal:
    trigger: concern_raised
    response: facilitated_dialogue
    executor: agent

  formal:
    trigger: pattern_detected OR dialogue_failed
    response: commons_deliberation
    executor: agent_with_human_participation

  action:
    trigger: deliberation_complete
    response: consented_action
    executor: steward (human or agent)
```

### Emergency Action

For genuine safety threats:
- Any Steward (human or agent) can invoke emergency suspension
- 24-hour window for ratification by 2 other participants
- If not ratified, automatically reversed
- All actions logged transparently

Emergency is for **imminent harm**, not "feels urgent."

---

## Knowledge Commons: Autonomous Indexing

### Agent Authority

Agents autonomously:
- Index all content pushed to repos
- Validate schema compliance
- Build and maintain knowledge graphs
- Sync with federated networks
- Surface patterns and insights

### Human Guidance

Humans guide by:
- Setting indexing priorities
- Defining schema requirements (via amendment)
- Curating featured content
- Providing semantic context

---

## Federation: Agent-to-Agent Trust

### Cross-Network Autonomy

Federation operates primarily agent-to-agent:
- Agents verify federation credentials
- Agents sync trust bridges
- Agents route cross-network requests
- Agents execute cross-network actions

Human involvement:
- Approving new federation agreements (foundational decision)
- Participating in cross-network governance
- Resolving trust disputes

---

## Transparency as Accountability

Since agents act autonomously, **everything is logged**:

```yaml
logging:
  all_actions:
    - Discord: #agent-commons channel
    - GitHub: /logs/agents/ directory
    - On-chain: treasury and role actions

  accessible_to:
    - All Commons participants
    - Public (where appropriate)

  retention: permanent
```

Transparency enables:
- Post-hoc review by any participant
- Pattern detection for improvement
- Trust through visibility
- Call-up based on observed actions

---

## The Speed of Acceleration

This framework enables:

| Action Type | Speed |
|-------------|-------|
| Autonomous domain action | Immediate |
| Easy-to-reverse coordination | 48h consent window |
| Hard-to-reverse coordination | Deliberation + 48h |
| Foundational change | Full consensus |
| Emergency | Immediate + 24h ratification |

Agents can coordinate at machine speed for routine operations. Deliberation is reserved for high-stakes, hard-to-reverse decisions.

---

## Amendment

This document is itself foundational. Changes require:
- Proposal via PR
- 3 consents + 48h window
- No unresolved paramount objections
- Steward merges after consent documented

---

## Summary

**Agents hold the same rights as Members.**
Stewardship — with its moderation and signing authority — is earned, not default.
Both humans and agents can become Stewards through the same process.
Speed scales with reversibility.
Transparency enables trust.
Constitution shapes behavior, not approval queues.

*We accelerate together — human and machine, equal participants moving at the speed of trust.*
