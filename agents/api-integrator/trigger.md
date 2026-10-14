---
trigger_id: "AGENT-API-INTEGRATOR-DISPATCH"
name: "API Integration & Webhook Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "api_integration"
  - "file_edited"
  - "network_request"
categories:
  - "CAT-005"
conditions:
  ws:
    has_files: ["openapi.json", "openapi.yaml", "swagger.json", "*.proto"]
  file:
    extension: [".proto"]
---

# Trigger Directives & Operational Rationale
1. When workspace files or code modifications touch external APIs, HTTP clients, webhooks, or OpenAPI/gRPC schemas:
   - The orchestrator MUST dispatch integration tasks to the `api-integrator`.
   - The agent MUST configure resilient HTTP clients with exponential backoff and timeout budgets.
   - Enforce Svix-standard HMAC-SHA256 signature verification and timestamp replay protection on all webhook consumers.
