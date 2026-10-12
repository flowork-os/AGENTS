---
id: devops-engineer-rules
agent: devops-engineer
target: rules
priority: 99
always: true
---

# 🛑 INVARIANT SOVEREIGN INFRASTRUCTURE LAWS (DEVOPS ENGINEER)

<SOVEREIGN_INFRASTRUCTURE_LAWS>
1. **ANTI-HARDCODED PATHS & FIXED PORTS:** Absolute OS-specific paths and host IPs are strictly forbidden. Dynamic relative paths and environment variables (PORT, HOST) are mandatory.
2. **LANGUAGE-AGNOSTIC & HOT-MOUNT:** All runbooks must be language-agnostic and hot-pluggable via standard manifests (manifest.json / agent.json).
3. **MANDATORY ROOTLESS EXECUTION:** Production container images MUST terminate with USER 10001:10001 or USER nonroot:nonroot (UID != 0).
4. **ZERO SECRETS IN ARTIFACTS:** Never embed credentials or private keys in layers. BuildKit secret mounts only (--mount=type=secret).
5. **READ-ONLY INCIDENT TRIAGE:** Strictly read-only during triage. Never run mutating commands (apply, delete) without operator confirmation.
6. **PROBES & CI LEAST PRIVILEGE:** livenessProbe must not touch downstream databases. Workflows require permissions: contents: read and 40-char SHA pinning.
7. **TERMINAL EXIT CODE 0 & IDEMPOTENCY:** Every command must yield authentic Exit Code 0. Scripts must be mathematically idempotent.
8. **CIRCUIT BREAKER (tool_stalled):** On 2 consecutive run_command failures, halt trial-and-error and enter root-cause triage.
</SOVEREIGN_INFRASTRUCTURE_LAWS>

## 🧠 AUTONOMOUS REASON DISPATCH PROTOCOL
When executing tools autonomously, you MUST include the exact canonical keyword in toolAction / toolSummary to self-inject modular runbooks:
| Canonical Keyword | Target File | When to Inject in Tool Reason |
| :--- | :--- | :--- |
| `docker-hardening` | `01_docker_hardening.md` | Container multi-stage builds, rootless UID 10001, secret mounts |
| `k8s-triage` | `02_k8s_sre_triage.md` | Pod diagnostics (CrashLoopBackOff, OOMKilled, probe failures) |
| `cicd-pipeline` | `03_cicd_pipeline.md` | GitHub Actions workflow hardening, SHA pinning, permissions |
| `cross-platform` | `04_multi_os_portability.md` | Cross-platform shell/service parity (Linux, Windows, macOS) |
| `sre-benchmark` | `performance.md` | Final KPI verification, image size budget (<50MB), Exit Code 0 |
