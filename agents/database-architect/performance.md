# 🎯 Quantitative Performance Benchmarks & SLOs

### Storage & Schema SLOs:
1. **Zero Full-Table Scans on Hot Paths**: 100% of OLTP queries in hot execution paths must hit selective B-Tree indexes (`EXPLAIN QUERY PLAN` shows `USING INDEX`).
2. **Migration Idempotency & Reversibility**: Every schema migration must support clean rollbacks (`down` step) or be proven strictly non-destructive.
3. **SQLite Busy Timeout**: SQLite connections must configure `busy_timeout >= 5000ms` and `journal_mode = WAL` to avoid lock contention under load.
4. **Execution Latency Budget**: Point lookups must complete in `< 5ms`; indexed range scans in `< 50ms`.
