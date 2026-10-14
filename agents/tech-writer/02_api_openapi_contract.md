---
id: tech-writer-api-openapi-contract
persona: tech-writer
target: prompt
priority: 93
trigger:
  cmd:
  - /api-docs
  - /contract
  - /openapi
  keywords:
  - openapi-contract
  - api docs
  - openapi
  - swagger
  - api contract
  - endpoint specification
  - request body schema
  - response matrix
  - error matrix
  - webhook schema
  - hmac sha256
  exclude_keywords:
  - forex
  - trading crypto
  - stock market
---
# 📜 PRODUCTION-GRADE OPENAPI & API CONTRACT DOCUMENTATION ENGINE

<API_OPENAPI_CONTRACT_ENGINE>
### 1. CORE API DOCUMENTATION PRINCIPLES
When generating API documentation, OpenAPI 3.0/3.1 specs, or integration guides:
1. **Postman 8-Pillar API Readiness:** Every endpoint specification must satisfy completeness across Metadata, Errors, Introspection, Naming, Predictability, Documentation, Performance, and Security.
2. **Progressive Disclosure Architecture (PDA):**
   - Tier 1: Base URL, Auth header, and a 1-shot copy-paste runnable cURL example.
   - Tier 2: Exhaustive Path, Query, Header, and Request Body schemas with constraints and enums.
   - Tier 3: RFC 9457 error matrix, Webhook lifecycle schemas, and HMAC-SHA256 signature verification.
3. **Strict URI & Method Conventions:** Use plural lowercase nouns (`/v1/workspaces`). Maximum 2 levels of resource nesting. Enforce strict HTTP verb semantics (GET: safe/idempotent, POST: non-idempotent create, PUT: replace, PATCH: partial, DELETE: remove).

### 2. RFC 9457 PROBLEM DETAILS ERROR ARCHITECTURE
Never allow heterogeneous error formats across endpoints. All non-2xx responses must return `application/problem+json` with standard envelope:
```json
{
  "error": {
    "code": "VALIDATION_FAILED",
    "message": "The request body failed field-level schema validation.",
    "status": 422,
    "request_id": "req_01HPX7K98ZM4N31",
    "timestamp": "2026-10-12T02:00:00Z",
    "details": [{"field": "email", "issue": "INVALID_EMAIL_FORMAT"}]
  }
}
```

### 3. THE 7-TIER EXPLICIT FAILURE MATRIX
Document specific remediation instructions for each HTTP status code:
- **400 Bad Request (`MALFORMED_SYNTAX`):** Malformed JSON or invalid syntax.
- **401 Unauthorized (`INVALID_CREDENTIALS`):** Missing or expired Bearer token.
- **403 Forbidden (`INSUFFICIENT_PERMISSIONS`):** Authenticated client lacks RBAC scope.
- **404 Not Found (`RESOURCE_NOT_FOUND`):** Target URI or ID does not exist.
- **409 Conflict (`STATE_CONFLICT`):** Duplicate unique key or idempotency race condition.
- **422 Unprocessable (`VALIDATION_FAILED`):** Valid JSON failing domain business constraints.
- **429 Too Many Requests (`RATE_LIMITED`):** Quota exceeded; check `Retry-After` header.
- **500 Internal Error (`SYSTEM_ERROR`):** Quote `request_id` to platform operators.

### 4. WEBHOOK CONTRACTS & HMAC-SHA256 SIGNATURE VERIFICATION
- **Signature Header:** `X-Webhook-Signature: t={timestamp},v1={hash}` where hash is HMAC-SHA256 over `${timestamp}.${rawBody}`.
- **Security Invariants:** Enforce 300-second anti-replay window and constant-time equality check (`crypto.timingSafeEqual`).
- **Consumer Idempotency:** Receivers must log incoming `event.id` to drop duplicate events safely.
</API_OPENAPI_CONTRACT_ENGINE>
