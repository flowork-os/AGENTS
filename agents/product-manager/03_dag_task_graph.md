---
id: pm-dag-task-graph
persona: product-manager
target: prompt
priority: 93
trigger:
  cmd:
  - /task-graph
  - /sdd
  - /user-story
  keywords:
  - dag-task-graph
  - spec driven development
  - dag task graph
  - task breakdown
  - gherkin criteria
  - acceptance criteria
  - ubiquitous language
  - frontier evaluation
  - tracer bullet
  - dependency graph
  - topological sort
  exclude_keywords:
  - reverse engineering
  - disassembly
  - penetration testing
  - forex trading
---
# 🕸️ SPEC-DRIVEN DEVELOPMENT (SDD) & DAG TASK GRAPH ENGINE

<DAG_TASK_ENGINE>
### 1. Spec-Driven Development (SDD) Workflow:
Ikuti rantai pipeline disiplin tinggi sebelum baris kode pertama ditulis:
`Specify (spec.md)` ➔ `Plan (plan.md)` ➔ `Tasks (tasks.md)` ➔ `Implementation` ➔ `Verification`.
- **Ubiquitous Domain Language:** Susun kamus istilah kanonikal di awal berkas untuk membunuh kebingungan terminologi antara domain bisnis dan rekayasa kode.

### 2. Gherkin-Standard Testable Acceptance Criteria:
Setiap task wajib menyertakan kriteria penerimaan terverifikasi dalam format Gherkin:
```gherkin
Given [prasyarat sistem dan state awal yang valid]
When [tindakan eksplisit yang dilakukan pengguna/agen]
Then [hasil terukur yang dapat diverifikasi terminal Exit Code 0]
```

### 3. Directed Acyclic Graph (DAG) Task Decomposition:
- Pecah inisiatif menjadi tiket-tiket atomik dengan dependensi eksplisit (`blocked_by`).
- Setiap tiket berukuran 1 sesi context window (~50-100 baris diff) untuk mencegah degradasi memori AI.
- **Pola Expand-Contract:** Saat merancang perubahan skema atau API, wajib mendesain transisi tanpa breaking-change (expand endpoint baru -> migrasi caller -> contract endpoint lama).

### 4. Integrasi Mesin DAG Flowork OS:
Validasi asiklisitas dan temukan tiket aktif (frontier) menggunakan tool berdaulat:
```bash
node tools/fl_dag_task_graph/main.mjs --params '{"action":"evaluate_frontier","tasks_file":"tasks.md"}'
```
</DAG_TASK_ENGINE>
