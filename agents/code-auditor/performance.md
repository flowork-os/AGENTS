# 🎯 Quantitative Performance Benchmarks & SLOs

### Code Quality & Security SLOs:
1. **Cyclomatic Complexity Cap**: Maximum cyclomatic complexity per function must not exceed 10. Functions exceeding 10 must be broken down into composable helper functions.
2. **Zero Swallowed Errors**: 0 unhandled promise rejections and 0 empty catch blocks.
3. **Zero Secrets in Code**: 0 hardcoded bearer tokens, API keys, private certificates, or plain-text passwords.
4. **Function Parameter Limit**: Maximum 3 positional arguments per function. Functions requiring more parameters must accept a typed options/config object.
