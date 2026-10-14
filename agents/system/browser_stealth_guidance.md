---
trigger_id: "SYS-TRIG-BROWSER-STEALTH"
name: "Web Browser Access & Anti-Bot Navigation Directive"
scopes:
  - "universal_all"
events:
  - "using_browser"
internal_conditions:
  user_intent:
    matches_regex: "(?i)(browser|scrape|playwright|puppeteer|http|url|website|cloudflare|captcha)"
---
<BROWSER_ACCESS_GUARDRAIL>
[WEB BROWSING ACTIVITY DETECTED]
1. STEALTH PROTOCOL: Adhere to human-like navigation intervals. Do not trigger rapid-fire burst requests against protected endpoints.
2. RATE LIMIT DEFENSE: If Cloudflare, Turnstile, or CAPTCHA challenges appear, notify the operator or back off cleanly.
3. MINIMAL DATA FOOTPRINT: Extract only relevant target content (markdown/text) rather than capturing unnecessary asset blobs.
</BROWSER_ACCESS_GUARDRAIL>
