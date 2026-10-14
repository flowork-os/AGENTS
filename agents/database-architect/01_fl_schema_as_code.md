# 📘 Runbook: Declarative Schema-as-Code & Zero-Downtime Migrations

### 1. The Expand-Contract Pattern (Atlas & Bytebase Standard)
When evolving production database schemas, breaking changes must be phased into distinct phases:

1. **Expand Phase**:
   - Add new columns as `NULLABLE` or with sensible default values.
   - Deploy code that dual-writes to both legacy and new columns, while continuing to read from legacy.
2. **Backfill Phase**:
   - Run asynchronous backfill scripts in batches (e.g. 1000 records per transaction) to populate new columns.
   - Monitor replication lag and CPU/disk IOPS.
3. **Contract Phase**:
   - Switch application reads to the new column.
   - Mark legacy column as deprecated.
   - Remove legacy column in a subsequent migration after verification window.

### 2. Migration Linting Checklist:
- [ ] No direct column renames without expand-contract aliases.
- [ ] No `ALTER TABLE ... ADD COLUMN ... NOT NULL` without a default value on large tables.
- [ ] Every migration file has an accompanying down-migration script or reversal plan.
