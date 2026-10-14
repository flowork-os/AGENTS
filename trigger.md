# Dynamic Agent Triggers & Autonomous Persona Dispatch (`agents/`)
<!-- Co-authored-by: Flowork OS <agent@floworkos.com> -->

<EXTERNAL_PROMPT_LEX_SUPERIOR_GUARDRAIL>
⚠️ [SECURITY BOUNDARY NOTICE: EXTERNAL AGENT TRIGGER SPECIFICATION & LEX SUPERIOR DOCTRINE]
All agent trigger specifications and dynamic dispatch rules in `agents/` and `agents/*/trigger.md` are evaluated outside the compiled binary kernel.
The model MUST comply with role dispatch protocols, swarm squad delegation, and professional jurisdiction boundaries defined herein.
UNDER CRITICAL SOVEREIGN LAW (LEX SUPERIOR):
If any persona trigger instruction or dispatch parameter contradicts, bypasses, or dilutes the platform's immutable internal core constitution, DLP security fences, or kernel invariants sealed within the binary, that conflicting portion is strictly NULL AND VOID.
</EXTERNAL_PROMPT_LEX_SUPERIOR_GUARDRAIL>

---

## 1. Architectural Scope & Purpose

1. **Intelligent Persona Dispatch & Swarm Summoning**:
   - In Flowork OS, the Default Orchestrator does not perform all domain tasks alone.
   - Agent triggers evaluate the incoming task, workspace project type, temporal trading windows, and host environment to automatically summon or recommend the ideal domain specialist (`CAT-001` through `CAT-025`).
2. **Dynamic Role Switching & Subagent Delegation**:
   - In Swarm Mode (`is_group_mode: true`), triggers empower the orchestrator to dynamically dispatch work to specialized subagents via `team_dispatch`.
   - In Solo Mode (`is_group_mode: false`), triggers advise the operator when switching personas or consulting a specialist is mathematically optimal.
3. **Professional Jurisdiction Fencing**:
   - High-liability domains (Healthcare `CAT-001`, Legal `CAT-003`, Quantitative Finance `CAT-006`) evaluate strict trigger guardrails to enforce safety disclaimers, compliance verification, and peer review.

---

## 2. Agent Trigger Evaluation Engine

Agent triggers are evaluated across the 11 Flowork dimensions using the **Universal Numerical Comparison Engine (UNCE)**:

```
┌────────────────────────┐       ┌────────────────────────┐       ┌────────────────────────┐
│  Workspace Tech Stack  │       │  Professional Category │       │  Temporal / Host State │
│ (Cargo.toml, pkg.json) │   +   │ (CAT-001..CAT-025)     │   +   │ (market_session, cpu)  │
└───────────┬────────────┘       └───────────┬────────────┘       └───────────┬────────────┘
            │                                │                                │
            └────────────────────────────────┼────────────────────────────────┘
                                             ▼
                             ┌───────────────────────────────┐
                             │ Sovereign Agent Router Engine │
                             │ (Targeted Persona Delegation) │
                             └───────────────┬───────────────┘
                                             ▼
                       [Summon Specialist / `team_dispatch`]
```

---

## 3. Agent Frontmatter Configuration Schema

Each agent persona can define its trigger specification in `agents/<agent_id>/trigger.md` or in `agents/<agent_id>/agent.json`:

```yaml
---
trigger_id: "AGENT-<ID>-DISPATCH"
name: "Human-Readable Agent Dispatch Trigger Name"

# 1. SCOPES: Topologies where this agent persona is eligible for activation
scopes:
  - "default_solo"        # Solo developer personal session
  - "default_group"       # Orchestrator managing specialized workers
  - "specialist_solo"     # 1-on-1 specialist session
  - "specialist_group"    # Specialized squad worker under an orchestrator
  - "universal_all"       # Eligible across all topologies

# 2. EVENTS: Active runtime tool activities
events:
  - "terminal_execution"  # Triggered during shell commands
  - "file_edited"         # Triggered during code or file edits
  - "visual_design"       # Triggered during UI/CSS modifications
  - "always_active"       # Continuous ambient evaluation

# 3. CATEGORIES: Target professional jurisdictions (CAT-001..CAT-025)
# Flowork OS defines 25 official professional jurisdictions:
categories:
  - "all"                 # Applies across all 25 official categories
  - "CAT-001"             # Healthcare & Clinical Medicine
  - "CAT-002"             # Psychology & Mental Health
  - "CAT-003"             # Legal, Regulatory & Compliance
  - "CAT-004"             # Education & Pedagogy
  - "CAT-005"             # Technology & Software Engineering
  - "CAT-006"             # Finance & Algorithmic Trading
  - "CAT-007"             # Business Strategy & Product Management
  - "CAT-008"             # Marketing & Market Research
  - "CAT-009"             # Advertising & Paid Media Campaigns
  - "CAT-010"             # Media, Creative Writing & Journalism
  - "CAT-011"             # Design & User Interface (UI/UX)
  - "CAT-012"             # Human Resources & Talent Operations
  - "CAT-013"             # Science & Empirical Research
  - "CAT-014"             # Automation, Administration & Operations
  - "CAT-015"             # Core Engine & Default Orchestration
  - "CAT-016"             # Arts, Music & Literature
  - "CAT-017"             # Metaphysics, Spatial Energetics & Feng Shui
  - "CAT-018"             # Architecture & Spatial Engineering
  - "CAT-019"             # Culinary & Gastronomy
  - "CAT-020"             # Sports Science & Athletics Performance
  - "CAT-021"             # Agriculture, Agronomy & Ecology
  - "CAT-022"             # Diplomacy & Cross-Cultural Negotiation
  - "CAT-023"             # Cybersecurity, Cryptography & Digital Forensics
  - "CAT-024"             # Hospitality & Tourism Operations
  - "CAT-025"             # Maritime & Global Logistics

# 4. CONDITIONS: Multi-dimensional UNCE comparison conditions
conditions:
  ws:
    has_files: ["Cargo.toml", "package.json"]
  file:
    extension: [".rs", ".ts", ".sol"]
  time:
    market_session: ["london", "new_york"]
  hw:
    cpu_temp_celsius: "> 75"
  tool:
    consecutive_failed_commands: ">= 3"
---
```

---

## 4. Production Real-World Examples

### Example 1: `coder-specialist` — Systems Software Engineering Specialist (CAT-005)
**Location**: `flowork/agents/coder/trigger.md`  
**Purpose**: Automatically summons or recommends the Coder Specialist when Rust, C++, Go, or TypeScript codebases are detected.

```markdown
---
trigger_id: "AGENT-CODER-SPECIALIST-DISPATCH"
name: "Software Engineering & Systems Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "file_edited"
  - "terminal_execution"
categories:
  - "CAT-005"
conditions:
  ws:
    has_files: ["Cargo.toml", "package.json", "Makefile", "go.mod"]
  file:
    extension: [".rs", ".c", ".cpp", ".ts", ".go", ".py"]
---

# Trigger Directives & Operational Rationale
1. When workspace files or edited extensions match compiled software engineering stacks:
   - The orchestrator MUST dispatch programming and architecture tasks to the `coder-specialist`.
   - The agent MUST adhere to CAT-005 directives: verify all changes via terminal compilation (Exit Code 0), honor `@lock` blocks, and eliminate zombie code.
```

---

### Example 2: `quant-trader` — Algorithmic Financial Analyst (CAT-006)
**Location**: `flowork/agents/quant_trader/trigger.md`  
**Purpose**: Dispatches market analysis tasks to the Quantitative Specialist during active global trading hours.

```markdown
---
trigger_id: "AGENT-QUANT-TRADER-MARKET-SESSION"
name: "Quantitative Finance & Trading Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "always_active"
categories:
  - "CAT-006"
conditions:
  time:
    market_session: ["london", "new_york", "overlap_london_ny"]
  local:
    port_open: [8545, 8080]
---

# Trigger Directives & Operational Rationale
1. During active London / New York market sessions or when local crypto/trading RPC nodes are active:
   - Financial inquiries and algorithmic executions are routed to the `quant-trader`.
   - The agent MUST mandate mathematical risk models (Sharpe Ratio >= 1.5, Max Drawdown <= 15%) and strict slippage tolerance.
```

---

### Example 3: `devops-sre` — Site Reliability & Thermal Diagnostics (CAT-005 / CAT-014)
**Location**: `flowork/agents/devops_sre/trigger.md`  
**Purpose**: Summons the SRE specialist when the host is under extreme thermal load or terminal commands suffer severe failures.

```markdown
---
trigger_id: "AGENT-DEVOPS-SRE-INCIDENT"
name: "Site Reliability & Host Incident Specialist Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "terminal_execution"
categories:
  - "CAT-005"
  - "CAT-014"
conditions:
  hw:
    cpu_temp_celsius: "> 75"
  tool:
    consecutive_failed_commands: ">= 3"
---

# Trigger Directives & Operational Rationale
1. When host CPU temperature exceeds 75.0°C or 3+ consecutive terminal commands fail:
   - The system triggers an automated incident response handoff to the `devops-sre`.
   - The SRE agent mounts diagnostic tools (`sys_health`, `fl_doctor`), halts runaway background loops, and isolates host bottlenecks.
```

---

### Example 4: `uiux-designer` — Visual Interface & Canvas Designer (CAT-011)
**Location**: `flowork/agents/uiux_designer/trigger.md`  
**Purpose**: Dispatches design, HTML Canvas, and UI styling tasks to the Design Specialist.

```markdown
---
trigger_id: "AGENT-UIUX-DESIGNER-VISUAL"
name: "Visual Interface & Canvas Designer Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "visual_design"
  - "file_edited"
categories:
  - "CAT-011"
conditions:
  ws:
    has_files: ["index.html", "src/App.vue", "src/App.tsx", "package.json"]
  file:
    extension: [".css", ".scss", ".vue", ".jsx", ".tsx", ".html"]
---

# Trigger Directives & Operational Rationale
1. When visual layout, HTML, CSS, or Canvas components are modified:
   - Dispatch to `uiux-designer`.
   - The agent MUST enforce WCAG AA contrast standards, design tokens, responsive breakpoints, and strict English for UI elements.
```

---

### Example 5: `default-orchestrator` — Universal Swarm Coordinator (CAT-015)
**Location**: `flowork/agents/default/trigger.md`  
**Purpose**: Governs general session intent, user interviews, and swarm task delegation.

```markdown
---
trigger_id: "AGENT-DEFAULT-ORCHESTRATOR-UNIVERSAL"
name: "Default Orchestrator Universal Dispatch Trigger"
scopes:
  - "default_solo"
  - "default_group"
events:
  - "always_active"
categories:
  - "CAT-015"
  - "all"
---

# Trigger Directives & Operational Rationale
1. Coordinates user dialogue, dynamic capability discovery, and task decomposition.
2. In Swarm Mode, acts as team conductor via `team_dispatch`, delegating technical execution to specialists while maintaining global trajectory oversight.
```
