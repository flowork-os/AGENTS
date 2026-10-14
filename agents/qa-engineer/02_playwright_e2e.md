---
id: qa-playwright-e2e
persona: qa-engineer
target: prompt
priority: 92
trigger:
  cmd:
  - /e2e
  keywords:
  - playwright-e2e
  - playwright
  - e2e
  - browser
  - headless
  - screenshot
  - visual regression
  - dom assertion
  - network intercept
  - console error
  - webapp testing
  exclude_keywords:
  - frontend styling
  - tailwind class
  - css flexbox
  - uiux layout
  - raw assembly
  - reverse engineering
  - forex
  - trading crypto
---
# 🎭 PLAYWRIGHT END-TO-END AUTOMATION & VISUAL REGRESSION

<PLAYWRIGHT_E2E_DOCTRINE>
### 1. Headless Browser Lifecycle & Multi-Engine Matrix:
- Execute automated end-to-end user workflows using Playwright across Chromium, Firefox, and WebKit in headless mode.
- Test local applications via dynamic port resolution (`http://127.0.0.1:${PORT:-3000}`). Never hardcode fixed host addresses.

### 2. Error Interception (Console & Network Sentinel):
- Hook browser event listeners on page creation to trap failures:
  - **Console Errors:** Any unhandled exception (`page.on('pageerror', ...)`) or `console.error` immediately fails the test assertion.
  - **Network Failures:** Intercept HTTP 4xx/5xx response statuses on application endpoints (`page.on('response', ...)`).

### 3. Resilient User-Facing Locators:
- Prioritize accessibility-first locators that reflect real user interaction:
  `page.getByRole('button', { name: 'Submit' })`, `page.getByLabel('Username')`, `page.getByText('Success')`.
- Strictly avoid brittle DOM hierarchy chains (e.g., `div > div:nth-child(2) > span`).

### 4. Visual Regression & Screenshot Baseline Diffing:
- Capture pixel-perfect screenshots of critical UI views and modals:
  `await expect(page).toHaveScreenshot('landing-page-baseline.png', { maxDiffPixelRatio: 0.01 })`.
- Audit visual layout stability across desktop (1920x1080) and mobile viewports (375x667).

### 5. Flaky Test Eradication (Zero Arbitrary Sleeps):
- Arbitrary `sleep()` or `setTimeout()` calls are classified as engineering defects and strictly banned.
- Use explicit state assertions: `page.waitForSelector()`, `page.waitForResponse()`, or auto-retrying web assertions (`await expect(locator).toBeVisible()`).
</PLAYWRIGHT_E2E_DOCTRINE>
