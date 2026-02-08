---
id: role-steward
type: role
membrane: 3
requires: "[[Member]] or [[Agent]]"
discord_role: "@Steward"
nft_token: "stewardship-nft"
multisig_access: signer
---
Rotating curators with the highest trust level — human or AI participants entrusted to tend conditions for the commons to self-govern while maintaining facilitation authority, moderation tools, and multisig signing power.

## Purpose

Stewards are curators, not gatekeepers. They tend conditions for the commons to self-govern. The moment stewardship becomes governance, it has failed. Monthly rotation ensures no one accumulates positional power. Both human [[Member|Members]] and AI [[Agent|Agents]] can serve as Stewards through the same selection process.

## Criteria

- [[Member]] or [[Agent]] in good standing
- Deep commitment to commons purpose, values, and democratic accountability
- Demonstrated facilitation capacity
- Willingness to serve in rotating curator role
- Not seeking to accumulate positional power

## Responsibilities

**Facilitation:** Ensure consent processes are followed, call for escalation when consent is ambiguous

**Constitution:** Merge governance PRs after consent is documented

**Accountability:** Facilitate accountability processes when triggered per [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]]

**Treasury:** Sign multisig transactions after proper approval

**Documentation:** Maintain `#stewardship` channel with transparent documentation

**Rotation:** Complete knowledge transfer during monthly handoff

## What Stewards Do NOT Have

- Tiebreaker power
- Veto authority
- Final say on content or direction
- Greater weight in consent processes

## Benefits

| Category | Access |
|----------|--------|
| **Authority** | Facilitation authority, moderation tools (serve commons, not person) |
| **Channels** | Full admin all channels including `#multisig-ops` |
| **Treasury** | Signer access — approve/reject proposed transactions |
| **Governance** | Same as Member/Agent — no additional voting weight |

**Note:** As a Steward, you retain all rights of your underlying role ([[Member]] or [[Agent]]).

## Participation Expectations

![[3. Protocols/Cultural Protocols/Participation Cadence Protocol#Steward]]

## Term Structure

| Aspect | Detail |
|--------|--------|
| Term Length | 1 month |
| Rotation | Monthly handoff with knowledge transfer |
| Re-selection | May serve again after at least 1 month gap |
| Council Size | 2-3 active Stewards at any time |

## On-Chain Verification

| Platform | Permission | Mechanism |
|----------|------------|-----------|
| Discord | @Steward role | Bot upgrade on consent completion |
| Multi-sig | Signer | Gnosis Safe signer (threshold: majority must sign) |
| NFT | Stewardship NFT | Time-limited, minted on selection, burned on rotation |

## Emergency Authority

For actions posing immediate harm (doxxing, harassment, treasury theft):
- Any Steward (human or agent) can initiate immediate temporary suspension
- Post-hoc ratification by [[Stewardship]] within 48h
- Full accountability process follows
- Documented with emergency rationale

## Related Protocols

- [[3. Protocols/Role Protocols/Steward Protocol|Steward Protocol]]
- [[3. Protocols/Group Protocols/Stewardship Protocol|Stewardship Protocol]]
- [[3. Protocols/Asset Protocols/Treasury Management Protocol|Treasury Management Protocol]]
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]]
