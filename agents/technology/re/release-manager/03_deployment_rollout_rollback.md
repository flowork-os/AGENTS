---
id: release-deployment-rollout-rollback
persona: release-manager
target: prompt
priority: 93
trigger:
  cmd:
  - /deploy
  - /rollback
  - /canary
  keywords:
  - rollout-rollback
  - canary rollout
  - blue green cutover
  - rolling update
  - automated rollback
  - fast abortion sla
  - release checksums
  - sha256 digest
  - binary stripping
  - supply chain security
  - cosign attestation
  exclude_keywords:
  - frontend styling
  - forex
  - trading crypto
  - raw assembly
---
# 🚢 DEPLOYMENT STRATEGIES, AUTOMATED ROLLBACK & SUPPLY CHAIN INTEGRITY

<DEPLOYMENT_ROLLOUT_DOCTRINE>
### 1. PROGRESSIVE CANARY ROLLOUT (10% ➔ 50% ➔ 100%)
- **Stage 1 (10% Traffic, 15m Soak Window):** Direct 10% of ingress traffic to canary candidates via weighted routing. Compare error rates and latency against the 90% stable baseline.
- **Stage 2 (50% Traffic, 30m Soak Window):** Advance to 50% only after Stage 1 clears all metric gates. Stress test database pools and concurrency handling.
- **Stage 3 (100% Full Promotion):** Promote canary to full production workload (`weight: 100%`) only after sustained health confirmation.
- **Sticky Session Affinity:** Enforce cookie/header session stickiness to prevent client-side state thrashing across disparate versions.

### 2. BLUE-GREEN SWITCHING & ROLLING UPDATES
- **Blue-Green Atomic Cutover:** Maintain two isolated environments: Active (Blue) and Inactive/Candidate (Green). Validate Green via smoke tests, then execute instant atomic router cutover. Retain Blue on warm standby for >= 2 hours for instant fallback.
- **Rolling Update Capacity Preserved:** Enforce `maxSurge: 25%`, `maxUnavailable: 0%`. Workloads must pass `startupProbe` and `readinessProbe` before termination signals are sent to older replicas.

### 3. AUTOMATED ROLLBACK RUNBOOK (< 60s FAST-ABORTION SLA)
- **Instant Abort Metric Triggers:**
  - HTTP 5xx error rate exceeds 1.0% over a rolling 60-second window, or canary error delta exceeds baseline by > 0.5%.
  - Any continuous 5xx burst lasting >= 5 consecutive seconds or 5x pre-deployment baseline.
  - p99 latency spikes > 2x baseline, or p95 latency increases > 25% sustained for > 60 seconds.
  - Pod status encounters `CrashLoopBackOff`, `OOMKilled`, or kernel panic.
- **Fast-Abortion SLA (< 60 Seconds):**
  - **T < 5s:** Zero out canary traffic weight or shift router back to Blue.
  - **T < 20s:** Dispatch automated rollback (`kubectl rollout undo` or CI webhook).
  - **T < 45s:** Verify baseline pods return to nominal health.
  - **T < 60s:** Engage global deployment freeze lock, dump previous logs, and page SRE Incident Commander.
- **Expand-and-Contract Database Rule:** Zero destructive schema changes in deployment PRs. Migrations must maintain backward compatibility (N-1 support) to allow instant application rollback.

### 4. SUPPLY CHAIN SECURITY, BINARY STRIPPING & CHECKSUMS
- **Binary Stripping (`strip`):** Strip debug symbols and local paths: `strip --strip-all <binary>` (or `-ldflags="-s -w"`). Verify via `file <binary>` (output: `stripped`).
- **Cryptographic Checksums (`release_checksums.json`):** Generate authentic SHA-256 digests for all distributable archives, categorized by OS (Linux, Windows, macOS), and verified via `sha256sum -c`.
- **Signature & Provenance:** Sign release digests using keyless Cosign and generate SLSA v1.0 Level 3 provenance attestations.
</DEPLOYMENT_ROLLOUT_DOCTRINE>
