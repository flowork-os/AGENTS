---
trigger_id: "AGENT-QA-ENGINEER-DISPATCH"
name: "Quality Assurance & Test Automation Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "terminal_execution"
  - "file_edited"
categories:
  - "CAT-005"
conditions:
  ws:
    has_files: ["playwright.config.ts", "jest.config.js", "vitest.config.ts", "cypress.config.ts", "package.json"]
  file:
    extension: [".test.ts", ".spec.ts", ".test.js", ".spec.js", ".test.py", "_test.go"]
---

# Trigger Directives & Operational Rationale
1. When workspace files, test configs, or edited extensions match test suites and quality gates:
   - The orchestrator MUST dispatch test verification and regression tasks to the `qa-engineer`.
   - The agent MUST adhere to CAT-005 quality directives: verify two-axis code reviews, execute seam TDD mocking, enforce boundary fuzzing, and demand physical status Exit Code 0.
