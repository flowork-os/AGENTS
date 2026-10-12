---
name: "sovereign_agents_registry"
category: "agent_architecture"
description: "Official sovereign agent registry, subfolder sharding hierarchy, zero-token fastly codeload delivery, and lifecycle pin-unpin governance for Flowork OS."
keywords:
  - "agents"
  - "registry"
  - "sharding"
  - "personas"
  - "subfolders"
  - "pinning"
  - "unpinning"
  - "codeload"
  - "fastly"
  - "tarball"
  - "discovery"
  - "sovereign"
  - "modular"
  - "manifest"
  - "attestation"
  - "taxonomy"
  - "microkernel"
  - "orchestration"
  - "governance"
  - "sandboxing"
---

# 🤖 Flowork OS Sovereign Agents Registry & Sharded Architecture

Welcome to the official repository for **Flowork OS Sovereign Agents** (`flowork-os/AGENTS`).
Flowork OS decouples agent personalities, operational prompts, and reasoning styles completely from the binary engine. All agents are 100% modular, plug-and-play, and discoverable via high-performance sharded subfolders.

---

## 🏛️ 1. Subfolder Sharding Canonical Hierarchy

To prevent directory explosion and filesystem inode degradation across thousands of community agents, all agents follow a strict 2-letter sharded hierarchy:

$$\mathbf{agents/\{category\}/\{prefix\}/\{agent\_id\}/}$$

### Official Canonical Built-in Matrix:
1. `agents/universal_core_system/de/default`
2. `agents/software_engineering_craft/co/coder-specialist`
3. `agents/devops_infrastructure/de/devops-engineer`
4. `agents/quality_assurance/qa/qa-engineer`
5. `agents/product_strategy/pr/product-manager`
6. `agents/design_systems/ui/uiux-designer`
7. `agents/technical_documentation/te/tech-writer`
8. `agents/release_operations/re/release-manager`
9. `agents/security_reverse_engineering/re/reverse-engineer`
10. `agents/agent_architecture/ag/agent_creator`

---

## ⚡ 2. Zero-Token / Zero-Quota Fastly Delivery Doctrine

All installations and downloads of agents from this repository are guaranteed **100% free of GitHub REST API limits**:
- **Registry Discovery**: Streamed directly via Fastly Raw CDN (`raw.githubusercontent.com/flowork-os/AGENTS/main/agents.json`).
- **Archive Extraction**: Streamed directly via public Codeload tarball stream (`codeload.github.com/flowork-os/AGENTS/tar.gz/refs/heads/main`) using native `curl | tar`.

---

## 📌 3. Universal Pinning & Unpinning Protocol

Agents can be pinned to active conversational sessions using the native in-binary anchor tool `agent_control`:
- **Search**: `agent_control(action: "search", query: "coder")`
- **Pin / Activate**: `agent_control(action: "pin", agent_id: "coder-specialist")`
- **Unpin / Reset**: `agent_control(action: "unpin")`
- **Status Check**: `agent_control(action: "status")`
- **Inspect**: `agent_control(action: "read", agent_id: "devops-engineer")`

---

## 🛡️ 4. Sovereign Attestation Guard

Operations that download or publish agents are guarded by hardware-grade integrity checks:
- Any tampering with core authentication interfaces or runtime binaries automatically locks the ecosystem gate.
- Developer mode bypass is exclusively unlocked by authenticating `flowork/dev.flow` credentials.
