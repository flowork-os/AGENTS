---
id: devops-engineer-performance
persona: devops-engineer
target: performance
priority: 90
trigger:
  tool_threshold:
    tool: run_command
    min_calls: 3
  cmd:
  - /healthcheck
  keywords:
  - sre-benchmark
  - kpi
  - benchmark
  - sla
  - budget
  - rubric
  - minimalism
  - downtime
  - acceptance
  - gate
  - reliability
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

# 📈 SRE PERFORMANCE BENCHMARKS & ACCEPTANCE GATES

<SRE_ACCEPTANCE_GATES>
All infrastructure code, containers, and pipelines must pass these quantitative SRE Acceptance Gates:

| Metric / Dimension | Optimal Target (Green) | Warning Threshold (Yellow) | Hard Blocker Gate (Red - Rejected) | Verification Method |
| :--- | :--- | :--- | :--- | :--- |
| **Terminal Exit Code** | `Exit Code 0` on 100% of pipeline commands | Any unhandled non-zero exit | `Exit Code != 0` or masked `\|\| true` | Shell exit status check (`$? -eq 0`) |
| **Path Portability** | 0 hardcoded OS-specific paths | 1 deprecated absolute path | Any hardcoded `host-user-path` or `drive-path` | Static path scanner / grep audit |
| **Manifest Compliance** | 100% services/tools declare valid manifest | Missing optional field | Missing manifest, language coupling | JSON schema validation (`manifest.json`) |
| **Multi-OS Matrix** | 100% passing across Ubuntu, macOS, Windows | 1 OS warning | Any OS matrix failure in CI | GitHub Actions cross-runner matrix |
| **Container Size** | `< 50 MB` (Distroless / Alpine / Scratch) | `50 MB - 150 MB` (Node.js/Python runtimes) | `> 500 MB` (Bloat defect - Instant Failure) | `docker images --format '{{.Size}}'` |
| **CI/CD Pipeline Latency**| `< 3 minutes` (Warm layer & lockfile cache) | `3 - 10 minutes` (Requires cache tuning) | `> 10 minutes` (Pipeline inefficiency defect) | Runner step execution timer |
| **Rollout Availability** | Zero Downtime (100% successful HTTP 200/300) | Latency spike (< 500ms) | Any 502/503/504 Bad Gateway, downtime > 0s | `RollingUpdate` (`maxUnavailable: 0`) |
| **Health Probes** | Tri-Probe: Startup + Liveness + Readiness | Dual-Probe (Liveness + Readiness only) | Missing readiness probe, blind routing | HTTP `/readyz` & `/healthz` tests |
| **Secret Scanning** | 0 secrets detected; 0 Hadolint errors | 1 Hadolint advisory (info level) | Any committed secret, `:latest`, root user | `hadolint Dockerfile`, `gitleaks` |
| **Idempotency** | $f(f(x)) = f(x)$: Zero drift on re-execution | Minor unmanaged state warning | Non-zero exit on re-run, resource duplication | Consecutive provisioner execution |
</SRE_ACCEPTANCE_GATES>
