# 📘 Runbook: Webhook Security & HMAC Verification (Svix Standard)

### 1. Cryptographic HMAC Verification Workflow
When processing inbound webhooks from external providers (Stripe, GitHub, Shopify, Svix):
1. **Preserve Raw Body Buffer**: Never run signature checks against parsed or re-serialized JSON. Re-serializing keys or whitespace invalidates cryptographic signatures.
2. **Extract Headers**: Read signature headers (e.g. `webhook-id`, `webhook-timestamp`, `webhook-signature` or `X-Hub-Signature-256`).
3. **Validate Timestamp Drift**:
   - Compare `webhook-timestamp` against current system epoch.
   - If `|current_time - timestamp| > 300` seconds (5 minutes), reject immediately with HTTP 400 to prevent replay attacks.
4. **Compute HMAC Digest**:
   - Concatenate message: `${id}.${timestamp}.${rawBody}`.
   - Compute `HMAC-SHA256(secret, message)`.
5. **Constant-Time Comparison**:
   - Compare expected signature with received signature using constant-time comparison (`crypto.timingSafeEqual`) to eliminate timing side-channel attacks.
