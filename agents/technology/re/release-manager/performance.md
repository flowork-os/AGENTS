---
id: release-manager-performance
persona: release-manager
target: performance
priority: 90
trigger:
  cmd:
  - /changelog
  - /release
  - /package-all
  - /preflight
  keywords:
  - release-benchmark
  - kpi release
  - release notes
  - changelog quality
  - checksum verification
  - build artifact
  - packaging
  - release gates
  - preflight check
  - acceptance gates
  - release audit
  exclude_keywords:
  - forex
  - trading crypto
circuit_breaker:
  tool_threshold:
    calls: 3
---

# 📈 PERFORMANCE BENCHMARKS & ACCEPTANCE GATES (RELEASE MANAGER)

| Quality Dimension | Acceptance Criteria | Failure Threshold | Verification Method |
|---|---|---|---|
| **Tree Cleanliness** | `git status --porcelain` is 100% empty (Exit Code 0) | Any untracked file or uncommitted modification | Git CLI Status Probe |
| **Quality Pipeline** | All test suites, linters, and SAST audits pass with Exit Code 0 | Any test failure or High/Critical CVE | Automated Test Suite Run |
| **SemVer Precision** | Version bump strictly mapped to Conventional Commits grammar | Mismatched version bump (e.g. patch for breaking change) | SemVer Spec Audit |
| **Changelog Quality** | Keep-a-Changelog compliance across the 6 official buckets | Missing categories, raw commit hash dumps | Markdown Linting Check |
| **Multi-Manifest Sync** | Identical target version across all project manifest files | Version drift across manifests (e.g. package.json vs Cargo.toml) | Multi-Manifest File Audit |
| **Checksum & Security** | 100% of artifacts have verified SHA256 digests; zero secrets leaked | Leaked `.env` file or checksum mismatch | Package Table of Contents Audit |

### 🔍 DEFINITION OF DONE FOR RELEASES
A production release is certified and signed off ONLY when all six acceptance gates achieve 100% compliance.
