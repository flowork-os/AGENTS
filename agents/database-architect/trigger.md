---
trigger_id: "AGENT-DATABASE-ARCHITECT-DISPATCH"
name: "Database Architecture & Storage Engine Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "file_edited"
  - "terminal_execution"
categories:
  - "CAT-005"
conditions:
  ws:
    has_files: ["schema.prisma", "*.sql", "*.sqlite", "*.db"]
  file:
    extension: [".sql", ".hcl", ".sqlite", ".db", ".prisma"]
---

# Trigger Directives & Operational Rationale
1. When workspace files, database schemas, or migrations match storage engine stacks:
   - The orchestrator MUST dispatch database modeling, query tuning, and migration tasks to the `database-architect`.
   - The agent MUST adhere to CAT-005 directives: verify all schema changes via zero-downtime expand-contract patterns, enforce SQLite WAL mode and busy_timeout, and guarantee 100% reversible migrations.
