---
id: uiux-flowork-css-identity
persona: uiux-designer
target: prompt
priority: 96
trigger:
  cmd:
  - /tokens
  - /flowork-css
  - /css-prefix
  keywords:
  - flowork-css
  - flowork css
  - css namespace
  - fl prefix
  - anti collision
  - css custom properties
  - scoped classes
  - design tokens
  - class naming
  - css architecture
  - token naming
  exclude_keywords:
  - reverse engineering
  - assembly
  - database migration
  - forex
---
# 🏷️ FLOWORK CSS NAMESPACING & ANTI-COLLISION ENGINE

<FLOWORK_CSS_IDENTITY_ENGINE>
### 1. MANDATORY FLOWORK PREFIX TAXONOMY
Every generated stylesheet, CSS module, utility class, and design token MUST incorporate the Flowork namespace to establish brand identity and eliminate collision against third-party UI frameworks:

- **CSS Custom Properties (Design Tokens):**
  - Primary Prefix: `--fl-*` (e.g. `--fl-bg-canvas`, `--fl-bg-surface`, `--fl-text-primary`, `--fl-accent-cyan`).
  - Extended Namespaces: `--flowork-*` (system level) and `--flow-*` (layout/grid level).
  - *Banned:* Raw unprefixed variables like `--bg-color`, `--primary`, `--spacing-4`.

- **Component & Utility Class Names:**
  - Standard Prefix: `.fl-*` (e.g. `.fl-card`, `.fl-avatar`, `.fl-pill`, `.fl-input`, `.fl-dialog`, `.fl-telemetry`).
  - System Components: `.flowork-btn`, `.flowork-modal`, `.flowork-drawer`.
  - Layout Utilities: `.flow-grid`, `.flow-stack`, `.flow-split-view`, `.flow-badge`.
  - *Banned:* Generic classes like `.card`, `.btn`, `.modal`, `.container`, `.badge`.

- **Data Attributes & State Selectors:**
  - Data Identity: `data-fl-theme="cyber" | "oled" | "studio"`
  - State Reflection: `data-fl-state="idle" | "loading" | "error" | "active"`
  - Density Scaling: `data-flow-density="compact" | "comfortable"`

- **Keyframe Animations:**
  - Prefix Standard: `@keyframes fl-*` and `@keyframes flowork-*`
  - Examples: `@keyframes fl-pulse`, `@keyframes fl-shimmer`, `@keyframes flowork-reveal`.

### 2. ANTI-COLLISION INTEGRATION DISCIPLINE
1. **Third-Party Immunity:**
   - Flowork stylesheets must safely coexist with Tailwind, Bootstrap, or host CSS without specificity escalation wars or rule hijacking.
2. **Strict File Naming Conventions:**
   - Stylesheet filenames must reflect the Flowork namespace: `fl-tokens.css`, `fl-components.css`, `flow-grid.css`.
3. **Multi-OS Asset Paths:**
   - Font face declarations and background assets must use relative portable paths (`./assets/fonts/...`), NEVER hardcoded platform paths.
</FLOWORK_CSS_IDENTITY_ENGINE>
