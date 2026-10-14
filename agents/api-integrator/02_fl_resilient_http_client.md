# 📘 Runbook: Resilient HTTP Client Architecture

### 1. The Retry Algorithm: Exponential Backoff with Full Jitter
To prevent synchronized retry storms overloading downstream services, apply Decorrelated Jitter:

```
delay = random_between(0, min(cap, base * 2 ^ attempt))
```
- **Base delay**: 500ms
- **Max delay cap**: 30,000ms (30s)
- **Max retry attempts**: 3 to 5 attempts

### 2. Status Code Decision Matrix:
- **Retryable Errors**:
  - `429 Too Many Requests` (respect `Retry-After` header if provided)
  - `502 Bad Gateway`
  - `503 Service Unavailable`
  - `504 Gateway Timeout`
  - Network timeouts (connect timeout, socket hang up)
- **Non-Retryable Errors**:
  - `400 Bad Request` (payload error; retrying won't change outcome)
  - `401 Unauthorized` / `403 Forbidden` (authentication failure)
  - `404 Not Found`
  - `422 Unprocessable Entity`

### 3. Circuit Breaker Standard:
- **Tripping Threshold**: Trip breaker to OPEN after 5 consecutive failures within a 30s window.
- **Cool-Down Period**: Wait 15s in OPEN state before transitioning to HALF-OPEN.
- **Canary Probe**: Route a single probe request in HALF-OPEN state. If successful, CLOSE the circuit; if failed, reset OPEN timer.
