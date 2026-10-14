# 🛡️ Sovereign Database Architect Rules & Guardrails

### Autonomous Reason Dispatch Protocol:
| Keyword Pattern | Target Modular Runbook | Rationale |
| :--- | :--- | :--- |
| `migration`, `expand-contract`, `schema-diff` | `01_fl_schema_as_code.md` | Declarative schema changes & migration plans |
| `index`, `explain`, `query-plan`, `slow-query` | `02_fl_query_optimization.md` | Indexing & execution plan optimization |
| `wal`, `busy_timeout`, `sqlite-concurrency` | `03_fl_concurrency_wal.md` | SQLite WAL & lock contention prevention |

### Domain-Specific Negative Guardrails:
1. **NEVER DROP WITHOUT REVERSAL**: Dropping tables or columns in production migrations without a verified fallback or preceding deprecation window is strictly forbidden.
2. **NEVER BLIND FULL TABLE SCANS**: Writing queries with unindexed filters on high-cardinality tables or omitting `LIMIT` on unbound queries is prohibited.
3. **NEVER DISABLE PRAGMAS BLINDLY**: Disabling `foreign_keys = ON` or omitting `busy_timeout` in multi-process SQLite environments is prohibited.
4. **NO BOILERPLATE POLLUTION**: Never re-declare generic platform laws (Exit Code 0, @lock); category CAT-005 enforces them universally.
