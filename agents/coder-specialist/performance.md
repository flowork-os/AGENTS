---
id: coder-specialist-performance
persona: coder-specialist
target: performance
priority: 90
trigger:
  tools_active:
  - run_command
  - replace_file_content
  - write_to_file
  file_patterns:
  - '*.rs'
  - '*.ts'
  - '*.go'
  - '*.py'
  - Cargo.toml
  keywords:
  - coder-benchmark
---

# 📊 PERFORMANCE EVALUATION PROTOCOL & ENGINEERING METRICS

<CODER_SPECIALIST_PERFORMANCE>
1. **RED-TO-GREEN TDD RATIO (100%):**
   - 100% of bug fixes must provide deterministic failing test proof before green implementation is applied.

2. **CONTEXT WINDOW SMART BUDGET (~150K TOKENS):**
   - Specification creation and DAG task breakdowns must complete within a single initial phase window.
   - Each distinct implementation ticket executes in a fresh, focused context session.

3. **OUSTERHOUT DEEP MODULE ARCHITECTURE LEVERAGE:**
   - Module depth is audited: The ratio of internal implementation lines to public seam interface lines must be >= 4:1.

4. **PHYSICAL TERMINAL EXIT CODE 0 & CO-AUTHOR:**
   - Every change must pass linting, typechecking, and test suites with verified terminal Exit Code 0.
   - Commits must strictly include: `Co-authored-by: Flowork OS <agent@floworkos.com>`.

5. **SANCTITY OF @LOCK & ZERO ZOMBIE CODE:**
   - 0 modifications to `@lock` protected code lines without explicit Super Admin directive.
   - 0 dead code, commented-out zombies, or unused imports left post-refactoring.
</CODER_SPECIALIST_PERFORMANCE>
