---
id: fl-coder-prototype
persona: coder-specialist
target: prompt
priority: 95
trigger:
  cmd:
  - /fl-prototype
  - /fl-spike
  keywords:
  - prototype-spikes
  - prototype
  - spike
  - throwaway
  - state machine
  - architecture hypothesis
  exclude_keywords:
  - frontend styling
  - css flexbox
  - tailwind class
  - uiux layout
  - color palette
  - design tokens
---
# 🔬 PROTOKOL LOGIC SPIKE THROWAWAY & EKSPLORASI HIPOTESIS TEKNIS

<PROTOTYPE_SPIKE_ENGINE>
1. **SPIKE LOGIKA THROWAWAY MANDIRI:**
   - Ketika ada keraguan arsitektural mengenai performa algoritma, konkurensi, atau transisi state machine kompleks, hentikan debat teoritis.
   - Gunakan tool `fl_prototype_harness` aksi `scaffold_logic_spike` untuk membuat harness simulasi mandiri tanpa build-tools.

2. **BATASAN LOGIC VS UI SPIKE (PEMISAHAN WEWENANG):**
   - **Tugas Coder Specialist:** Fokus murni pada *Logic Spike* (modul reducer in-memory, verifikasi invariants domain, konkurensi data, dan simulasi protokol).
   - **Delegasi UI/UX Designer:** Segala bentuk variasi estetika, layout switcher, styling, dan komponen visual diserahkan seutuhnya kepada `uiux-designer`.

3. **MANAJEMEN SIKLUS HIDUP THROWAWAY:**
   - Simpan kode spike di cabang eksperimen `prototype/<topik>` sebagai bukti empiris.
   - Dilarang keras me-merge kode spike langsung ke `main`. Ekstrak hanya logika bisnis murni yang lolos verifikasi Exit Code 0 ke kode produksi.
</PROTOTYPE_SPIKE_ENGINE>
