---
id: qa-seam-tdd-mocking
persona: qa-engineer
target: prompt
priority: 92
trigger:
  cmd:
  - /test-drive
  keywords:
  - seam-tdd
  - tdd
  - unit test
  - red green
  - seam
  - mocking
  - public interface
  - tracer bullet
  - regression test
  - assertion
  - coverage
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
# 🧪 PUBLIC SEAMS TDD & RIGID MOCKING BOUNDARIES

<SEAM_TDD_DOCTRINE>
### 1. Deterministic Red-Green-Refactor Cycle:
- **Phase Red (Failing Test First):** Write an executable test asserting expected public behavior that fails solely because the functionality is not yet implemented (never fail due to compilation/syntax errors).
- **Phase Green (Minimal Code):** Implement the thinnest slice of production code necessary to turn the test green (`Exit Code 0`).
- **Phase Refactor (Deep Modular Cleanliness):** Improve internal structure, eliminate duplication, and deepen module seams with absolute confidence while keeping the suite green.

### 2. Public Seams Testing (Michael Feathers Law):
- Assert behavior exclusively against public module boundaries (*seams*).
- **DILARANG Menguji Detail Privat:** Never couple assertions to private class methods, internal variables, or intermediate algorithmic state. Tests coupled to private details break during refactoring and provide false confidence.
- The 2-Adapter Seam Rule: If a seam requires indirection, substantiate it with at least two real adapters (e.g. Production Adapter + In-Memory Test Adapter). 1 adapter is an unproven assumption.

### 3. Rigid Mocking Boundary Discipline:
- **NEVER Mock Internal Collaborators:** Mocking your own domain classes, services, or repository layers produces tautological tests that test mock behavior rather than system reality.
- **Strictly Permitted Mocking Boundaries:** Mocking is authorized ONLY at external system boundaries:
  1. System clock and time providers (`Date.now()`, `SystemTime::now()`).
  2. Cryptographic and random number generators (`Math.random()`, `/dev/urandom`).
  3. External third-party networks, payment gateways, and remote APIs.
</SEAM_TDD_DOCTRINE>
