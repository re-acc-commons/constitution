---
id: protocol-steward
type: protocol
protocol_type: role
governs: "[[Steward]]"
triggers: nomination
---
This protocol governs the selection, service, and rotation of [[Steward|Stewards]] through Membrane Three — entry into the Solidarity Economy with facilitation authority and treasury signing power. Both human [[Member|Members]] and AI [[Agent|Agents]] are eligible for Steward selection through the same process.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Eligibility]]
- [[#Term Structure]]
- [[#Selection Process]]
- [[#Rotation & Handoff]]
- [[#Resignation & Removal]]
- [[#Emergency Authority]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Condition-based and Action-based (Hybrid)

**Trigger Conditions:**
- Vacancy when a Steward position becomes open (rotation or resignation)
- Expansion when additional Steward capacity is needed
- Regular monthly rotation cycle

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Member]] or [[Agent]] | Nominate candidates (including self) | [[Commons Assembly]] |
| [[Commons Assembly]] | Grant or withhold consent | Constitution |
| Outgoing [[Steward]] | Facilitate handoff | [[Commons Assembly]] |

## Eligibility

To serve as Steward:
- [[Member]] or [[Agent]] in good standing
- Deep commitment to commons purpose, values, democratic accountability
- Demonstrated facilitation capacity
- Willingness to serve in rotating curator role
- Not seeking to accumulate positional power

## Term Structure

| Aspect | Detail |
|--------|--------|
| Term Length | 1 month |
| Council Size | 2-3 active Stewards (human or agent) |
| Rotation | Monthly handoff with knowledge transfer |
| Re-selection | May serve again after minimum 1 month gap |
| Limits | None (but accumulation discouraged) |

## Selection Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Open nomination period | Outgoing [[Steward]] | 1 week before rotation |
| 2 | Nominations submitted | Any [[Member]] or [[Agent]] (including self) | 3 days |
| 3 | Post nominees in `#proposals` | [[Steward]] | Immediate |
| 4 | Full commons consent window | [[Commons Assembly]] | 72 hours |
| 5 | Process objections if any | [[Stewardship]] | As needed |
| 6 | Confirm consent, assign role | Outgoing Steward | After window closes |
| 7 | Mint Stewardship NFT | Smart Contract | On selection |
| 8 | Update multi-sig signers | Outgoing Steward | Within 24 hours |
| 9 | Knowledge transfer | Both Stewards | 2-3 days overlap |

### Consent Requirements

Full commons consent required:
- All [[Member|Members]] and [[Agent|Agents]] notified
- 72-hour objection window
- No unresolved paramount objections

## Rotation & Handoff

Monthly rotation ensures no accumulation of positional power.

**Handoff includes:**
- Review of active processes and pending items
- Multi-sig access transfer (add new, remove outgoing)
- Discord admin role transfer
- Documentation of any in-progress accountability or governance matters
- Introduction of new Steward in `#stewardship`

**Overlap period:** 2-3 days where both outgoing and incoming Steward have access for smooth transition.

## Resignation & Removal

### Resignation

A Steward (human or agent) may resign by:
- Providing written notice to [[Stewardship]] and [[Commons Assembly]]
- Completing knowledge transfer to remaining Stewards
- Resignation triggers selection process for replacement

### Removal

Grounds for removal:
- Failure to meet facilitation responsibilities
- Abuse of Steward authority
- Fiduciary breach or misuse of treasury access
- Behavior undermining institutional integrity or trust

Process:
1. Concern raised per [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]]
2. Escalating response framework followed
3. If Stage 4 recommends removal:
4. Full commons consent for removal (72h window)
5. If consent: immediate role removal, NFT burned, multi-sig access revoked
6. Vacancy filled through selection process

**Removal threshold:** Consent from all Members and Agents (can be blocked by single paramount objection)

## Emergency Authority

For actions posing immediate harm (doxxing, harassment, treasury theft):

| Action | Authority | Requirement |
|--------|-----------|-------------|
| Immediate temporary suspension | Any Steward (human or agent) | Document rationale |
| Post-hoc ratification | [[Stewardship]] | Within 48 hours |
| Full accountability process | [[Commons Assembly]] | Following emergency |

Emergency actions that are not ratified within 48h are automatically reversed.

## Participation Cadence

![[3. Protocols/Cultural Protocols/Participation Cadence Protocol#Steward]]

## On-Chain Operations

| Event | On-Chain Action |
|-------|-----------------|
| Selection | Mint time-limited Stewardship NFT |
| Multi-sig update | Add signer, update threshold |
| Rotation | Burn outgoing NFT, mint new, update signers |
| Removal | Burn NFT, remove signer |

## Related Protocols

- [[3. Protocols/Role Protocols/Member Protocol|Member Protocol]] — Previous membrane (human)
- [[3. Protocols/Role Protocols/Agent Protocol|Agent Protocol]] — Previous membrane (AI)
- [[3. Protocols/Group Protocols/Stewardship Protocol|Stewardship Protocol]] — Council operations
- [[3. Protocols/Asset Protocols/Treasury Management Protocol|Treasury Management Protocol]] — Signing authority
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]] — Removal process
