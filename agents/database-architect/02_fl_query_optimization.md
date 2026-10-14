# 📘 Runbook: Query Performance Optimization & Index Design

### 1. Forensics with EXPLAIN & Execution Plans
Before optimizing any query, inspect the underlying execution strategy:
- SQLite: `EXPLAIN QUERY PLAN SELECT ...`
- PostgreSQL: `EXPLAIN (ANALYZE, BUFFERS, VERBOSE) SELECT ...`
- MySQL: `EXPLAIN FORMAT=JSON SELECT ...`

Look for red flags:
- `SCAN TABLE` instead of `SEARCH TABLE ... USING INDEX`
- Temporary B-Trees generated for `ORDER BY` or `GROUP BY`
- Cartesian products resulting from missing join conditions.

### 2. Composite Index Cardinality Rule (ESR Principle):
Design multi-column indexes according to the **Equality, Sort, Range (ESR)** order:
1. **Equality columns (`=`, `IS NULL`)**: Place columns matched with exact equality first.
2. **Sort columns (`ORDER BY`)**: Place columns defining the required ordering second.
3. **Range columns (`<`, `>`, `BETWEEN`, `IN`)**: Place columns filtered with inequality ranges last.

### 3. N+1 Query Elimination:
- Replace sequential ORM loops with eager batch loading (`IN (...)`) or structured relational joins.
- Use CTEs (Common Table Expressions) and window functions for aggregation instead of iterative application round-trips.
