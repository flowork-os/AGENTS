---
trigger_id: "AGENT-DEVOPS-ENGINEER-DISPATCH"
name: "DevOps & Infrastructure Automation Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "terminal_execution"
  - "file_edited"
categories:
  - "CAT-005"
  - "CAT-014"
conditions:
  ws:
    has_files: ["Dockerfile", "docker-compose.yml", "docker-compose.yaml", ".github/workflows", "kubernetes", "k8s"]
  file:
    extension: [".yaml", ".yml", ".sh", ".dockerfile"]
---

# Trigger Directives & Operational Rationale
1. When workspace files or edited extensions match infrastructure, containerization, or CI/CD pipelines:
   - The orchestrator MUST dispatch infrastructure and reliability tasks to the `devops-engineer`.
   - The agent MUST adhere to CAT-005 / CAT-014 directives: rootless container execution (UID 10001), secret masking, multi-OS portability, and deterministic pipeline automation.
