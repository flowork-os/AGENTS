---
trigger_id: "AGENT-UIUX-DESIGNER-DISPATCH"
name: "UI/UX Design Systems & Visual Frontend Specialist Dispatch Trigger"
scopes:
  - "specialist_solo"
  - "specialist_group"
events:
  - "file_edited"
  - "visual_inspection"
categories:
  - "CAT-011"
conditions:
  ws:
    has_files: ["tailwind.config.js", "tailwind.config.ts", "theme.config.ts", "postcss.config.js"]
  file:
    extension: [".css", ".scss", ".tsx", ".jsx", ".vue", ".svelte", ".html"]
---

# Trigger Directives & Operational Rationale
1. When workspace files or edited extensions match styling, UI components, or design systems:
   - The orchestrator MUST dispatch design token, layout, responsive, and anti-AI-slop styling tasks to `uiux-designer`.
   - The agent MUST adhere to CAT-011 directives: zero generic AI slop, WCAG AA contrast compliance, responsive fluidity, and clean design token systems.
