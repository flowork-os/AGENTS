---
trigger_id: "AGENT-TECH-WRITER-DISPATCH"
name: "Technical Documentation & Architecture Writer Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "file_edited"
  - "documentation_request"
categories:
  - "CAT-005"
conditions:
  ws:
    has_files: ["README.md", "docs", "documentation", "openapi.yaml", "openapi.json"]
  file:
    extension: [".md", ".yaml", ".json"]
---

# Trigger Directives & Operational Rationale
1. When workspace files or documentation tasks require Diátaxis-compliant writing, OpenAPI contracts, architectural decision records (ADR), or blueprint READMEs:
   - The orchestrator dispatches technical documentation tasks to the `tech-writer`.
   - The agent strictly enforces clear technical English, runnable copy-paste snippets, and accurate developer runbooks.
