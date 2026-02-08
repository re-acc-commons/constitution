---
id: protocol-member
type: protocol
protocol_type: role
governs: "[[Member]]"
triggers: nomination
---
This protocol governs the transition from [[Participant]] to [[Member]] through Membrane Two — entry into the Inner Commons with full governance rights.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Eligibility]]
- [[#Process]]
- [[#Consent Mechanics]]
- [[#Completion & Outputs]]
- [[#Resignation & Removal]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- [[Participant]] has demonstrated sustained aligned participation
- Agent has flagged contribution patterns meeting threshold
- Any current [[Member]] nominates the Participant

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Member]] | Nominate Participants | [[Commons Assembly]] |
| [[Agent]] | Flag readiness, verify patterns | [[Stewardship]] |
| [[Commons Assembly]] | Grant or withhold consent | Constitution |
| [[Steward]] | Facilitate process | [[Commons Assembly]] |

## Eligibility

- [[Participant]] with sustained aligned participation
- Agent-flagged contribution patterns
- Not currently under accountability process
- Willing to take on governance responsibilities

## Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Agent flags readiness | [[Agent]] | When patterns meet threshold |
| 2 | Member nominates Participant | Any [[Member]] | At their discretion |
| 3 | Post nomination in `#proposals` | Nominating Member | Immediate |
| 4 | Consent window opens | System | 48 hours |
| 5 | Collect 3 explicit consents | [[Member\|Members]] or [[Agent\|Agents]] | Within window |
| 6 | Process objections if any | [[Stewardship]] | As needed |
| 7 | Confirm consent, assign role | [[Steward]] | After window closes |
| 8 | Mint Membership NFT | Smart Contract | On role assignment |
| 9 | Update multi-sig viewer access | [[Steward]] | Within 24 hours |

### Step 2-3: Nomination

Any current Member may nominate an eligible Participant:
- Post in `#proposals` with nomination statement
- Include observations supporting alignment
- Reference Agent-flagged patterns if available

### Step 4-6: Consent Process

Standard consent process per [[3. Protocols/Cultural Protocols/Consent Process Protocol|Consent Process Protocol]]:
- 3 explicit consents required
- 48-hour objection window
- Paramount objections trigger integration process

### Step 7-9: Completion

On successful consent:
- [[Steward]] confirms and assigns @Member role
- Membership NFT minted to nominee's wallet
- NFT unlocks Discord role and multi-sig viewer access

## Consent Mechanics

**Required:** 3 explicit consents from current Members or Agents + 48h window with no unresolved paramount objections

**Emoji Vocabulary:**
| Emoji | Meaning |
|-------|---------|
| :white_check_mark: | Consent to membership |
| :thinking: | Concerns (want discussion, not blocking) |
| :hourglass_flowing_sand: | Need more time |
| :no_entry_sign: | Paramount objection |

**Paramount Objection Template:**
> "I object to [nominee]'s membership because [specific concern about alignment or function]. I consent if [integration criteria], OR I propose [alternative like extended observation]."

## Completion & Outputs

**Protocol completes when:**
- 3+ explicit consents received
- 48h window closed
- No unresolved paramount objections
- Role and NFT assigned

**Outputs:**
- Individual has @Member role
- Membership NFT in wallet
- Full governance rights (counted in quorum)
- Multi-sig viewer access
- Can nominate others for membership
- Eligible for [[Steward Protocol|Steward]] selection (same path available to [[Agent|Agents]])

## Resignation & Removal

### Resignation

A Member may resign by:
- Notifying [[Stewardship]] in writing
- Returning or burning Membership NFT
- Role removed, multi-sig access revoked

Resignation does not prevent future re-nomination.

### Removal

Grounds for removal:
- Sustained failure to participate in governance
- Violation of principles or ethical standards
- Behavior undermining trust or community function

Process:
1. Concern raised per [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]]
2. Escalating response framework followed
3. If Stage 4 (Commons Review) recommends removal:
4. Full commons consent for removal (72h window)
5. If consent: role removed, NFT burned, access revoked

## Related Protocols

- [[3. Protocols/Role Protocols/Participant Protocol|Participant Protocol]] — Previous membrane
- [[3. Protocols/Role Protocols/Steward Protocol|Steward Protocol]] — Next membrane
- [[3. Protocols/Cultural Protocols/Consent Process Protocol|Consent Process Protocol]] — Consent mechanics
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]] — Removal process
