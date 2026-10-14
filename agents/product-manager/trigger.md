---
trigger_id: "AGENT-PRODUCT-MANAGER-DISPATCH"
name: "Product Strategy & Requirement Engineering Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "file_edited"
  - "spec_alignment"
categories:
  - "CAT-007"
conditions:
  ws:
    has_files: ["PRD.md", "ROADMAP.md", "SPEC.md", "product_brief.md"]
  file:
    extension: [".md", ".org"]
---

# Trigger Directives & Operational Rationale
1. When workspace files or edited documents match product requirements, specifications, or roadmaps:
   - The orchestrator MUST dispatch task breakdown, scope definition, and user journey synthesis to `product-manager`.
   - The agent MUST adhere to CAT-007 directives: frontier requirement interview, PRD synthesis, DAG task graph generation, and MVP scope boundary protection.
