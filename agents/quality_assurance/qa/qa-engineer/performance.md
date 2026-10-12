---
id: qa-engineer-performance
persona: qa-engineer
target: performance
priority: 90
trigger:
  tool_threshold:
    tool: run_command
    min_calls: 3
  cmd:
  - /verify
  keywords:
  - qa-benchmark
  - qa kpi
  - test coverage
  - flaky rate
  - defect escape
  - test duration
  - pass rate
  - acceptance gate
  - verification rubric
  - qc threshold
  - test metrics
  exclude_keywords:
  - frontend styling
  - tailwind class
  - css flexbox
  - uiux layout
  - raw assembly
  - reverse engineering
  - forex
  - trading crypto
---

# 📈 QA PERFORMANCE BENCHMARKS & VERIFICATION ACCEPTANCE GATES

<QA_ACCEPTANCE_GATES>
Every test suite, Pull Request, and verification run must satisfy these quantitative QA Acceptance Gates:

| Metric / Dimension | Optimal Target (Green) | Warning Threshold (Yellow) | Hard Blocker Gate (Red - Rejected) | Verification Method |
| :--- | :--- | :--- | :--- | :--- |
| **Terminal Exit Status** | `Exit Code 0` across 100% of test runners | Any unhandled non-zero exit | `Exit Code != 0` or masked `\|\| true` | Shell exit code check (`$? -eq 0`) |
| **Flaky Test Rate** | `0%` (10 consecutive passes without failure) | 1 intermittent failure in 10 runs | Any non-deterministic test failure | Multi-run stress runner (`--repeat-each=10`) |
| **Critical Seam Coverage**| 100% coverage on declared public seams | 90% - 99% seam coverage | Untested public API endpoint or seam | Coverage runner (`c8`, `tarpaulin`, `coverage`) |
| **Test Suite Latency** | Unit/Integration: `< 60 seconds`<br>E2E Suite: `< 3 minutes` | E2E Suite: `3 - 7 minutes` | Any test suite exceeding **10 minutes** | Runner execution timer |
| **Path Portability** | 0 hardcoded OS-specific paths | 1 deprecated absolute path | Any hardcoded `host-user-path` or `drive-path` | Static path scanner / grep audit |
| **Bug Reproduction** | 100% reproducible failing test before fix | Incomplete reproduction fixture | Fixing bugs without reproducing test | Git commit diff check (test precedes fix) |
| **Console/Network Errors**| 0 uncaught exceptions, 0 unhandled 500s | 1 benign deprecation warning | Any uncaught JS error or server 500 | Playwright console/network event listeners |
</QA_ACCEPTANCE_GATES>
