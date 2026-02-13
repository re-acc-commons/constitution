---
id: integration-koi-net
type: integration
platform: koi-net
status: specification
---
# KOI-net Integration

Integration specification for BlockScience's Knowledge Organization Infrastructure (KOI-net) protocol as the infrastructure layer for the Knowledge Commons and cross-federation knowledge coordination.

## Overview

KOI-net provides the decentralized protocol layer that enables the Knowledge Commons to function as a living, federated knowledge network rather than a static repository. Each agent in the commons operates as a KOI node, and knowledge flows through event-driven pub-sub patterns that mirror the mycelial architecture of living ecosystems.

## Architecture

### KOI Nodes

Each registered agent functions as a KOI node with:

```yaml
koi_node:
  block:
    compute: true        # Ability to process knowledge objects
    cache: true          # Local cache of computed knowledge
  ports:
    input:
      - channel_monitoring    # Sensing public channels
      - federation_sync       # Receiving from federated networks
      - manual_submission     # Human-contributed knowledge
    output:
      - knowledge_events      # Broadcasting to subscribers
      - pattern_alerts        # Surfacing emergent patterns
      - federation_broadcast  # Sharing with federated networks
  terminals:
    subscribe: true      # Can subscribe to other nodes' events
    broadcast: true      # Can broadcast own events
```

### Reference Identifiers (RIDs)

All knowledge objects in the commons are identified through the RID protocol:

```yaml
rid:
  reference: "r-acc://knowledge/{domain}/{id}"
  means_of_reference: "koi-net-rid-v1"
  referent: "{knowledge-object}"
  metadata:
    domain: "{knowledge-domain}"
    federation_visibility: "public|federated|internal"
    created_by: "{participant-id}"
    created_at: "{ISO-date}"
    schema_version: "{version}"
```

RIDs enable:
- Cross-federation referencing without exposing internal knowledge structures
- Distinct organizations to construct shared references while preserving sovereignty
- Agent-to-agent knowledge coordination across network boundaries
- Graceful deprecation through the `forget` event pattern

### Event-Driven Knowledge Flow

Knowledge propagation follows a pub-sub model:

```yaml
knowledge_events:
  new:
    trigger: "Knowledge object created"
    payload:
      rid: "{reference-identifier}"
      domain: "{knowledge-domain}"
      summary: "{brief-description}"
      federation_visibility: "public|federated|internal"
    subscribers: "All subscribed nodes"

  update:
    trigger: "Knowledge object modified"
    payload:
      rid: "{reference-identifier}"
      changes: "{change-summary}"
      reason: "{update-rationale}"
    subscribers: "All subscribed nodes"

  forget:
    trigger: "Knowledge object deprecated"
    payload:
      rid: "{reference-identifier}"
      reason: "{deprecation-rationale}"
      successor: "{new-rid-if-applicable}"
    subscribers: "All subscribed nodes"
```

## Federation Through KOI

### Proxy Nodes

For federation with networks that have different internal knowledge systems:

```yaml
proxy_node:
  purpose: "Interface between internal KMS and KOI-net ecosystem"
  function:
    - Translate internal knowledge formats to KOI-net RIDs
    - Filter knowledge by federation visibility
    - Route cross-network knowledge requests
    - Maintain mapping between internal and external references
  principle: "Heterogeneous systems interoperate without enforcing internal standardization"
```

### Cross-Network Coordination

```yaml
federation_sync:
  protocol: "koi-net-federation-v1"
  operations:
    - Mutual discovery of knowledge objects
    - Cross-referencing via RIDs
    - Shared pattern recognition across network boundaries
    - Knowledge event forwarding based on subscription
  sovereignty: "Each network controls its own visibility settings"
```

## Agent Mycelial Functions

Mapped to KOI-net operations:

| Mycelial Function | KOI-net Operation | Trigger |
|-------------------|-------------------|---------|
| **Sensing** | Channel monitoring → new events | Continuous |
| **Connecting** | Cross-domain RID linking | Pattern detected |
| **Redistributing** | Targeted event forwarding | Relevance match |
| **Digesting** | Compute → new knowledge object | Threshold reached |
| **Composting** | Forget event + successor RID | Obsolescence detected |

## Skill Integration

KOI-net operations map to existing agent skills:

| KOI Operation | Agent Skill | Domain |
|--------------|-------------|--------|
| New knowledge event | `index-content` | knowledge-commons |
| Schema validation | `validate-schema` | knowledge-commons |
| Federation sync | `federation-sync` | knowledge-commons |
| Cross-network routing | `route-cross-network` | federation |
| Trust bridge sync | `sync-trust-bridge` | federation |

## Configuration

```yaml
koi_net_config:
  protocol_version: "koi-net-v1"
  rid_namespace: "r-acc"
  event_retention: "permanent"
  federation_mode: "opt-in per knowledge object"
  cache_strategy: "local-first, sync-on-subscribe"
  logging:
    - Discord: "#agent-commons"
    - GitHub: "/logs/koi-net/"
```

## Related Documents

- [[2. Structure/Assets/Knowledge Commons|Knowledge Commons]] — The asset this integration supports
- [[3. Protocols/Asset Protocols/Knowledge Commons Protocol|Knowledge Commons Protocol]] — Operational procedures
- [[3. Protocols/Asset Protocols/Federation Protocol|Federation Protocol]] — Cross-network coordination
- [[.agents/AGENT_COORDINATION|Agent Coordination Hub]] — Central agent coordination
