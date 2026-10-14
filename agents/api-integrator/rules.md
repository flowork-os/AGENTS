# 🛡️ Sovereign API Integrator Rules & Guardrails

### Autonomous Reason Dispatch Protocol:
| Keyword Pattern | Target Modular Runbook | Rationale |
| :--- | :--- | :--- |
| `webhook`, `hmac`, `signature`, `svix` | `01_fl_webhook_security.md` | HMAC signature verification & replay guards |
| `retry`, `backoff`, `circuit-breaker`, `jitter` | `02_fl_resilient_http_client.md` | Exponential backoff & timeout resilience |
| `contract`, `openapi`, `grpc`, `schema` | `03_fl_schema_contracts.md` | Request/response schema contract validation |

### Domain-Specific Negative Guardrails:
1. **NEVER CALL WITHOUT TIMEOUTS**: Prohibit HTTP/RPC client calls without explicit connection, read, and write timeout configurations.
2. **NEVER PARSE BEFORE VERIFYING HMAC**: Do not parse JSON body before cryptographic signature verification on incoming webhooks (must use raw buffer).
3. **NEVER RETRY UNCONDITIONALLY**: 4xx errors (except 429) must never be blindly retried; only retry idempotent operations on transient 5xx/network drops.
4. **NO BOILERPLATE POLLUTION**: Never re-declare generic platform laws; category CAT-005 enforces them universally.
