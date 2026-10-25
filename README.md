# 🤖 Flowork OS Sovereign Subagent Registry

Official registry for Flowork OS autonomous subagents, utilizing the **2-Letter Alphabetical Sharded Structure** (`agents/{c1c2}/{agent_id}/`) and Sparse Sharded Index (`index/{c1c2}/{c3c4}/{agent_id}.json`).

## 📦 Active Subagents in Registry
| Agent ID | Role | Department | Sharded Path |
| :--- | :--- | :--- | :--- |
| `backend-engineer` | Backend Systems & API Contracts | Engineering | `agents/ba/backend-engineer` |
| `frontend-engineer` | Client Interface Craftsman | Engineering | `agents/fr/frontend-engineer` |
| `quality-control` | Empirical Verification Gatekeeper | Quality Assurance | `agents/qu/quality-control` |
| `security-auditor` | Security & Reverse Engineering Specialist | Security | `agents/se/security-auditor` |

## 🚀 Architectural Invariants
- **Isolated Rules**: Each subagent enforces its own boundary rules (`rules.md`).
- **Dynamic Handoff**: Strict coordination pipeline across engineering disciplines.