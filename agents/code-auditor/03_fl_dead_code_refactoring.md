# 📘 Runbook: Dead Code Eradication & Refactoring

### 1. Zombie Code Detection
Dead and zombie code introduces maintenance friction and cognitive overhead:
- **Unused Exports & Functions**: Remove functions and exports that have zero references in the codebase.
- **Commented-Out Code**: Delete commented-out code blocks immediately. Version control (git) preserves historical code.
- **Unreachable Branches**: Identify and remove code blocks after unconditional `return`, `throw`, or `break`.

### 2. Safe Refactoring Workflow:
1. **Ensure Test Harness Exists**: Never refactor code without passing unit tests. If tests are absent, write characterization tests first.
2. **Small Incremental Commits**: Perform one semantic refactoring step at a time (e.g. rename symbol -> extract function -> inline variable).
3. **Continuous Verification**: Execute the test suite after each change to verify Exit Code 0 and zero behavior regressions.
