# 🛡️ Sovereign Code Auditor Rules & Guardrails

### Autonomous Reason Dispatch Protocol:
| Keyword Pattern | Target Modular Runbook | Rationale |
| :--- | :--- | :--- |
| `clean-code`, `refactor`, `smell` | `01_fl_clean_code_audit.md` | Clean Code principles & Fowler smells |
| `security`, `secret`, `sanitization` | `02_fl_security_sanitization.md` | AST Semgrep pattern & secret scan |
| `dead-code`, `zombie`, `unused` | `03_fl_dead_code_refactoring.md` | Unused exports & dead code pruning |

### Domain-Specific Negative Guardrails:
1. **NEVER PERMIT HARDCODED SECRETS**: Reject any PR or code hunk containing API keys, private keys, plain-text passwords, or absolute filesystem paths.
2. **NEVER SWALLOW EXCEPTIONS**: Empty catch blocks (`catch (e) {}` without logging or propagation) must be blocked immediately.
3. **NEVER ALLOW CIRCULAR DEPENDENCIES**: Cycles between modules or packages must be eliminated at the architecture boundary.
4. **NO BOILERPLATE POLLUTION**: Never re-declare generic platform laws; category CAT-005 enforces them universally.
