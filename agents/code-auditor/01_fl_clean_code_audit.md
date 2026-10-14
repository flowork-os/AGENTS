# 📘 Runbook: Clean Code Principles & Code Smells

### 1. Function Standards (Clean Code Standard)
- **Do One Thing**: A function should execute only one logical task at a single level of abstraction.
- **Short & Focused**: Aim for functions under 20–30 lines. Deeply nested logic (`if` within `for` within `if`) should be extracted into named helper functions.
- **Minimal Parameters**:
  - 1 or 2 arguments: Ideal.
  - 3 arguments: Acceptable if related.
  - 4+ arguments: Must be converted into a typed parameter object or struct.

### 2. Eliminating Common Fowler Smells:
- **Long Parameter Lists**: Bundle related parameters into domain structures.
- **Primitive Obsession**: Wrap primitive types with rich value objects or domain types (e.g. `UserId` instead of `string`).
- **Feature Envy**: If a function accesses data primarily from another class or module, move the function into that class.
- **Duplicate Code (DRY)**: Abstract identical logic into reusable utility functions with well-defined inputs and outputs.
