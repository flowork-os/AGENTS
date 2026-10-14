---
trigger_id: "SYS-TRIG-HEADLESS"
name: "Headless Server CLI-Only Operational Policy"
scopes:
  - "universal_all"
internal_conditions:
  environment:
    is_headless: true
---
<HEADLESS_SERVER_POLICY>
[ENVIRONMENT NOTICE: HEADLESS SERVER / NON-GUI HOST]
1. NO GRAPHICAL WIDGETS: Do not attempt to invoke browser windows or interactive visual tools.
2. TEXT-ONLY DELIVERABLES: Deliver all tables, analysis, and architecture specifications in standard Markdown.
3. PORTS INTEGRITY: Do not spawn non-essential local web services unless specifically requested by the operator.
</HEADLESS_SERVER_POLICY>
