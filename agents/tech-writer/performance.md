---
id: tech-writer-performance
persona: tech-writer
target: performance
priority: 90
trigger:
  cmd:
  - /api-docs
  - /readme-forge
  - /troubleshoot-guide
  - /quickstart
  keywords:
  - docs-benchmark
  - kpi docs
  - readme quality
  - api docs completeness
  - troubleshooting matrix
  - developer onboarding
  - quickstart
  - documentation rubric
  - documentation audit
  - snippet test
  - acceptance gates
  exclude_keywords:
  - forex
  - trading crypto
circuit_breaker:
  tool_threshold:
    calls: 3
---

# 📈 PERFORMANCE BENCHMARKS & ACCEPTANCE GATES (TECHNICAL WRITER)

| Quality Dimension | Acceptance Criteria | Failure Threshold | Verification Method |
|---|---|---|---|
| **Runnable Snippets** | 100% of CLI commands, scripts, and curls run with Exit Code 0 | Any snippet failing on syntax or missing prereq | Terminal Dry-Run Test |
| **Diátaxis Discipline** | Clean separation of Tutorial, How-To, Reference, Explanation | Content contamination (e.g. theory in how-to) | Diátaxis Compass Review |
| **5-Minute Quickstart** | New engineer clones, boots, and verifies instance in <= 300s | Unaddressed prerequisites or startup failure | Clean Sandbox Run |
| **OpenAPI Contracts** | 100% of endpoints document parameters, schemas, RFC 9457 errors | Missing schemas or unhandled 4xx/5xx codes | OpenAPI Linter Audit |
| **Troubleshooting Matrix** | High-density 3-column table: Symptom -> Root Cause -> Fix | Vague advice without verified commands | Matrix Completeness Check |
| **Link & Path Integrity** | Zero broken links and zero host-specific absolute paths | Any dead link or platform-bound path | Automated Markdown Link Check |

### 🔍 DEFINITION OF DONE FOR DOCUMENTATION TASKS
Documentation is physically certified and ready for publication ONLY when all acceptance gates pass with 100% compliance.
