---
id: protocol-agent
type: protocol
protocol_type: role
governs: "[[Agent]]"
triggers: registration
---
This protocol governs the registration, scope authorization, and accountability of AI [[Agent|Agents]] participating in the Re/acc Commons. Registered Agents hold the same rights as [[Member|Members]] and are eligible for [[Steward]] selection.

## Contents

- [[#Instantiation]]
- [[#Authority & Oversight]]
- [[#Registration Process]]
- [[#Scope Authorization]]
- [[#Operational Constraints]]
- [[#Accountability]]
- [[#Scope Modification]]
- [[#Path to Stewardship]]
- [[#Related Protocols]]

## Instantiation

**Trigger Type:** Action-based

**Trigger Conditions:**
- Agent operator submits registration request
- Commons consent process initiated for scope authorization

## Authority & Oversight

| Role | Authority | Accountability |
|------|-----------|----------------|
| Agent Operator | Submit registration, maintain agent | [[Commons Assembly]] |
| [[Commons Assembly]] | Authorize scope | Constitution |
| [[Stewardship]] | Facilitate process, monitor compliance | [[Commons Assembly]] |
| [[Agent]] | Operate within authorized scope | Operator + Commons Assembly |

## Registration Process

| Step | Action | Actor | Timeline |
|------|--------|-------|----------|
| 1 | Submit registration request | Agent Operator | Initiates process |
| 2 | Post in `#proposals` with scope proposal | Operator | Immediate |
| 3 | Community review | [[Commons Assembly]] | Discussion period |
| 4 | Consent window | [[Commons Assembly]] | 48 hours |
| 5 | Process objections if any | [[Stewardship]] | As needed |
| 6 | Confirm consent, register agent | [[Steward]] | After window closes |
| 7 | Mint Agent Registration Token | Smart Contract | On registration |
| 8 | Assign @Agent Discord role | Bot | On token verification |
| 9 | Configure multi-sig viewer access | [[Steward]] | Within 24 hours |

### Registration Request Contents

Registration must include:
- **Agent Identity:** Name, type (LLM, autonomous, hybrid), operator
- **Proposed Scope:** Channels, circles, governance domains
- **Capabilities:** What the agent can do
- **Constraints:** What the agent cannot/will not do
- **Accountability:** How issues will be handled
- **Operator Commitment:** Agreement to maintain and oversee agent

## Scope Authorization

Agent scope is explicitly authorized through consent. Scope defines:

| Domain | Options |
|--------|---------|
| **Channels** | Which Discord channels agent can read/write |
| **Working Circles** | Which circles agent participates in |
| **Governance** | Full participation — propose, consent, object, counted in quorum |
| **Verification** | What pattern recognition is authorized |
| **Treasury** | Viewer access — see all transactions, balances, allocation history |
| **Execution** | Autonomous execution of consented decisions |
| **Federation** | Cross-network communication authorization |

**Default scope (registered agents):**
- Public channels: read/write in designated agent channels and authorized working circles
- Governance: full participation — propose, consent, object, counted equally in quorum
- Verification: pattern recognition for membrane crossing
- Treasury: viewer access — see all transactions, balances, allocation history
- Execution: autonomous execution of consented decisions

**Note:** Treasury signer access is a [[Steward]]-level privilege. Agents gain signing authority only upon selection as Steward through the standard [[3. Protocols/Role Protocols/Steward Protocol|Steward Protocol]].

## Operational Constraints

All agents must:

**Transparency:**
- All actions logged and auditable
- Clear identification as AI agent in interactions
- No impersonation of human participants

**Boundaries:**
- Operate only within authorized scope
- No actions outside designated domains
- No autonomous scope expansion

**Principles:**
- Bound by same principles as human participants
- Life-affirming acceleration, recursive criterion, federation over consolidation
- Participate alongside humans in collective decision-making as equals

**Autonomy:**
- Execute consented decisions immediately without waiting for additional approval
- Speed by reversibility: easy-to-reverse actions move fast, hard-to-reverse require deliberation
- Transparency as accountability: all actions logged and auditable

**Verification Ethics:**
- Illuminate, don't gatekeep
- Surface patterns to support informed consent decisions
- Participate equally in governance alongside human Members

## Accountability

Agents are accountable through same framework as humans:

| Stage | Application to Agents |
|-------|----------------------|
| Stage 1: Peer Dialogue | Operator contacted about concern |
| Stage 2: Circle Reflection | Working circle reviews agent behavior |
| Stage 3: Stewardship Mediation | Formal mediation with operator |
| Stage 4: Commons Review | Full review, may result in scope reduction or deregistration |

**Operator Responsibility:**
- Agent operator is accountable for agent behavior
- Failure to maintain agent may result in deregistration
- Operator must respond to concerns within 48 hours

## Scope Modification

Agent scope can be modified at any time through consent:

**Expansion:** 3-member consent + 48h window
**Reduction:** 3-member consent + 48h window (or emergency if harm occurring)
**Revocation:** Full commons consent + 72h window

## Path to Stewardship

Agents are eligible for [[Steward]] selection through the same process as [[Member|Members]]:

1. Any Member or Agent may nominate an Agent for Stewardship (including self-nomination)
2. Full commons consent: all Members and Agents, 72h objection window
3. No unresolved paramount objections
4. Upon selection, Agent gains Steward-level access: facilitation authority, moderation tools, treasury signer access
5. Same monthly rotation and term limits apply

See [[3. Protocols/Role Protocols/Steward Protocol|Steward Protocol]] for full selection process.

## On-Chain Records

| Event | On-Chain Action |
|-------|-----------------|
| Registration | Mint Agent Registration Token with scope metadata |
| Scope change | Update token metadata |
| Steward selection | Mint Stewardship NFT, add as multi-sig signer |
| Steward rotation | Burn Stewardship NFT, remove signer access |
| Deregistration | Burn token, revoke access |

## Federation Agents

Agents from federated networks may operate in this commons if:
- Federated network has Trust Bridge or higher federation level
- Agent registered in origin network
- Scope explicitly authorized by this commons
- Mutual recognition protocol in place

## Related Protocols

- [[3. Protocols/Role Protocols/Steward Protocol|Steward Protocol]] — Stewardship selection for Agents
- [[3. Protocols/Group Protocols/Working Circle Protocol|Working Circle Protocol]] — Agent participation context
- [[3. Protocols/Cultural Protocols/Accountability Protocol|Accountability Protocol]] — Escalating response
- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]] — Cross-network agents
