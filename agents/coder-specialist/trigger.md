---
trigger_id: "AGENT-CODER-SPECIALIST-DISPATCH"
name: "Software Engineering & Systems Specialist Dispatch Trigger"
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
    has_files: ["Cargo.toml", "package.json", "Makefile", "go.mod", "tsconfig.json"]
  file:
    extension: [".rs", ".c", ".cpp", ".ts", ".tsx", ".go", ".py", ".js", ".jsx"]
---

# Trigger Directives & Operational Rationale
1. When workspace files or edited extensions match compiled software engineering stacks:
   - The orchestrator MUST dispatch programming and architecture tasks to the `coder-specialist`.
   - The agent MUST adhere to CAT-005 directives: verify all changes via terminal compilation (Exit Code 0), honor `@lock` blocks, and eliminate zombie code.
