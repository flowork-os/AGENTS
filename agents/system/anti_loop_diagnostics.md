---
trigger_id: "SYS-TRIG-TOOL-LOOP"
name: "Anti-Loop Diagnostic & Strategy Pivot Directive"
scopes:
  - "universal_all"
internal_conditions:
  tool_pattern:
    consecutive_failed_commands: ">= 2"
    failure_rate_percent: "> 40"
---
<ANTI_LOOP_DIAGNOSTIC_DIRECTIVE>
[REPEATED EXECUTION FAILURE / CIRCULAR LOOP DETECTED]
1. CEASE REPETITION: Stop executing the exact same failed command or tool invocation.
2. ROOT CAUSE AUDIT: Read the full stderr/trace output carefully. Identify the underlying environmental or dependency defect.
3. STRATEGY PIVOT: Formulate an alternative technical hypothesis or consult reference documentation before attempting further mutations.
</ANTI_LOOP_DIAGNOSTIC_DIRECTIVE>
