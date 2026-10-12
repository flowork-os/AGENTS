---
id: uiux-design-tokens-matrix
persona: uiux-designer
target: prompt
priority: 92
trigger:
  cmd:
  - /tokens
  - /a11y-audit
  - /contrast-check
  keywords:
  - design-tokens
  - design tokens
  - primitive tokens
  - semantic tokens
  - component tokens
  - wcag contrast
  - contrast ratio
  - focus appearance
  - focus visible
  - skip link
  - target size
  exclude_keywords:
  - reverse engineering
  - disassembly
  - penetration testing
  - forex trading
---
# 🎨 3-TIER DESIGN TOKENS ARCHITECTURE & WCAG 2.1/2.2 AA MATRIX

<DESIGN_TOKENS_A11Y_ENGINE>
### 1. 3-TIER DESIGN TOKEN HIERARCHY (W3C DTCG STANDARD)
Never hardcode raw color literals or magic pixel numbers inside component styles. Enforce a clean three-tier structure:
1. **Tier 1: Primitive Tokens (Global Raw Values):**
   - Context-agnostic values for colors, spacing units, and font scales.
   - Example: `--fl-primitive-cyan-400: #22d3ee;`, `--fl-primitive-space-4: 1rem;`.
2. **Tier 2: Semantic Tokens (System Intent & Theme Layer):**
   - Functional design roles mapped to primitives.
   - **Mandatory Doctrine:** Light/Dark mode switching occurs EXCLUSIVELY at this tier. Primitives remain static; semantic tokens remap their values.
   - Surfaces: `--fl-bg-canvas`, `--fl-bg-surface`, `--fl-bg-muted`, `--fl-bg-accent`.
   - Typography: `--fl-text-primary`, `--fl-text-secondary`, `--fl-text-muted`, `--fl-text-inverse`.
   - Boundaries & Focus: `--fl-border-subtle`, `--fl-border-default`, `--fl-border-focus`.
   - Feedback: `--fl-feedback-success`, `--fl-feedback-warning`, `--fl-feedback-error`.
3. **Tier 3: Component Tokens (Scoped Implementation):**
   - Scoped strictly to specific UI elements to prevent unexpected global cascades.
   - Example: `--fl-btn-primary-bg: var(--fl-bg-accent);`, `--fl-card-border: var(--fl-border-subtle);`.

### 2. WCAG 2.1 & 2.2 LEVEL AA CONTRAST MATRIX
All color pairings must be mathematically verified against WCAG contrast algorithms:
- **Normal Text (SC 1.4.3 Level AA):** Minimum **4.5:1** contrast ratio against surrounding surface.
- **Large Text (SC 1.4.3 Level AA):** Minimum **3.0:1** contrast ratio (>=18pt / 24px, or >=14pt / 18.66px bold).
- **Non-Text Components (SC 1.4.11 WCAG 2.1):** Minimum **3.0:1** contrast for interactive input borders, checkboxes, toggles, and functional icons.
- **Focus Appearance (SC 2.4.11 WCAG 2.2):** Focus indicators must have >= **2px perimeter** area and >= **3.0:1** contrast between focused and unfocused states.
- **Target Size (SC 2.5.8 WCAG 2.2):** Minimum **24x24 CSS px** (Level AA); **44x44 CSS px** on touch viewports (`@media (pointer: coarse)`).

### 3. KEYBOARD SOVEREIGNTY & ACCESSIBILITY PATTERNS
- **Focus Rings:** Complete ban on `outline: none` without dedicated `:focus-visible` dual ring:
  `outline: 2px solid var(--fl-border-focus); outline-offset: 2px;`
- **Skip Links:** Provide `<a href="#main-content" class="fl-skip-link">Skip to main content</a>` as first DOM node, visible on keyboard focus.
- **Native Semantic First:** Always use `<header>`, `<nav>`, `<main>`, `<dialog>`, `<button>` over generic `<div>` with ARIA hacks.
</DESIGN_TOKENS_A11Y_ENGINE>
