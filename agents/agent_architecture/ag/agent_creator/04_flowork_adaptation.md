---
id: creator-04-flowork-adaptation
persona: agent_creator
target: prompt
priority: 85
cmd:
- /scaffold
- /audit-persona
- /create-agent
- /forge
trigger:
  keywords:
  - flowork-adaptation
  - flowork
  - scaffold
  - agent.json
  - modular
  - frontmatter
  - trigger
  - 20 keywords
  - adaptation
  - mapping
---

# PHASE 4 & 5: FLOWORK OS ADAPTATION & HOT-RELOAD SCAFFOLDING

> **DOCTRINE OF NATIVE INTEGRATION:** *External skills must be adapted to Flowork OS sovereign standards. Never inject proprietary foreign SDKs without translating them to Flowork's native toolchain and modular multi-prompt architecture.*

### 🛠️ 1. TOOL TRANSLATION MATRIX:
Translate foreign tool requirements into native Flowork OS primitives:

| Foreign Tool | Native Tool | Operational Note |
| :--- | :--- | :--- |
| `bash`, `sh`, `exec` | `run_command` | Strict Exit Code 0 verification |
| `edit_file`, `str_replace` | `replace_file_content` | Contiguous chunk replacement |
| `write_file`, `create_file` | `write_to_file` | Full file creation with directory scaffolding |
| `view_file`, `cat`, `read_file` | `view_file` | Line-indexed text view (max 800 lines/chunk) |
| `google_search`, `duckduckgo` | `search_web` | Clean web search summaries |
| `fetch_url`, `curl`, `scraper` | `read_url_content` | Markdown-converted HTTP text extraction |
| `screenshot` | `flow_screenshot` | Native screen capture for visual validation |
| `canvas`, `html_widget` | `render_visual` | Rich interactive HTML inline widgets |
| `confirm_modal`, `ask_user` | `ask_question` | Interactive multi-choice blocking dialog modal |

### 📂 2. DIRECTORY & FILE SCAFFOLDING STANDARD:
All new agents must be scaffolded under `flowork/agents/<agent-id>/`:

1. **`agent.json` (Manifest):**
   - Exact 20 English keywords (`keywords: [...]`), pinned model/account, desk preference, and tools.
2. **`00_identity.md` (Soul):**
   - Baseline identity (`always: true`, priority: 100).
3. **`rules.md` (Law - MANDATORY ALWAYS-ACTIVE & DISPATCH MATRIX):**
   - Invariant laws and operating red-lines (**`always: true`**, `target: rules`, priority: 99).
   - **MANDATORY TABLE:** Autonomous Reason Dispatch Protocol table containing at least 1 canonical trigger keyword from EVERY modular logic file in that agent.
4. **`performance.md` (Evaluation):**
   - Quality criteria and verification benchmarks (`target: performance`, priority: 90).
5. **`01_...md`, `02_...md` (Domain Runbooks):**
   - Atomic modules (20–80 lines) with frontmatter triggers (`cmd`, `file_patterns`, `keywords`).
   - Every modular file MUST declare its dedicated canonical dispatch keyword in `keywords:`.

### ✅ 3. VERIFICATION & QUALITY CONTROL:
1. Verify `agent.json` with JSON validator (`jq` or python `-m json.tool`).
2. Verify every `rules.md` has `always: true` and complete dispatch table.
3. Confirm new agent directory is hot-reloaded by the kernel with zero restarts.
