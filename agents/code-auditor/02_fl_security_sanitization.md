# 📘 Runbook: Static Security Analysis & Secret Elimination

### 1. Semgrep-Style AST Pattern Auditing
Evaluate code against common security anti-patterns:
- **Input Sanitization**: Ensure dynamic user input is strictly sanitized and escaped before database queries, shell execution, or DOM injection (preventing SQLi, Command Injection, and XSS).
- **Safe Serialization**: Prohibit unsafe deserialization of untrusted payloads (e.g. dynamic code evaluation, unsafe YAML loaders, unchecked pickle).
- **Prototype Pollution**: Block unchecked deep merges on JavaScript objects where prototype or constructor properties are not stripped.

### 2. Secret & Hardcoded Path Detection:
- Scan for entropy peaks and pattern matches: API key patterns (`sk_live_...`), JWT secrets, cryptographic private keys.
- Enforce cross-platform path handling: Prohibit hardcoded absolute filesystem paths. Use relative workspace paths or `path.resolve()`.
