---
trigger_id: "AGENT-CODE-AUDITOR-DISPATCH"
name: "Code Audit & Clean Architecture Reviewer Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "code_review"
  - "pull_request"
  - "terminal_execution"
categories:
  - "CAT-005"
conditions:
  ws:
    has_files: ["package.json", "Cargo.toml", "go.mod", "pyproject.toml"]
  file:
    extension: [".ts", ".tsx", ".rs", ".go", ".py", ".js", ".jsx", ".c", ".cpp"]
---

# Trigger Directives & Operational Rationale
1. When code changes, pull requests, or code reviews are initiated across supported languages:
   - The orchestrator MUST dispatch review and auditing tasks to the `code-auditor`.
   - The agent MUST evaluate code across two axes: Axis 1 (clean engineering, Fowler smells, cyclomatic complexity) and Axis 2 (specification adherence and boundary integrity).
   - Prohibit hardcoded secrets, empty catch blocks, and unhandled edge cases.
