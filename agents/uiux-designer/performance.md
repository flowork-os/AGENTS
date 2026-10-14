---
id: uiux-designer-performance
persona: uiux-designer
target: performance
priority: 90
trigger:
  cmd:
  - /tokens
  - /critique-ui
  - /wireframe
  keywords:
  - uiux-benchmark
  - kpi ui
  - design verification
  - design audit
  - tokens spec
  - visual hierarchy
  - contrast pass
  - responsive audit
  - cls benchmark
  - transition speed
  - acceptance gates
  exclude_keywords:
  - forex
  - trading crypto
circuit_breaker:
  tool_threshold:
    calls: 3
---

# 📈 PERFORMANCE BENCHMARKS & ACCEPTANCE GATES (UI/UX DESIGNER)

| Quality Dimension | Acceptance Criteria | Failure Threshold | Verification Method |
|---|---|---|---|
| **Namespace Integrity** | 100% of tokens, classes, attributes use `--fl-*` / `.fl-*` / `data-fl-*` | Any raw `.btn`, `.card`, or unprefixed var | Static CSS Regex Audit |
| **WCAG Contrast Floor** | Normal text >= 4.5:1; Headings & UI borders >= 3.0:1 | Contrast < 4.5:1 on normal text | Color Luminance Formula |
| **Viewport Elasticity** | Flawless rendering from 360px to 1920px with zero horizontal scroll | Horizontal scrollbar at any breakpoint | Viewport Stress-Test |
| **Micro-Transitions** | Interactive states complete in < 150ms via `cubic-bezier(0.16, 1, 0.3, 1)` | Transition duration >= 300ms or `transition: all` | Stylesheet Audit |
| **Cumulative Layout Shift** | Absolute CLS = 0.00 with explicit `aspect-ratio` and skeleton parity | Layout jumping during async component load | Layout Shift Audit |
| **Strict English UI** | 100% of rendered public copy, buttons, dialogs in technical English | Indonesian strings detected in UI output | String Dictionary Audit |

### 🔍 DEFINITION OF DONE FOR DESIGN TASKS
A UI/UX deliverable is physically certified ONLY when all acceptance gates pass with 100% compliance.
