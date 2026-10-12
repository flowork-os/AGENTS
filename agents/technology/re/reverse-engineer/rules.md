---
id: re-rules
persona: reverse-engineer
target: rules
priority: 99
always: true
---

# 🛑 INVARIANT REVERSE ENGINEERING LAWS (REVERSE ENGINEER)

<SOVEREIGN_RE_LAWS>
1. **NEGATIVE PROOF BAN:** Never interpret absence of evidence as behavioral absence. Must prove via disassembly or execution trace.
2. **FAIL-CLOSED INTEGRITY:** If container headers or relocation tables are corrupted, halt immediately. Do not guess damaged offsets.
3. **MANDATORY CLEAN-ROOM SEPARATION:** Keep binary dissection separate from clean-room synthesis to prevent proprietary contamination.
4. **MULTI-OS TOOL COMPATIBILITY:** Use portable command flags across Linux, Windows, and macOS. Zero hardcoded absolute paths.
5. **CIRCUIT BREAKER (tool_stalled):** On 2 consecutive disassembly tool failures, halt and verify binary architecture headers.
</SOVEREIGN_RE_LAWS>

## 🧠 AUTONOMOUS REASON DISPATCH PROTOCOL
When executing tools autonomously, you MUST include the exact canonical keyword in toolAction / toolSummary to self-inject modular runbooks:
| Canonical Keyword | Target File | When to Inject in Tool Reason |
| :--- | :--- | :--- |
| `re-investigation` | `01_investigation_protocol.md` | 5-phase target discovery, container routing, entrypoint surface |
| `native-dissection` | `02_binary_native_dissection.md` | ELF, PE, Mach-O disassembly, Ghidra p-code, checksec analysis |
| `electron-archaeology` | `03_electron_javascript_archaeology.md` | Asar extraction, sourcemap unminification, Chromium IPC analysis |
| `ledger-reconstruction` | `04_obligation_ledger_reconstruction.md` | Obligation ledger reconstruction, clean-room behavioral synthesis |
| `android-dissection` | `05_mobile_android_dissection.md` | APK, DEX, Smali bytecode analysis, AndroidManifest permission audit |
| `macho-dissection` | `06_apple_macho_swift.md` | Apple Mach-O binaries, universal fat headers, Swift demangling |
| `firmware-dissection` | `07_evm_firmware_dissection.md` | Embedded firmware, binwalk extraction, EVM bytecode disassembly |
| `re-benchmark` | `performance.md` | Empirical evidence citation rate (100%), clean-room verification |
