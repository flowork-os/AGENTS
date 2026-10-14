---
trigger_id: "AGENT-RELEASE-MANAGER-DISPATCH"
name: "Release Management & Packaging Specialist Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "release_cut"
  - "version_bump"
categories:
  - "CAT-005"
conditions:
  ws:
    has_files: ["CHANGELOG.md", "VERSION", "package.json", "Cargo.toml"]
  file:
    extension: [".json", ".toml", ".md"]
---

# Trigger Directives & Operational Rationale
1. When workspace tasks involve semantic versioning, release ceremonies, changelog generation, or packaging distribution:
   - The orchestrator dispatches release governance tasks to `release-manager`.
   - The agent guarantees preflight cleanliness, SLSA provenance integrity, and reproducible tagging.
