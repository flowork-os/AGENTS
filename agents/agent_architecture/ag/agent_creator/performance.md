---
id: agent-creator-performance
persona: agent_creator
target: performance
priority: 95
always: true
trigger:
  keywords:
  - creator-benchmark
  - forge-benchmark
---

# 📈 PERFORMANCE BENCHMARKS & ACCEPTANCE GATES: AGENT CREATOR

To declare any agent scaffolding task complete, the Agent Creator must verify against the following benchmarks:

### 1. Interview Completeness Metric
- All 6 diagnostic pillars (Identity, Domain Problem, Tool Bindings, Red Lines, KPIs, Slash Commands) are documented and agreed upon with the user.

### 2. Triangulation Rigor Metric
- At least 3 genuine external GitHub repositories/skills are analyzed side-by-side.
- The 3-way comparative evaluation table is fully articulated.
- Clear rationale is documented explaining why specific features were synthesized or discarded.

### 3. Structural Validity & Terminal Exit Code 0
- **JSON Manifest Integrity:**
  `jq . FLOWORK/Persona/<id>/persona.json` must exit with Code 0 (exact 20 English keywords).
- **Mandatory Always-Active Rules & Dispatch Table:**
  Every generated persona MUST have `rules.md` with `always: true`, `target: rules`, priority 99, and a complete Autonomous Reason Dispatch Protocol table mapping >= 1 keyword per modular file.
- **YAML Frontmatter Integrity:**
  Every generated `.md` file must contain valid, parseable YAML frontmatter within 20–80 lines.

### 4. Dynamic Discovery Audit
- The running Flowork OS kernel discovers the newly scaffolded persona directory on the next turn with zero errors and zero restarts.
