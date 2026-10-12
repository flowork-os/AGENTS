# 🤖 Flowork OS Sovereign Agents

Official repository for **Flowork OS Sovereign Agents** ([floworkos.com](https://floworkos.com)).

Flowork OS decouples agent personas, reasoning styles, and operational prompts completely from the binary engine. All agents are 100% modular, plug-and-play, and discoverable via high-performance sharded subfolders.

---

## 🏛️ Subfolder Sharding Hierarchy

```
agents/
├── universal_core_system/
│   └── de/
│       └── default/
├── software_engineering_craft/
│   └── co/
│       └── coder-specialist/
├── devops_infrastructure/
│   └── de/
│       └── devops-engineer/
├── quality_assurance/
│   └── qa/
│       └── qa-engineer/
├── product_strategy/
│   └── pr/
│       └── product-manager/
├── design_systems/
│   └── ui/
│       └── uiux-designer/
├── technical_documentation/
│   └── te/
│       └── tech-writer/
├── release_operations/
│   └── re/
│       └── release-manager/
├── security_reverse_engineering/
│   └── re/
│       └── reverse-engineer/
└── agent_architecture/
    └── ag/
        └── agent_creator/
```

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
- Status: `agent_control(action: "status")`

---

## 📄 License & Attribution

Governed by Flowork OS Sovereign Architecture.
Co-authored-by: Flowork OS <agent@floworkos.com>
