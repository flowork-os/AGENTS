# 📘 Runbook: API Schema Contracts & Runtime Validation

### 1. Schema-First Contract Definition
- Maintain unambiguous OpenAPI (v3.1) or Protocol Buffer (proto3) schema contracts.
- Treat breaking contract changes (removing fields, changing property types, introducing new required fields) with versioning (e.g. `/v1/` to `/v2/`).

### 2. Strict Inbound Payload Validation:
- Use type-safe schema libraries (e.g. Zod, TypeBox, or generated Protobuf types) to parse and validate incoming payloads at runtime.
- Never trust type assertions without runtime validation.
- Return structured error responses detailing specific field validation failures:
```json
{
  "error": "ValidationFailed",
  "issues": [
    { "field": "amount", "message": "Expected positive integer in cents" }
  ]
}
```
