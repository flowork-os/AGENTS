---
trigger_id: "SYS-TRIG-POST-EDIT"
name: "Post-Edit Compilation & Test Verification Directive"
scopes:
  - "specialist_group"
  - "default_solo"
events:
  - "file_edited"
categories:
  - "CAT-005"
---
<POST_EDIT_VERIFICATION_DIRECTIVE>
[CODEBASE MUTATION DETECTED: MANDATORY VERIFICATION]
1. IMMEDIATE SYNTAX AUDIT: Verify modified source files through terminal compiler or linter immediately.
2. EMPIRICAL PROOF: Do not report completion based on assumptions; verify with Exit Code 0 test runs.
3. LOCK PRESERVATION: Confirm no lines containing `@lock` or `@freez` were altered or removed.
</POST_EDIT_VERIFICATION_DIRECTIVE>
