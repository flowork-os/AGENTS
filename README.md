# 🤖 Flowork OS Sovereign Agents

Official repository for **Flowork OS Sovereign Agents** ([floworkos.com](https://floworkos.com)).

Flowork OS decouples agent personas, reasoning styles, and operational prompts completely from the binary engine. All agents are 100% modular, plug-and-play, and operate under the **4-Layer Zero-Overlap Prompt Pyramid v3.0.0**.

---

## 🏛️ Modern Architecture Layout (v3.0.0)

Agents reside in flat, atomic directories under `agents/<agent-id>/`:

```
agents/
├── default/               # Universal Core Sovereign Engine & Master Orchestrator (CAT-015)
├── coder-specialist/      # Software Engineering & Deep Modules Craftsman (CAT-005)
├── code-auditor/          # Clean Code & Security Sanitization Reviewer (CAT-005)
├── database-architect/    # Database Architecture & Query Optimization Specialist (CAT-005)
├── api-integrator/        # Resilient Webhooks & API Integration Specialist (CAT-005)
├── qa-engineer/           # Quality Assurance & Playwright E2E Automation (CAT-005)
├── devops-engineer/       # Docker, K8s & Multi-OS CI/CD Infrastructure (CAT-005)
├── release-manager/       # SemVer Changelog & Rollout Release Gatekeeper (CAT-005)
├── uiux-designer/         # UI/UX & Flowork CSS Design System Architect (CAT-011)
├── product-manager/       # Product Discovery & DAG Task Graph Architect (CAT-007)
├── tech-writer/           # Diátaxis Framework & OpenAPI Technical Writer (CAT-005)
├── system/                # System Triggers & Operational Runbooks
├── SKILL.MD               # Master Operational Standard & 4-Layer Prompt Pyramid
└── trigger.md             # Sovereign Agent Router & Dispatch Specification
```

Each atomic agent directory adheres to:
- `agent.json` — Formal manifest with official `category_id`, tool permissions, and metadata
- `00_fl_identity.md` (or `00_identity.md`) — Foundational mental model & domain heuristics (<= 40 lines)
- `rules.md` — Lean reason dispatch table + negative guardrails (<= 40 lines)
- `performance.md` — Quantitative KPI benchmarks
- `01_...md`, `02_...md` — On-demand modular runbooks (0 token cost when inactive)

---

## ⚡ Zero-Token Fastly Delivery

- **Manifest**: `https://raw.githubusercontent.com/flowork-os/AGENTS/main/agents.json`
- **Tarball Stream**: `https://codeload.github.com/flowork-os/AGENTS/tar.gz/refs/heads/main`
- Zero GitHub API tokens or rate limits consumed during agent downloads.

---

## 📌 Pin & Unpin Commands

In the Flowork OS terminal or via LLM tool calls:
- Search: `agent_control(action: "search", query: "coder")`
- Pin: `agent_control(action: "pin", agent_id: "coder-specialist")`
- Unpin: `agent_control(action: "unpin")`

<!-- Co-authored-by: Flowork OS <agent@floworkos.com> -->
