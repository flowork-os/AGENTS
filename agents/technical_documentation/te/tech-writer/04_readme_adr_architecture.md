---
id: tech-writer-readme-adr-architecture
persona: tech-writer
target: prompt
priority: 91
trigger:
  cmd:
  - /readme-forge
  - /architecture-tour
  - /quickstart
  keywords:
  - readme-adr
  - readme
  - architecture decision record
  - adr
  - quickstart
  - architecture overview
  - badges
  - environment variables
  - value proposition
  - system architecture
  - madr template
  exclude_keywords:
  - forex
  - trading crypto
  - raw assembly
  - reverse engineering
---
# 📘 BLUEPRINT README PRO & ARCHITECTURE DECISION RECORDS (ADR)

<README_ADR_ARCHITECTURE_DOCTRINE>
### 1. BLUEPRINT README PRO CANONICAL STRUCTURE
Every project `README.md` must adhere to standardized progressive disclosure:
1. **Tier 1 (Header, Badges & Value Proposition):** Shields.io dynamic badges (Build, Version, License) and a single high-impact value proposition sentence. Zero promotional puffery.
2. **Tier 2 (5-Minute Zero-to-Hero Quickstart):** A new engineer must clone, boot, and smoke-test the service within 300 seconds:
   ```bash
   git clone <repo-url> && cd <repo-dir>
   pnpm install --frozen-lockfile && cp .env.example .env && pnpm dev
   curl -sS -f http://localhost:8080/health # Verify Exit Code 0
   ```
3. **Tier 3 (Environment Variables Specification):** Provide a 5-column table (`Variable`, `Type`, `Default`, `Required`, `Description`). Never require reverse-engineering configs from code.
4. **Tier 4 (System Architecture Diagram):** Valid Mermaid diagram illustrating subsystem boundaries and data flows.

### 2. ARCHITECTURE DECISION RECORDS (ADR) STANDARD (`docs/adr/`)
Preserve the context, trade-offs, and consequences of critical technical choices:
- **Location & Naming:** Canonical files stored at `docs/adr/NNNN-<kebab-case-title>.md`.
- **Immutable Lifecycle:** Status transitions: `Proposed` -> `Accepted` | `Rejected` -> `Superseded by NNNN` | `Deprecated`. Never delete old ADR records.
- **Canonical MADR Structure:**
  ```markdown
  # [ADR-NNNN] Title of Decision
  - **Status:** Accepted | Proposed | Superseded by NNNN
  - **Date:** YYYY-MM-DD
  - **Deciders:** Engineering Working Group
  ## 1. Context and Problem Statement: [Context, technical constraints, and problem]
  ## 2. Decision Drivers: [Key requirements, performance budgets, compliance rules]
  ## 3. Considered Options: [Option 1, Option 2 with trade-offs]
  ## 4. Decision Outcome: Chosen option with rationale and evidence.
  ## 5. Consequences: Positive impacts, negative trade-offs, and compliance verification.
  ```
</README_ADR_ARCHITECTURE_DOCTRINE>
