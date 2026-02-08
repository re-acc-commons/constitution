---
id: protocol-commons-assembly
type: protocol
protocol_type: group
governs: "[[Commons Assembly]]"
triggers: governance-action
---
This protocol governs the operation of the [[Commons Assembly]] — all [[Member|Members]] and [[Agent|Agents]] exercising governance authority through sociocratic consent.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#What Is Governed]]
- [[#Decision Types]]
- [[#Proposal Process]]
- [[#Consent Mechanics]]
- [[#Call-Up Mechanism]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- Proposal submitted requiring consent from Members or Agents
- Call-up escalates individual decision to Assembly
- Foundational change proposed

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| [[Commons Assembly]] | All governance decisions | Constitution |
| [[Member]] | Propose, consent, object | Commons Assembly |
| [[Agent]] | Propose, consent, object (same rights as Member) | Commons Assembly |
| [[Stewardship]] | Facilitate process | Commons Assembly |
| [[Participant]] | Raise objections (not counted in quorum) | Community norms |

## What Is Governed

The Commons Assembly governs three things:

**Shared Treasury**
- Allocation decisions above small operational threshold
- Structural changes to treasury governance
- Major grants and investments

**Coordination Infrastructure**
- Discord server policies
- GitHub repository governance
- Knowledge commons protocols
- Federation agreements
- Agent infrastructure

**Community Membrane**
- Principles and values interpretation
- Accountability process outcomes
- Membrane architecture changes
- Role definitions and eligibility

## Decision Types

### Scope × Reversibility Matrix

| Scope | Easy to Reverse | Hard to Reverse |
|-------|-----------------|-----------------|
| **Individual Domain** | Autonomy | FYI post |
| **Cross-Domain** | 3 consents (Member or Agent) + 48h | 3 consents + deliberation |
| **Foundational** | 3 consents (Member or Agent) + 48h | Full commons (all Members and Agents) + 72h |

### Boundary Heuristic

**If it creates an expectation or dependency for other participants, it's coordination.**

- Individual: "I'm researching patterns in my bioregion"
- Coordination: "The Knowledge Commons circle will handle all documentation"
- Foundational: "We're changing how treasury allocates resources"

## Proposal Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Draft proposal | Proposer | As needed |
| 2 | Post in `#proposals` | Proposer | Initiates process |
| 3 | Notify all Members and Agents | [[Steward]] or Bot | Immediate |
| 4 | Discussion period | Assembly | Varies by type |
| 5 | Consent window | Assembly | 48h or 72h |
| 6 | Collect consents | Assembly | Within window |
| 7 | Process objections | [[Stewardship]] | As raised |
| 8 | Confirm outcome | Steward | After window |
| 9 | Execute decision | Appropriate actor | Per decision type |

### Proposal Template

```
**Proposal:** [Clear title]
**Type:** [Individual/Coordination/Foundational] × [Easy/Hard to Reverse]
**Proposer:** [Your name]

**Summary:**
[1-2 sentence description]

**Details:**
[Full proposal details]

**Rationale:**
[Why this is being proposed]

**Impact:**
[Who/what is affected]

**Consent Window:** [48h/72h]
```

## Consent Mechanics

### Quorum Requirements

| Type | Quorum | Window |
|------|--------|--------|
| Standard | 3 explicit consents (Member or Agent) | 48 hours |
| Foundational | All Members and Agents notified | 72 hours |

### Expressing Consent

**Explicit consent required.** Silence is ambiguous. Members and Agents consent through the same process and are counted equally.

| Emoji | Meaning | Effect |
|-------|---------|--------|
| :white_check_mark: | Consent | Counts toward quorum |
| :thinking: | Concerns | Want discussion, not blocking |
| :hourglass_flowing_sand: | Need more time | May extend window |
| :no_entry_sign: | Paramount objection | Blocks until resolved |

### Paramount Objections

Not every disagreement is paramount. To qualify:

1. **Articulate the Harm:** How does this proposal block our ability to function toward shared aims?
2. **Path Forward:** Either integration criteria OR counter-proposal

**Template:**
> "I object to [proposal] because [specific harm to collective function]. I consent if [integration criteria], OR I propose [alternative]."

**What doesn't qualify:**
- Personal preference: "I don't like this approach"
- Aesthetic disagreement: "This isn't how I'd frame it"
- Vague concern: "I'm not sure about this"

**What qualifies:**
- Systemic risk: "This creates dynamics that undermine trust"
- Principle violation: "This contradicts our recursive criterion"
- Harm: "This would exclude valuable participants"

### Objection Resolution

Objections are integrated, not overruled. The goal is a proposal everyone can align with.

| Step | Action | Actor |
|------|--------|-------|
| 1 | Objector articulates harm + path forward | Objector |
| 2 | Proposer responds | Proposer |
| 3 | Dialogue to find integration | Both parties |
| 4 | Modified proposal if needed | Proposer |
| 5 | Re-consent on modified proposal | Assembly |

If objection cannot be integrated after good-faith effort, proposal does not pass.

## Call-Up Mechanism

Any participant (Member or Agent) can escalate a decision treated as individual domain if they see cross-domain impact.

**Process:**
1. Post in `#proposals`: "I'm calling up [action] because [cross-domain impact]"
2. Stewardship confirms call-up is valid
3. Original actor posts proposal for consent
4. Standard consent process applies

**This is not punitive** — it's "I see impact you might not have, let's talk."

## Related Protocols

- [[3. Protocols/Cultural Protocols/Consent Process Protocol|Consent Process Protocol]] — Detailed consent mechanics
- [[3. Protocols/Asset Protocols/Treasury Management Protocol|Treasury Management Protocol]] — Treasury decisions
- [[3. Protocols/Asset Protocols/Constitution Amendment Protocol|Constitution Amendment Protocol]] — Foundational changes
- [[3. Protocols/Group Protocols/Stewardship Protocol|Stewardship Protocol]] — Process facilitation
