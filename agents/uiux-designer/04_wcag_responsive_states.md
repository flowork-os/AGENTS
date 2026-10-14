---
id: uiux-wcag-responsive-states
persona: uiux-designer
target: prompt
priority: 93
trigger:
  cmd:
  - /responsive
  - /states
  - /fluid-scale
  keywords:
  - wcag-responsive
  - fluid typography
  - css clamp
  - component states
  - hover active focus
  - focus visible
  - skeleton loading
  - micro interactions
  - cubic bezier
  - cumulative layout shift
  - zero cls
  exclude_keywords:
  - kernel panic
  - assembly
  - database migration
  - forex
---
# 📐 FLUID RESPONSIVENESS, 6-STATE COMPONENTS & ZERO-CLS ARCHITECTURE

<WCAG_RESPONSIVE_STATES_ENGINE>
### 1. FLUID MULTI-VIEWPORT SCALING (CSS CLAMP ARCHITECTURE)
Enforce continuous mathematical scaling from Mobile (360px) to Ultrawide (1920px) using CSS `clamp()` linear interpolation:
- **Fluid Typography Scales:**
  - `Display / Hero`: `clamp(2.25rem, 1.615rem + 2.82vw, 5rem)`
  - `Heading 1`: `clamp(1.75rem, 1.346rem + 1.79vw, 3.5rem)`
  - `Heading 2`: `clamp(1.5rem, 1.240rem + 1.15vw, 2.625rem)`
  - `Heading 3`: `clamp(1.25rem, 1.077rem + 0.77vw, 2rem)`
  - `Body Regular`: `clamp(0.9375rem, 0.894rem + 0.19vw, 1.125rem)`
  - `Microcopy / Mono`: `clamp(0.75rem, 0.720rem + 0.12vw, 0.875rem)`
- **Fluid Layout & Gutter Rhythm:**
  - `Page Gutter`: `clamp(1rem, 0.308rem + 3.08vw, 4rem)`
  - `Section Rhythm`: `clamp(2.5rem, 1.346rem + 5.13vw, 7.5rem)`
  - `Grid Gap`: `clamp(0.75rem, 0.577rem + 0.77vw, 1.5rem)`
- **Viewport Stability:**
  - Always use `min-h-dvh` instead of `h-screen` or `100vh` to eliminate mobile address bar layout jumps.

### 2. THE 6 MANDATORY COMPONENT STATES MATRIX
Every interactive element MUST explicitly implement and verify six states:
1. **Default:** Resting baseline geometry referencing `--fl-*` tokens; minimum 44x44px touch target on coarse pointers.
2. **Hover (`:hover`):** Scoped to `@media (hover: hover) and (pointer: fine)`. Subtle luminosity shift (+/- 8-12%); NEVER shift layout geometry.
3. **Active (`:active`):** Instant tactile compression (`transform: scale(0.98)`), darker surface tone (< 100ms response).
4. **Focus-Visible (`:focus-visible`):** WCAG 2.2 SC 2.4.11 compliant double ring: `outline: 2px solid var(--fl-border-focus); outline-offset: 2px;`.
5. **Disabled (`:disabled`, `[aria-disabled="true"]`):** `opacity: 0.5`, `cursor: not-allowed`, pointer events blocked on interactive actions.
6. **Loading / Skeleton (`[data-fl-state="loading"]`):** Maintain exact original bounding box width/height to prevent layout collapsing. Container marked `aria-busy="true"`.

### 3. MICRO-INTERACTION SPEED BUDGET & ZERO CLS (0.00)
- **Speed Budget:** Complete micro-transitions in **< 150ms** (optimal: 100ms - 130ms) using fast-out curve `cubic-bezier(0.16, 1, 0.3, 1)`.
- **Composited Only:** Strictly forbid `transition: all`. Animate only `transform`, `opacity`, `background-color`, `border-color`, `box-shadow`.
- **Motion Guard:** Respect `@media (prefers-reduced-motion: reduce)` by collapsing duration to 0.01ms.
- **Zero CLS (0.00):** Lock explicit `aspect-ratio` on all media/cards, declare HTML `width`/`height` on images, and match skeleton dimensions to loaded content.
</WCAG_RESPONSIVE_STATES_ENGINE>
