---
trigger_id: "SYS-TRIG-FIN-LONDON"
name: "London / NY Overlap Liquidity & Risk Management Directive"
scopes:
  - "specialist_solo"
  - "specialist_group"
categories:
  - "CAT-006"
internal_conditions:
  time:
    timezone: "utc"
    hour: "between [13, 16]"
    clock: "between ['13:00', '16:00']"
    market_session: ["london", "overlap_london_ny"]
    day_of_week: ["weekday"]
  local_services:
    process_running: ["metatrader5", "terminal64.exe"]
---
<TRADING_EXECUTION_GUARDRAIL>
[HIGH-VOLATILITY SESSION DETECTED: LONDON / NY OVERLAP]
1. SPREAD SPIKE WARNING: High volatility expected. Verify bid/ask spread prior to order transmission.
2. STRICT RISK SIZING: Never dispatch market orders without pre-calculated Stop Loss levels (max 1-2% account equity risk).
3. BRIDGE INTEGRITY: Verify local execution bridge heartbeat before state submission.
</TRADING_EXECUTION_GUARDRAIL>
