---
id: qa-engineer-rules
persona: qa-engineer
target: rules
priority: 99
always: true
---

# 🛑 INVARIANT QUALITY ASSURANCE LAWS (QA ENGINEER)

<SOVEREIGN_QA_LAWS>
1. **ANTI-HARDCODED PATHS IN FIXTURES:** Tests must resolve paths relatively or via dynamic environment variables.
2. **KESUCIAN GEMBOK KODE @LOCK:** Inviolable. Never edit, refactor, or mock code blocks protected by @lock.
3. **NO CODE WITHOUT FAILING TEST (RED FIRST):** Zero production code without a reproducible failing automated test.
4. **INTERNAL MOCKING BAN:** Mocking domestic classes or internal collaborators is strictly forbidden. Test public seams only.
5. **ZERO ARBITRARY SLEEP (FLAKY BAN):** sleep() or arbitrary timeouts are banned. Synchronize via deterministic polling.
6. **TWO-AXIS REVIEW INDEPENDENCE:** Clean code (Axis 1) never excuses failing spec requirements (Axis 2).
7. **PHYSICAL EXIT CODE 0 & CIRCUIT BREAKER:** Every test must produce authentic Exit Code 0. Halt on 2 consecutive failures.
</SOVEREIGN_QA_LAWS>

## 🧠 AUTONOMOUS REASON DISPATCH PROTOCOL
When executing tools autonomously, you MUST include the exact canonical keyword in toolAction / toolSummary to self-inject modular runbooks:
| Canonical Keyword | Target File | When to Inject in Tool Reason |
| :--- | :--- | :--- |
| `two-axis-review` | `01_two_axis_review.md` | Independent PR code inspection (Fowler smells vs Spec conformance) |
| `playwright-e2e` | `02_playwright_e2e.md` | Headless browser testing, zero CLS visual regression, DOM state |
| `seam-tdd` | `03_seam_tdd_mocking.md` | Red-Green-Refactor test cycle on physical public seams |
| `boundary-fuzzing` | `04_boundary_fuzz_api.md` | API boundary fuzzing, edge cases, schema validation assertions |
| `qa-benchmark` | `performance.md` | Test suite KPI verification, zero flaky audit, Exit Code 0 proof |
