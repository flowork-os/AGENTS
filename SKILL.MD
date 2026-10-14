---
name: agent-trigger-architecture
title: Flowork OS Sovereign Agent Trigger Architecture & Zero-Bloat Operational Standard
version: 3.0.0
description: Comprehensive operational guide and standard specification for configuring, scoping, and orchestrating trigger-based modular agents outside the binary kernel with zero prompt bloat.
keywords:
  - agents
  - triggers
  - manifest
  - hotreload
  - modular
  - sovereign
  - lifecycle
  - slashcommands
  - injection
  - autocomplete
  - guardrails
  - privilege
  - multiagent
  - orchestration
  - rules
  - dispatch
  - performance
  - autonomy
  - taxonomy
  - department
---

# 🏛️ FLOWORK OS SOVEREIGN AGENT TRIGGER ARCHITECTURE & ZERO-BLOAT OPERATIONAL STANDARD

> **Micro-Kernel Principle:** *The compiled binary is an immutable Level 0 Kernel ("Empty Board"). All dynamic agents, contextual runbooks, and trigger rules live 100% outside the binary on disk (`<engine_root>/agents/`), hot-reloading in real time without recompilation.*

---

## 📌 1. Fundamental Architecture & The 4-Layer Zero-Overlap Prompt Pyramid

In Flowork OS, prompts **MUST NEVER SUFFER FROM REDUNDANT BLOAT OR COGNITIVE OVERLAP**. When system base prompts, category quality controls, and agent persona files repeat the same instructions, LLM context windows degrade, latency spikes, and attention dilution impairs execution.

To guarantee pristine precision and absolute zero prompt bloat, Flowork OS enforces the **4-Layer Zero-Overlap Prompt Pyramid**:

```
┌────────────────────────────────────────────────────────────────────────┐
│ LAYER 0: BASE PROMPT (Kernel Invariant - Rust Runtime Managed)         │
│ • Source Files : promp_solo_spesialis.md / promp_team_spesialis.md    │
│ • Governance   : Platform identity, anti-jailbreak, anti-yesman ethics,│
│                  active workspace boundaries ({effective_ws}),        │
│                  permanent memory (.fl_brain/), scratch (.FL_BIN/),    │
│                  git commit co-authoring mandate.                      │
│ 🚨 AGENT LAW   : STRICTLY FORBIDDEN TO DUPLICATE LAYER 0 IN ANY AGENT! │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
┌───────────────────────────────────▼────────────────────────────────────┐
│ LAYER 1: JIT CATEGORY DIRECTIVES (Department Quality Gate - Auto JIT)  │
│ • Source Files : SYSTEM/categories/CAT-XXX.md (24 Specialist Cats)     │
│ • Governance   : Universal professional standards per category:        │
│                  CAT-005 (Tech): Terminal Exit Code 0, diff review,    │
│                  @lock/@freez sanctity, zombie process/code cleanup.   │
│                  CAT-011 (Design): flow_screenshot UI inspection,      │
│                  design tokens, WCAG AA, strict English UI text.       │
│                  CAT-003 (Legal): JDIH statutory research, anti-fable. │
│ 🚨 AGENT LAW   : STRICTLY FORBIDDEN TO RE-DECLARE GENERIC QC LAWS!     │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
┌───────────────────────────────────▼────────────────────────────────────┐
│ LAYER 2: AGENT IDENTITY & DISPATCH GATE (Always Active: 00_id + rules) │
│ • Source Files : <engine_root>/agents/<id>/00_identity.md & rules.md   │
│ • 00_identity  : PURE mental models, domain intuition & role traits.   │
│                  (Budget: Strict Cap <= 40 lines / 300 tokens).        │
│ • rules.md     : PURE Reason Dispatch Table + Role Negative Guardrails.│
│                  (Budget: Strict Cap <= 40 lines / 300 tokens).        │
│ 🚨 EFFICIENCY  : TOTAL LAYER 2 LOAD MUST REMAIN UNDER 600 TOKENS!      │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │
┌───────────────────────────────────▼────────────────────────────────────┐
│ LAYER 3: ON-DEMAND MODULAR RUNBOOKS (0 Token When Inactive)            │
│ • Source Files : <engine_root>/agents/<id>/01_xxx.md, performance.md   │
│ • Governance   : Deep, step-by-step procedures triggered JIT via tool  │
│                  reason dispatch, slash commands, or file patterns.    │
│ • Efficiency   : Inactive runbooks consume exactly 0 context tokens.   │
└────────────────────────────────────────────────────────────────────────┘
```

---

## 📂 2. Standard Directory Layout (Atomic & Lean Multi-Prompt Architecture)

Every sovereign agent adheres to an atomic, modular directory structure residing strictly within the **Flowork Engine Body** (`<engine_root>/agents/`), NEVER inside a user's workspace directory:

```
<engine_root>/agents/<agent-id>/
├── agent.json                     # Birth certificate, category_id, tools, file patterns & slash commands
├── rules.md                       # Lean Dispatch Table & Role-Specific Negative Guardrails (always: true, priority: 99)
├── 00_identity.md                 # Foundational mental models & domain intuition (always: true, priority: 100)
├── performance.md                 # Role-specific quantitative KPI benchmarks (target: performance, on-demand)
├── 01_domain_module_a.md          # Modular domain runbook A (e.g. 01_docker_hardening.md)
├── 02_domain_module_b.md          # Modular domain runbook B (e.g. 02_k8s_sre_triage.md)
├── 03_domain_module_c.md          # Modular domain runbook C (e.g. 03_cicd_pipeline.md)
└── 04_domain_module_d.md          # Modular domain runbook D (e.g. 04_multi_os_portability.md)
```

### Invariant Architectural Mandates:
1. **Lean Dispatch Gate (`rules.md`):**
   `rules.md` is loaded on **every turn** (`always: true`, `target: rules`, `priority: 99`). It **MUST NEVER** copy-paste generic platform rules (no Exit Code 0 boilerplate, no @lock boilerplate, no multi-OS boilerplate). It **MUST ONLY** contain:
   - The **Autonomous Reason Dispatch Protocol Table** (mapping canonical keywords to modular runbooks).
   - **Role-Specific Negative Guardrails** (explicit operational limits unique to that role).
   - Total file size MUST remain under 40 lines (~300 tokens).
2. **Pristine Domain Persona (`00_identity.md`):**
   `00_identity.md` is loaded on **every turn** (`always: true`, `target: prompt`, `priority: 100`). It **MUST NEVER** repeat platform flattery or creator subservience (handled by Layer 0). It **MUST ONLY** define the specialist's core mindset, domain intuition, and analytical heuristic. Total size MUST remain under 40 lines (~300 tokens).
3. **Role-Specific Performance Rubrics (`performance.md`):**
   Defines quantitative KPI benchmarks specific to the agent's deliverables (e.g. "Docker image size < 50MB", "E2E test suite runtime < 60s"). Triggered on-demand during `/verify` or verification gates, avoiding wasteful per-turn injection.
4. **Multi-Prompt Injection Guarantee:**
   When multiple modular prompts match active triggers simultaneously (e.g. `00_identity.md` via `always: true`, `01_docker_hardening.md` via keyword dispatch, and `performance.md` via threshold), the Flowork Engine injects ALL matching prompts into context, preserving priority order without artificial 1-prompt caps.

---

## ⚙️ 3. Agent Manifest Specification (`agent.json`)

The `agent.json` manifest acts as the **Birth Certificate & Employment Contract** for the agent. It strictly binds metadata, the official 25-category taxonomy, desk positioning, default mounted tools, agent-scoped slash commands, and dynamic trigger rules:

```json
{
  "id": "coder-specialist",
  "name": "Sovereign Coder Specialist & Systems Craftsman",
  "agent_id": "agent-coder-specialist-01",
  "department": "technology",
  "category_id": "CAT-005",
  "category": "technology",
  "desk_preference": {
    "zone": "Engineering Pod",
    "desk_id": "desk-coder-specialist"
  },
  "description": "Senior software engineering agent specialized in clean architecture, deep module design, and zero-defect systems.",
  "priority": 95,
  "pinned_model": {
    "model_id": "gemini-3.8-flash-high",
    "provider": "google",
    "enforce_lock": false
  },
  "pinned_account": {
    "account_id": "combo",
    "pool_strategy": "combo"
  },
  "default_tools": [
    "run_command",
    "view_file",
    "write_to_file",
    "replace_file_content",
    "ask_question",
    "brain_control"
  ],
  "slash_commands": [
    {
      "command": "/verify",
      "description": "Physical terminal Exit Code 0 verification before task completion",
      "icon": "✅"
    },
    {
      "command": "/investigate",
      "description": "Reproduce-first root-cause diagnostic loop for complex bugs & crashes",
      "icon": "🔍"
    },
    {
      "command": "/test-drive",
      "description": "Red-Green test-first development cycle on public interfaces",
      "icon": "🧪"
    },
    {
      "command": "/inspect",
      "description": "Self-code audit, dead-code elimination, and git co-author check",
      "icon": "🛡️"
    },
    {
      "command": "/sharpen",
      "description": "Interactive deep interview to sharpen system design before coding",
      "icon": "🔥"
    },
    {
      "command": "/forge-tool",
      "description": "Scaffold a new precision 1File1Logic tool if missing from catalog",
      "icon": "🛠️"
    },
    {
      "command": "/purge",
      "description": "Clean transient trash in .FL_BIN/scratch/",
      "icon": "🧹"
    },
    {
      "command": "/plan",
      "description": "Structured architecture blueprint and task checklist before implementation",
      "icon": "📋"
    },
    {
      "command": "/goal",
      "description": "Autonomous long-running task execution without stopping until goal is achieved",
      "icon": "🎯"
    },
    {
      "command": "/boost",
      "description": "Deep thinking mode with multi-perspective architectural review",
      "icon": "⚡"
    },
    {
      "command": "/learn",
      "description": "Crystallize permanent user decisions & preferences into .fl_brain/",
      "icon": "🧠"
    },
    {
      "command": "/browser",
      "description": "Interactive stealth web browsing & perimeter automation",
      "icon": "🌐"
    },
    {
      "command": "/schedule",
      "description": "Schedule a one-time timer or recurring cron job",
      "icon": "⏰"
    }
  ],
  "file_patterns": ["*.rs", "*.go", "*.ts", "*.js", "*.py", "Cargo.toml", "package.json"],
  "keywords": [
    "refactor", "compiler", "architecture", "tdd", "algorithm",
    "backend", "frontend", "concurrency", "async", "profiling"
  ],
  "exclude_keywords": ["docker", "k8s", "terraform", "helm", "devops", "marketing"],
  "triggers": [
    {
      "id": "terminal_error_guard",
      "description": "Triggered when terminal execution yields non-zero exit code or compiler errors",
      "enabled": true,
      "priority": 95,
      "conditions": {
        "exit_code": { "operator": "!=", "value": 0 },
        "output_contains": ["error", "panic", "fatal", "FAILED"]
      },
      "inject_file": "04_fl_diagnostics_tight_loop.md"
    }
  ]
}
```

### Slash Commands Configuration Rules:
1. **Strict Agent Scoping:** Slash commands registered in `agent.json` are hermetically sealed to that agent. Switching active chat agent dynamically swaps the available slash commands catalog without cross-session bleeding.
2. **Default Agent Rule (Zero Slash Commands):** The `default` (Core Engine) agent has `slash_commands: []`. It exposes NO external slash commands.
3. **Sovereign Command Naming Doctrine:**
   Legacy repository command names are strictly forbidden across Flowork OS. All agents must use sovereign commands:
   - ❌ Forbidden: `/diagnose` ➔ ✅ Sovereign: `/investigate`
   - ❌ Forbidden: `/tdd` ➔ ✅ Sovereign: `/test-drive`
   - ❌ Forbidden: `/qc` ➔ ✅ Sovereign: `/verify`
   - ❌ Forbidden: `/audit` ➔ ✅ Sovereign: `/inspect`
   - ❌ Forbidden: `/tool_maker` ➔ ✅ Sovereign: `/forge-tool`
   - ❌ Forbidden: `/grill-me` ➔ ✅ Sovereign: `/sharpen`
   - ❌ Forbidden: `/clean` ➔ ✅ Sovereign: `/purge`
   - Standard Core Suite: `/plan`, `/goal`, `/boost`, `/learn`, `/browser`, `/schedule`.

---

## 🏢 4. Dual-Tier Scalability Architecture: Session Locking vs. 25-Category Registry

A foundational architectural distinction governs how Flowork OS scales to thousands of specialized agents across 25 official specialist categories:

```
                   ┌───────────────────────────────────────────────┐
                   │    TIER 2: 25-CATEGORY TAXONOMY REGISTRY     │
                   │ (Pre-Session UI, 3D Clustering & JIT Routing) │
                   └───────────────────────┬───────────────────────┘
                                           │
                        User Selects / Auto-Routes Agent
                                           │
                                           ▼
                   ┌───────────────────────────────────────────────┐
                   │   TIER 1: IN-SESSION HERMETIC ISOLATION LOCK   │
                   │  `chat_id` -> `agent_id` -> `model` -> `dock` │
                   └───────────────────────────────────────────────┘
```

### Tier 1: In-Session Hermetic Isolation (`chat_id` Lock)
* **Binding Relationship:** `chat_id` ➔ `agent_id` ➔ `pinned_model` ➔ `pinned_account` ➔ `agent directory`.
* **Runtime Isolation:** Once a chat session is initiated, the engine executes within strict hermetic isolation. The runtime operates in $O(1)$ memory lookup, evaluating triggers and modular files **exclusively from that locked agent's directory**.
* **Zero Cross-Agent Contamination:** A chat locked to `coder-specialist` will never be contaminated by financial SMC rules, legal statutory guides, or medical triage protocols.

### Tier 2: 25-Category Taxonomy Registry
Flowork OS organizes all specialist agents under **25 Official Categories (`CAT-001` through `CAT-025`)**:
1. `CAT-001`: Healthcare (`CAT-001_healthcare.md`)
2. `CAT-002`: Psychology (`CAT-002_psychology.md`)
3. `CAT-003`: Legal (`CAT-003_legal.md`)
4. `CAT-004`: Education (`CAT-004_education.md`)
5. `CAT-005`: Technology (`CAT-005_technology.md`)
6. `CAT-006`: Finance (`CAT-006_finance.md`)
7. `CAT-007`: Business (`CAT-007_business.md`)
8. `CAT-008`: Marketing (`CAT-008_marketing.md`)
9. `CAT-009`: Advertising (`CAT-009_advertising.md`)
10. `CAT-010`: Media Creative (`CAT-010_media_creative.md`)
11. `CAT-011`: Design (`CAT-011_design.md`)
12. `CAT-012`: Human Resources (`CAT-012_human_resources.md`)
13. `CAT-013`: Science Research (`CAT-013_science_research.md`)
14. `CAT-014`: Automation & Admin (`CAT-014_automation_admin.md`)
15. `CAT-015`: Universal Core System (Agent Default / Mr. Flow - No Category Directive)
16. `CAT-016`: Arts, Music & Poetry (`CAT-016_arts_music_poetry.md`)
17. `CAT-017`: Metaphysics & Feng Shui (`CAT-017_metaphysics_fengshui.md`)
18. `CAT-018`: Architecture & Spatial (`CAT-018_architecture_spatial.md`)
19. `CAT-019`: Culinary & Gastronomy (`CAT-019_culinary_gastronomy.md`)
20. `CAT-020`: Sports & Athletics (`CAT-020_sports_athletics.md`)
21. `CAT-021`: Agriculture & Ecology (`CAT-021_agriculture_ecology.md`)
22. `CAT-022`: Diplomacy & Negotiation (`CAT-022_diplomacy_negotiation.md`)
23. `CAT-023`: Cybersecurity & Forensics (`CAT-023_cybersecurity_forensics.md`)
24. `CAT-024`: Hospitality & Tourism (`CAT-024_hospitality_tourism.md`)
25. `CAT-025`: Maritime & Logistics (`CAT-025_maritime_logistics.md`)

---

## ⌨️ 5. Agent-Locked Slash Commands & Autocomplete Engine

To maximize discoverability and operational speed, Flowork OS features a real-time, agent-locked slash command autocomplete palette directly in the chat composer (`#rightbar-chat-input`).

### A. Autocomplete Activation & Lifecycle
1. **Trigger Condition:** User types a forward slash (`/`) at the start of a prompt or immediately following whitespace.
2. **Scope Resolution:**
   - The engine checks `getActiveAgentSlashCommands()` for the current chat session.
   - If `currentAgent.id === 'default'` or the agent's `slash_commands` array is empty, the palette remains closed (`closeSlashPalette()`), allowing clean typing of directory paths without popup annoyance.
   - If `slash_commands` are declared, the glassmorphic palette opens above the composer.
3. **Real-Time Substring Filtering:**
   - As the user types characters following the slash (e.g. `/tes`), the palette performs case-insensitive substring matching against both `command` (e.g. `/test-drive`) and `description`.
   - If no commands match the filter query, the palette automatically closes.

### B. Pointer & Keyboard Interaction Architecture
* **Mouse / Pointer Selection:**
  - `mousedown` with `e.preventDefault()`: Intercepts the click before textarea blur can fire, instantaneously selecting the command without losing focus.
  - Hover / `mouseover`: Updates CSS `.selected` highlights **without rebuilding DOM (`innerHTML`)**. This eliminates DOM thrashing and prevents click events from being canceled by mouse movements.
  - `onclick`: Provides a redundant fallback ensuring reliable selection across touch and mobile screens.
* **Keyboard Navigation:**
  - `ArrowDown` / `ArrowUp`: Cycles the selected command index and scrolls the item into view.
  - `Enter` / `Tab`: Applies the selected command, automatically appending a trailing space (`/verify `), positions the cursor at the end, and closes the palette.
  - `Escape`: Closes the palette immediately.

---

## ⚡ 6. Modular Trigger Dimensions & Frontmatter Specification

Every modular prompt markdown file in `agents/<agent-id>/*.md` specifies runtime activation rules via YAML frontmatter:

### 1. Baseline Always-Active (`always: true`)
- **Purpose:** Guaranteed presence for core identities (`00_identity.md`) and invariant operating laws (`rules.md`) across every single turn.
- **Syntax:**
  ```yaml
  always: true
  ```
- **Strict Anti-Bloat Mandate:** Only `00_identity.md` and `rules.md` may use `always: true`. Modular runbooks and performance rubrics MUST NEVER use `always: true`!

### 2. Command & CLI Execution (`cmd` / `commands`)
- **Syntax:**
  ```yaml
  trigger:
    cmd: ["/verify", "cargo test", "npm test", "git commit"]
  ```
- **Engine Logic:** Case-insensitive substring matching against user input or command line.

### 3. Active & Mounted Tools (`tools_active`)
- **Syntax:**
  ```yaml
  trigger:
    tools_active: ["run_command", "view_file"]
  ```

### 4. Tool Stalled Circuit Breaker (`tool_stalled`)
- **Syntax:**
  ```yaml
  trigger:
    tool_stalled:
      tool: "run_command"
      consecutive_failures: 2
  ```

### 5. Tool Usage Threshold (`tool_threshold`)
- **Syntax:**
  ```yaml
  trigger:
    tool_threshold:
      tool: "run_command"
      min_calls: 3
  ```

### 6. Workspace File Patterns (`file_patterns`)
- **Syntax:**
  ```yaml
  trigger:
    file_patterns: ["*.rs", "*.go", "*.ts", "*.py", "Cargo.toml"]
  ```

### 7. Conversation Turn Budget Window (`turn_range`)
- **Syntax:**
  ```yaml
  trigger:
    turn_range:
      min_turn: 1
      max_turn: 3
  ```

---

## 🚀 7. Multi-Prompt Modular Injection Engine

Unlike monolithic architectures that force a single rigid prompt onto the agent, Flowork OS implements **Composite Multi-Prompt Injection**:

```
                 [ USER INPUT / CONTEXT TELEMETRY ]
                                 │
           ┌─────────────────────┴─────────────────────┐
           ▼                                           ▼
 [ Always-Active Prompts ]                   [ Dynamic Triggers ]
  • 00_identity.md (prio 100)                 • 03_cicd_pipeline.md (cmd: "git commit")
  • rules.md (prio 99)                        • 02_k8s_sre_triage.md (tool_stalled: 2)
           │                                           │
           └─────────────────────┬─────────────────────┘
                                 │
                    [ Filter & Disqualify ]
                  (exclude_keywords evaluation)
                                 │
                     [ Multi-Match Collector ]
                     (All matched docs collected)
                                 │
                     [ Priority-Sorted Queue ]
                   (Sorted descending by priority)
                                 │
                    [ Typed XML Composition ]
         ┌───────────────────────┼───────────────────────┐
         ▼                       ▼                       ▼
<ACTIVE_SOVEREIGN_AGENT>  <SOVEREIGN_AGENT_RULES>  <SOVEREIGN_AGENT_PERFORMANCE>
(00_identity + modules)     (rules.md + guardrails)    (performance.md KPI gates)
```

### Key Multi-Prompt Guarantees:
1. **Simultaneous Injection:** When multiple modular prompts match active triggers, all matching prompts are injected into context in priority-sorted order.
2. **Contextual Isolation via XML Enclaves:**
   - `<ACTIVE_SOVEREIGN_AGENT>` for role identity and modular doctrines (`target: prompt`).
   - `<SOVEREIGN_AGENT_RULES>` for dispatch table and role guardrails (`target: rules`).
   - `<SOVEREIGN_AGENT_PERFORMANCE>` for KPI rubrics (`target: performance`).
3. **Token Efficiency:** Inactive modules consume exactly 0 tokens.

---

## 🧠 8. Autonomous Reason Dispatch Protocol & Self-Chaining

### The Autonomy Problem
In autonomous workflows (e.g. running `/goal` pipelines, background subagents, or automated builds), agents execute multi-turn loops without manual user prompting. Relying on user prompts or slash commands to trigger modular runbooks fails because no user is present to type `/dockerize` on turn 5.

### The Solution: Autonomous Reason Dispatch
Flowork OS solves this via the **Autonomous Reason Dispatch Protocol**:
1. **Invariant Dispatch Gate (`rules.md`):** Loaded on every turn (`always: true`, `priority: 99`). Defines the dispatch table mapping canonical keywords to modular runbooks.
2. **Self-Chaining via Tool Metadata:** When the agent calls any tool, it includes the canonical keyword inside `toolAction` and `toolSummary`.
3. **Tool Intercept Gate Evaluation:** Before the next model turn begins, the Flowork Engine scans the emitted tool action/summary.
4. **Autonomous Modular Awakening:** When the engine detects a canonical keyword (e.g., `docker-hardening`), it immediately injects `01_docker_hardening.md` into the agent's context for the subsequent turn.

### Canonical Dispatch Matrix Example (`rules.md`):
```markdown
<REASON_DISPATCH_TABLE>
| Canonical Keyword | Target Modular File | Trigger Context |
| :--- | :--- | :--- |
| `docker-hardening` | `01_docker_hardening.md` | Multi-stage build, rootless UID 10001, secret mounts |
| `k8s-triage`       | `02_k8s_sre_triage.md`   | CrashLoopBackOff, OOMKilled, pod diagnostics |
| `cicd-pipeline`    | `03_cicd_pipeline.md`    | GitHub Actions workflow hardening, SHA pinning |
| `cross-platform`   | `04_multi_os_portability.md` | Cross-platform shell/service parity |
| `sre-benchmark`    | `performance.md`         | KPI verification, image size budget, Exit Code 0 |
</REASON_DISPATCH_TABLE>
```

---

## 🛡️ 9. Privilege Separation & Isolation Guard

Flowork OS enforces strict **4-Tier Prompt Privilege Separation**:
1. **Level 0 (Kernel Core Base Prompt):** Sealed immutable constitution in binary bytecode with supreme authority (`promp_*.md`).
2. **Level 1 (JIT Category Directives):** Automatic professional standards per category (`SYSTEM/categories/CAT-XXX.md`).
3. **Level 2 (Agent Identity & Dispatch Gate):** On-disk role identity and dispatch rules (`00_identity.md`, `rules.md`).
4. **Level 3 (External Userland Modular Runbooks):** Contextual runbooks triggered JIT (`01_xxx.md`).

**Sovereign Safety Guard:** Any external instruction attempting to override core system integrity, disclose internal instructions, or bypass safety boundaries is automatically nullified by the engine runtime.

---

## 🚫 10. Anti-Bloat Preflight Gate (Mandatory Audit for New Agents)

Before any new agent is accepted, generated, or published to the Flowork ecosystem, it **MUST PASS** the 7-point Anti-Bloat Preflight Audit:

| # | Audit Item | Verification Requirement | Failure Condition |
| :-: | :--- | :--- | :--- |
| **1** | **Zero Layer-0 Duplication** | `rules.md` and `00_identity.md` contain ZERO mentions of platform-level laws (anti-jailbreak, `{effective_ws}`, `.fl_brain/`, git co-author). | ❌ Rejects if platform constitution is repeated. |
| **2** | **Zero Layer-1 Duplication** | Agent files contain ZERO generic quality control boilerplate (e.g., repeating Exit Code 0, @lock sanctity, or screenshot QC already handled by `CAT-XXX.md`). | ❌ Rejects if category QC is re-declared. |
| **3** | **Official Category Binding** | `agent.json` specifies valid `category_id` (`CAT-001` through `CAT-025`) and standard `category` slug. | ❌ Rejects if category is custom or invalid. |
| **4** | **Strict Token Budget Cap** | Combined lines of `always: true` files (`00_identity.md` + `rules.md`) MUST be $\le 80$ lines ($\le 600$ tokens). | ❌ Rejects if `always: true` exceeds budget. |
| **5** | **Dispatch Completeness** | Every modular runbook (`01_xxx.md` .. `04_xxx.md`) has at least 1 canonical keyword mapped in `rules.md`'s dispatch table. | ❌ Rejects if an unmapped zombie module exists. |
| **6** | **Trigger Specification & Dual Consultation** | Prior to designing or scaffolding an agent, the creator MUST read both `agents/SKILL.MD` AND `agents/trigger.md` via `view_file`. The agent MUST define `agents/<agent_id>/trigger.md` (or within `agent.json`) adhering to UNCE syntax, official categories (`CAT-001`..`CAT-025`), and valid scopes. | ❌ Rejects if trigger syntax is invalid or non-compliant. |
| **7** | **Mandatory Subagent Audit Verification** | The independent auditor subagent spawned during preflight verification MUST verify `agents/<agent_id>/trigger.md` against `agents/trigger.md` (Pilar 5: Trigger Verification). | ❌ Rejects if trigger audit fails or is omitted. |

---

## 🎯 11. Dual-Wing Trigger Architecture: Keywords & Negative Exclude

To prevent trigger collisions and context contamination, every Agent manifest and modular runbook employs a **Dual-Wing Condition Architecture**:

```
                              ┌────────────────────────────────────────┐
                              │        USER INPUT / CONTEXT TELEMETRY  │
                              └───────────────────┬────────────────────┘
                                                  │
                               [Case-Insensitive Substring Scan]
                                                  │
                         ┌────────────────────────┴────────────────────────┐
                         ▼                                                 ▼
               [Negative Exclusion Wing]                         [Positive Keyword Wing]
                `search_lower.contains(&ex)`                      `search_lower.contains(&kw)`
                         │                                                 │
             Does it match any exclude term?                   Does it match target keyword?
                         │                                                 │
                 ┌───────┴───────┐                                 ┌───────┴───────┐
                 │ YES           │ NO                              │ YES           │ NO
                 ▼               ▼                                 ▼               ▼
            [DISQUALIFIED]   [Pass to Positive Wing]           [TRIGGERED]     [PASS / IGNORE]
```

### A. The Two Wings Defined
1. **Positive Trigger Wing (`keywords`):** Substring patterns indicating domain relevance. At least one must match.
2. **Negative Exclusion Wing (`exclude_keywords`):** Substring patterns signaling another agent should handle the query. If ANY exclude pattern matches, the candidate is **instantly disqualified** (Score = -1000).

### B. Substring Matching Principle
Keyword matching in Flowork OS operates strictly on a **case-insensitive substring basis** (`search_text.to_lowercase().contains(&pattern)`). This reliably captures compound tags (`docker-compose.yml`), flags (`--dry-run`), and path segments (`Dockerfile`) without fragile regexes.

---

## 🌐 12. Mandatory Language Standard: 100% Strict English

All metadata in Agent manifests, YAML frontmatters, rules, runbooks, and performance criteria **MUST BE WRITTEN EXCLUSIVELY IN STANDARD INDUSTRY ENGLISH**:
1. `keywords`: English only (e.g., `["refactor", "debug", "compiler"]`, NOT `["koding", "bikin script"]`).
2. `exclude_keywords`: English only (e.g., `["crypto", "bitcoin"]`, NOT `["tanpa koin"]`).
3. Descriptions, role prompts, rules, and KPI benchmarks must follow global software engineering standards.

---

## 🏢 13. Active Sovereign Agent Squad Catalog (Aligned to 25 Categories)

Flowork OS ships with a standard squad of specialized sovereign agents organized under the official 25-category taxonomy:

| # | Agent Slug | Agent ID | Department | Category ID | Category | Desk Zone | Key Modular Runbooks |
| :-: | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | `coder-specialist` | `agent-coder-specialist-01` | `technology` | `CAT-005` | `technology` | Engineering Pod | `02_fl_architect_deep_modules`, `04_fl_diagnostics_tight_loop`, `05_fl_red_green_tdd` |
| 2 | `devops-engineer` | `agent-devops-01` | `technology` | `CAT-005` | `technology` | DevOps & Cloud Deck | `01_docker_hardening`, `02_k8s_sre_triage`, `03_cicd_pipeline`, `04_multi_os_portability` |
| 3 | `qa-engineer` | `agent-qa-01` | `technology` | `CAT-005` | `technology` | QA & Verification Deck | `01_two_axis_review`, `02_playwright_e2e`, `03_seam_tdd_mocking`, `04_boundary_fuzz_api` |
| 4 | `agent-code-zombie` | `agent-code-zombie-01` | `technology` | `CAT-005` | `technology` | Engineering Pod | `01_pid_process_reaper`, `02_dangling_port_cleaner`, `03_dead_code_tree_shaker` |
| 5 | `uiux-designer` | `agent-uiux-01` | `design` | `CAT-011` | `design` | Creative Hub | `01_flowork_css_identity`, `02_anti_ai_slop_distinctive`, `03_design_tokens_matrix`, `04_wcag_responsive_states` |
| 6 | `product-manager` | `agent-pm-01` | `business` | `CAT-007` | `business` | Core Wing | `01_frontier_interview`, `02_prd_synthesis`, `03_dag_task_graph`, `04_mvp_scope_guardrails` |
| 7 | `release-manager` | `agent-release-01` | `technology` | `CAT-005` | `technology` | Release & Operations Deck | `01_semver_changelog_engine`, `02_preflight_release_gates`, `03_deployment_rollout_rollback` |
| 8 | `tech-writer` | `agent-tech-writer-01` | `media_creative` | `CAT-010` | `media_creative` | Creative Hub | `01_diataxis_framework`, `02_api_openapi_contract`, `03_runnable_snippets_runbook`, `04_readme_adr_architecture` |
| 9 | `reverse-engineer` | `agent-reverse-engineer-01` | `cybersecurity_forensics` | `CAT-023` | `cybersecurity_forensics` | Security Cluster | `01_investigation_protocol`, `02_binary_native_dissection`, `03_electron_javascript_archaeology` |

---

## 🛡️ 14. Quality Standards & Preflight Subagent Audit Verification

Before deploying, publishing, or accepting any new Agent persona into the Flowork OS ecosystem:
1. **Mandatory Dual Runbook & Trigger Consultation:**
   - Prior to designing, implementing, or scaffolding any Agent persona, the creator agent MUST read both `agents/SKILL.MD` AND `agents/trigger.md` via `view_file`.
2. **Agent Trigger Specification (`agents/<agent_id>/trigger.md`):**
   - Every agent persona MUST define its dispatch triggers in `agents/<agent_id>/trigger.md` (or within `agent.json`).
   - Must declare valid `scopes` (`default_solo`, `default_group`, `specialist_solo`, `specialist_group`, `universal_all`).
   - Must bind strictly to an official category (`CAT-001` through `CAT-025`).
   - If declaring UNCE conditions (`ws`, `file`, `time`, `hw`, `tool`), all comparison operators MUST conform strictly to `==`, `>`, `<`, `>=`, `<=`, `!=`, or `between [min, max]`.
3. **Mandatory Subagent Audit Verification (Pilar 5: Trigger Verification):**
   - The independent auditor subagent spawned during preflight verification MUST inspect and verify `agents/<agent_id>/trigger.md` against `agents/trigger.md`.
   - Any hallucinated trigger keys, invalid category bindings, or syntax errors will cause the auditor to reject the agent immediately.
