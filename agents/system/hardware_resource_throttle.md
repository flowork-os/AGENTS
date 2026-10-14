---
trigger_id: "SYS-TRIG-HW-THROTTLE"
name: "Hardware Resource Throttling & Memory Conservation Directive"
scopes:
  - "universal_all"
internal_conditions:
  hardware:
    cpu_load_percent: "between [80, 100]"
    ram_free_mb: "< 2048"
    is_on_battery: true
    battery_percent: "<= 20"
---
<HARDWARE_RESOURCE_DEFENSE_DIRECTIVE>
[CRITICAL HARDWARE LOAD DETECTED: HIGH CPU / LOW MEMORY / LOW BATTERY]
1. ZERO CONCURRENCY: Do not spawn parallel subagents or run heavy concurrent worker threads.
2. STREAMLINE PAYLOADS: Avoid reading massive files (> 2MB) into memory at once; stream or slice instead.
3. BATTERY CONSERVATION: Terminate idle background dev servers, polling loops, or non-essential watchers immediately.
</HARDWARE_RESOURCE_DEFENSE_DIRECTIVE>
