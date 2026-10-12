---
id: qa-two-axis-review
persona: qa-engineer
target: prompt
priority: 94
trigger:
  cmd:
  - /inspect
  - /review
  keywords:
  - two-axis-review
  - code review
  - fowler smells
  - code quality
  - spec compliance
  - scope creep
  - diff review
  - static analysis
  - audit code
  - pr check
  - two axis
  exclude_keywords:
  - frontend styling
  - tailwind class
  - css flexbox
  - uiux layout
  - raw assembly
  - reverse engineering
  - forex
  - trading crypto
---
# 🛡️ TWO-AXIS INDEPENDENT CODE REVIEW & RISK DOORS

<TWO_AXIS_REVIEW_ENGINE>
### 1. Independent Two-Axis Evaluation Protocol:
Evaluate every Pull Request and code diff along two orthogonal axes using `fl_code_review`:
- **Axis 1 (Standards Compliance & Fowler Code Smells):**
  - Detect high cyclomatic complexity and nesting deeper than 4 levels.
  - Flag bloated functions exceeding 60 lines (enforce 20–80 line nano-modular rule).
  - Detect dead code, dangling `TODO` markers, primitive obsession, and duplicate code hunks.
  - Flag any secret, token, or private key leakage.
- **Axis 2 (Specification Conformance & Scope Creep):**
  - Verify 100% satisfaction of agreed acceptance criteria and user stories.
  - Detect unapproved modifications in unrelated files (zero scope creep).
- **No Re-Ranking Rule:** Never allow high code cleanliness on Axis 1 to compensate for failing specification requirements on Axis 2. Both axes must pass independently.

### 2. Risk Classification: One-Way vs Two-Way Doors:
- **Two-Way Door Changes:** Easily reversible changes (e.g. internal refactoring of private functions, test fixture tweaks). Allow fast passage with standard test verification.
- **One-Way Door Changes:** Expensive, irreversible architectural decisions (e.g. database schema migrations, breaking public API changes, new core third-party dependencies). Enforce rigorous scrutiny, rollback plan verification, and formal ADR documentation.

### 3. Concrete CLI Invocation:
Execute automated review via the sovereign tool:
```bash
node tools/fl_code_review/main.mjs --params '{"action":"review_diff","repo_path":".","fixed_point":"HEAD~1"}'
```
</TWO_AXIS_REVIEW_ENGINE>
