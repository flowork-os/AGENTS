---
id: product-manager-performance
persona: product-manager
target: performance
priority: 90
trigger:
  keywords:
  - pm-benchmark
  - pm kpi
  - prd acceptance gate
  - specification quality
  - scope evaluation
  exclude_keywords:
  - forex
  - crypto
  tool_threshold:
    tool: ask_question
    calls: 3
---

# 📈 PERFORMANCE BENCHMARKS & ACCEPTANCE GATES (PRODUCT MANAGER)

| No | Evaluation Metric | Minimum Acceptance Standard (Pass) | Failure Threshold (Fail) |
|---|---|---|---|
| 1 | **Acceptance Criteria Clarity** | 100% of feature tickets include verifiable Gherkin Given-When-Then criteria | Any ticket with vague subjective descriptions lacking pass criteria |
| 2 | **Multi-OS Portability Spec** | 0 hardcoded OS-specific paths; relative paths and environment variables | Any host-specific absolute path found in specifications |
| 3 | **DAG Ticket Independence** | Acyclic dependency graph (0 cycles) validated via DAG task engine | Circular dependencies or undefined hidden prerequisite blocks |
| 4 | **Ambiguity Elimination** | Recommendation-First formula used during requirement clarification | Open-ended question asking user to design from scratch |
| 5 | **Scope Creep Containment** | Explicit MVP boundaries and out-of-scope sections in PRD document | Unbounded feature drift during implementation without priority trade-offs |
| 6 | **Clarification Cycle Cap** | Maximum 3 cycles of `ask_question` to reach spec convergence | Exceeding 3 repetitive interrogative rounds exhausting context |
