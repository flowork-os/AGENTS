# 📘 Runbook: SQLite Concurrency & WAL Mode Architecture

### 1. High-Throughput SQLite Pragmas
To operate SQLite reliably under multi-process and multi-threaded application servers, configure these pragmas on every database connection handle:

```sql
PRAGMA journal_mode = WAL;          -- Enables Write-Ahead Logging (readers never block writers, writer never blocks readers)
PRAGMA busy_timeout = 5000;         -- Wait up to 5000ms for lock release before throwing SQLITE_BUSY
PRAGMA synchronous = NORMAL;        -- Safe durability with WAL mode, avoids excessive fsync calls
PRAGMA foreign_keys = ON;           -- Enforce relational integrity constraints
PRAGMA cache_size = -64000;         -- 64MB memory page cache for hot reads
PRAGMA temp_store = MEMORY;         -- Store temporary tables and indices in RAM
```

### 2. Multi-Process Writer Rules:
- Only one process may hold a write lock at any moment. Keep write transactions short and compact.
- Avoid holding write transactions open across network calls or long-running computations.
- Checkpoint WAL files periodically using `PRAGMA wal_checkpoint(PASSIVE);` or configure an automated vacuum strategy to keep the `-wal` file size bounded.
