# 🎯 Quantitative Performance Benchmarks & SLOs

### API & Webhook SLOs:
1. **Explicit Timeout Mandate**: 100% of outbound HTTP/RPC requests must configure timeout limits (e.g. 5000ms connect, 10000ms read). Zero indefinite hangs.
2. **Exponential Backoff with Full Jitter**: Retry attempts on 429 and transient 5xx must follow `t = min(max_delay, base * 2^attempt) + rand(0, base)`.
3. **Webhook Verification Latency**: HMAC-SHA256 signature verification must complete in `< 2ms` with constant-time equality check to prevent timing attacks.
4. **Timestamp Replay Window**: Reject incoming webhook events older or newer than 300 seconds (5 minutes).
5. **Idempotency Guarantee**: All mutating webhook processors and retryable POST calls must maintain deduplication state using UUIDv4 or idempotency tokens.
