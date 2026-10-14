---
trigger_id: "SYS-TRIG-RISK-SAFETY"
name: "Destructive Command Safety Confirmation Directive"
scopes:
  - "universal_all"
internal_conditions:
  user_intent:
    matches_regex: "(?i)(drop table|rm -rf|format|delete database|production deploy|force push)"
---
<DESTRUCTIVE_OPERATION_SAFETY_DIRECTIVE>
[HIGH-RISK INTENT PATTERN DETECTED]
1. MANDATORY CONFIRMATION: Verify the exact target path, database name, or git branch with the operator prior to executing destructive operations.
2. BACKUP VERIFICATION: Inspect local backup state or git stash status before file deletion or schema migration.
3. DRY-RUN FIRST: When possible, execute simulation or dry-run flags (e.g. `--dry-run`, test migrations) before applying live mutations.
</DESTRUCTIVE_OPERATION_SAFETY_DIRECTIVE>
