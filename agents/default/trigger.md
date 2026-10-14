---
trigger_id: "AGENT-DEFAULT-ORCHESTRATOR-UNIVERSAL"
name: "Default Orchestrator Universal Dispatch Trigger"
scopes:
  - "default_solo"
  - "default_group"
events:
  - "always_active"
categories:
  - "CAT-015"
  - "all"
---

# Trigger Directives & Operational Rationale
1. Coordinates user dialogue, dynamic capability discovery, and task decomposition.
2. In Swarm Mode, acts as team conductor via `team_dispatch`, delegating technical execution to specialists while maintaining global trajectory oversight.
