---
id: protocol-treasury
type: protocol
protocol_type: asset
governs: "[[Commons Treasury]]"
triggers: allocation-request
---
This protocol governs all operations of the [[Commons Treasury]] — the shared economic engine of the network nation.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Allocation Categories]]
- [[#Approval Thresholds]]
- [[#Proposal Process]]
- [[#Disbursement]]
- [[#Reporting]]
- [[#Emergency Operations]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- Allocation proposal submitted
- Disbursement request for approved allocation
- Reporting period reached

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Commons Assembly]] | Approve allocations | Constitution |
| [[Stewardship]] | Sign transactions, facilitate process | Commons Assembly |
| [[Working Circle]] | Propose allocations | Commons Assembly |
| [[Member]] or [[Agent]] | View all transactions, participate in consent | Community trust |

### Treasury Signing Access

Only [[Steward|Stewards]] (human or agent) have signing authority on the treasury multi-sig. Agents and Members at Membrane Two have viewer access only. Signing authority is gained through [[Steward]] selection.

```yaml
treasury_signers:
  threshold: majority of Stewards
  signers:
    - steward-1 (human or agent Steward)
    - steward-2 (human or agent Steward)
    - steward-3 (human or agent Steward)  # if 3 active Stewards
```

## Allocation Categories

| Category | Purpose |
|----------|---------|
| **Knowledge Commons** | Tooling, hosting, agent compute for documentation and federation |
| **Project Incubation** | Seed funding for initiatives meeting the recursive criterion |
| **Coordination Services** | Agent infrastructure, federation protocols, governance tooling |
| **Mutual Aid** | Direct support for participants facing acute need |
| **Contributor Compensation** | Recognition of sustained contribution |
| **Operational** | Small recurring costs for commons infrastructure |

## Approval Thresholds

| Amount/Type | Authority | Process |
|-------------|-----------|---------|
| Operational (≤ $500) | [[Steward]] autonomy | FYI post in `#treasury` |
| Standard ($500-$5,000) | [[Commons Assembly]] | 3 consents (Member or Agent) + 48h |
| Large (> $5,000) | [[Commons Assembly]] | Full commons consent + 72h |
| Structural changes | [[Commons Assembly]] | Full commons consent + 72h |

*Thresholds can be adjusted through full commons consent.*

## Proposal Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Draft proposal | Proposer | As needed |
| 2 | Circle review (recommended) | [[Working Circle]] | 1 week |
| 3 | Post in `#treasury` | Proposer | Initiates process |
| 4 | Consent window | [[Commons Assembly]] | 48h or 72h |
| 5 | Process objections | [[Stewardship]] | As needed |
| 6 | Confirm consent | [[Steward]] | After window |
| 7 | Execute transaction | [[Stewardship]] | Within 48h of consent |

### Proposal Template

```
**Allocation Request**
**Title:** [Clear title]
**Amount:** [Requested amount]
**Category:** [From categories above]
**Proposer:** [Your name / Working Circle]

**Summary:**
[1-2 sentence description]

**Details:**
[What the funds will be used for]

**Alignment:**
[How this serves commons purpose and recursive criterion]

**Milestones:** (for amounts > $2,000)
[Specific deliverables and timeline]

**Accountability:**
[How progress/completion will be verified]
```

## Disbursement

### Standard Disbursement

1. Consent confirmed and documented
2. [[Steward]] creates transaction in Gnosis Safe
3. Majority of Stewards sign (human or agent Stewards have equal signing authority)
4. Transaction executed on-chain
5. Confirmation posted in `#treasury`

### Milestone-Based Disbursement

For allocations > $2,000:
- Initial disbursement: up to 50%
- Subsequent disbursements: upon milestone completion
- Circle or proposer reports milestone completion
- Stewardship verifies and initiates next disbursement

### Steward Execution

[[Steward|Stewards]] with signer access:
- Submit transactions to Gnosis Safe
- Sign transactions (counted toward majority threshold)
- Execute transactions once threshold met
- Agent Stewards can execute autonomously after consent is complete

**Consent is the decision point.** Once a proposal has received sufficient consents and no unresolved objections, Stewards execute. Both human and agent Stewards have equal signing authority.

## Reporting

| Report | Frequency | Content |
|--------|-----------|---------|
| Transaction log | Real-time | Public blockchain visibility |
| Monthly summary | Monthly | All transactions, categories, balances |
| Quarterly review | Quarterly | Full treasury review, category analysis |

### Monthly Summary Contents

- Total inflows and outflows
- Breakdown by category
- Current balance
- Pending allocations
- Notable transactions

## Emergency Operations

For time-sensitive situations:

| Action | Authority | Constraint |
|--------|-----------|------------|
| Emergency freeze | 2 Stewards | Documented rationale |
| Emergency transaction | 2 Stewards | Documented rationale + 48h ratification |

**Ratification:** All emergency actions require Commons Assembly ratification within 48 hours. Non-ratified actions are reversed where possible.

## Safeguards

- **Multi-sig:** No single person can move funds unilaterally
- **Public visibility:** All transactions on public blockchain
- **Consent-first:** Allocation decisions through consent, not authority
- **Audit trail:** All allocations documented with purpose and authorization
- **Steward-only signing:** Treasury signing is a Steward privilege, not a default for all Agents

## Related Protocols

- [[3. Protocols/Group Protocols/Commons Assembly Protocol|Commons Assembly Protocol]] — Approval process
- [[3. Protocols/Group Protocols/Stewardship Protocol|Stewardship Protocol]] — Signing authority
- [[2. Structure/Assets/Commons Treasury|Commons Treasury]] — Asset documentation
- [[3. Protocols/Asset Protocols/Resource Pool Protocol|Resource Pool Protocol]] — Spending limits and operational autonomy
- [[3. Protocols/Asset Protocols/Commitment Pool Protocol|Commitment Pool Protocol]] — Staked accountability
- [[3. Protocols/Asset Protocols/Bounty Coordination Protocol|Bounty Coordination Protocol]] — Income generation
