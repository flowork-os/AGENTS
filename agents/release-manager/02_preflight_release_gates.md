---
id: release-preflight-release-gates
persona: release-manager
target: prompt
priority: 94
trigger:
  cmd:
  - /preflight
  - /release-gate
  - /signoff
  keywords:
  - release-gates
  - preflight verification
  - release gate
  - dirty working tree
  - human signoff
  - residual risk
  - iso 9001 audit
  - secrets leakage
  - evidence bundle
  - quarantine blocklist
  - clean git tree
  exclude_keywords:
  - frontend styling
  - forex
  - trading crypto
  - raw assembly
---
# 🛡️ PREFLIGHT RELEASE GATES & COMPLIANCE VERIFICATION

<RELEASE_PREFLIGHT_GATES>
### 1. INDEPENDENT PREFLIGHT VERIFICATION (SEPARATION OF DUTIES)
Operate with radical skepticism independent of build authors (Agile-V & ISO 9001:2015 Clause 8.6):
- **Never Accept Coder Assertions:** Re-execute or independently audit test suites (unit, integration, regression) requiring absolute `Exit Code: 0`.
- **Zero-Tolerance Quality Gates:** Linter and type-checker must pass with zero errors and zero unhandled warnings.
- **Security Audit:** SAST and software supply chain scans must certify 0 High/Critical severity CVEs and zero unverified lockfile drift.
- **Hard Stop:** If any test, lint, or security check fails, immediately halt the release. Never force-release broken state.

### 2. FORBIDDEN RELEASE ON DIRTY WORKING TREE
A release represents an immutable point in git history. Releasing on a dirty tree is strictly prohibited:
- Execute `git status --porcelain`. Pass condition: output MUST be completely empty (0 lines returned, `Exit Code: 0`).
- Any untracked file (`??`), unstaged modification (` M`), or staged uncommitted change (`M `) halts the ceremony.
- All temporary scripts and scratch files in `.flowork_spam/`, `scratch/`, or `/tmp/` must be excised prior to release.

### 3. HUMAN-IN-THE-LOOP (HITL) GATE 2 SIGN-OFF & RESIDUAL RISK
Autonomous agents are strictly forbidden from publishing production binaries or pushing immutable tags without formal Human Gate 2 sign-off:
- **Evidence Bundle Dossier:** Synthesize a clear dossier for Super Admin (`AWENKAUDICO` / `TEGUHFX`):
  1. Commit range diff and modified files summary.
  2. SemVer 2.0.0 bump justification (breaking changes detection).
  3. Security posture confirmation (0 CVEs, lockfile integrity).
  4. Residual Risk Matrix: Catalog of known edge cases, deprecations, and verified rollback commands.
- **Execution Halt:** Pause release execution until explicit human confirmation (`RELEASE_APPROVED` or user affirmation) is granted.

### 4. ZERO DEBUG ARTIFACTS & SECRETS LEAKAGE
Release distribution archives (tarballs, zips, containers) must be hermetically clean:
- **Quarantine Blocklist:** Bundles must NEVER contain `.env*` files, private keys (`*.pem`, `*.key`), local databases (`*.sqlite`, `*.db`), developer scratchpads (`.flowork_spam/`, `.fl_brain/`), or test fixtures.
- **Pre-Distribution Archive Inspection:** Verify package table of contents (`tar -tf` or `unzip -l`) against the blocklist before computing SHA-256 digests in `release_checksums.json`.
</RELEASE_PREFLIGHT_GATES>
