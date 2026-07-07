---
type: workflow
code: WF-009
tags: [workflow, integrity, audit]
updated: 2026-07-01
---
# WF-009 — Verify Vault Integrity

> **Invocation:** *"Verify vault integrity"* · *"Which projects have issues?"*
>
> ⚠️ **Requires MCP available.** Without MCP, this workflow cannot be executed autonomously.
>
> Claude **does not modify anything** — only reports. The PM decides what to fix and in what order. For guided spot corrections (merging duplicates, fixing a non-standard `status`, completing `confidentiality`), use WF-002 section A.1 as a reference for correct fields.
>
> Especially useful before the Tactical Early Bird or after a session involving many projects. **Before running this workflow manually, first check [[Dashboards/Dashboard-Integridad-Vault]]** — it covers live (without invoking Claude) the three most common findings in this list.

---

## What Claude verifies

| Verification | How it detects |
|---|---|
| `Logbook.md` with invalid or incomplete frontmatter | Reads frontmatter; alerts if fields are missing (`completion`, `status`, `prioridad`, `company`), dates are empty, or `status` lacks exact emoji |
| **`confidentiality` missing or empty** | Reads frontmatter of each `Logbook.md` in `Projects/` and `Archive/Projects/`; if the field does not exist or is empty, the project is invisible in Tactical Early Bird, Operational Early Bird, and Weekly Report with no visible error. Severity 🔴 Critical always. |
| **`status` outside the exact 6-value enum** | Compares the `status` value against the exact list: `"⚪ To be defined"` · `"🔵 Not started"` · `"🟣 In progress"` · `"⏸️ Paused"` · `"🏆 Showcased"` · `"❌ Canceled"`. Any variant (`"🟡 In execution"`, `"✅ Closed"`, different capitalization, different emoji) is invisible in all portfolio dashboards even if the rest of the frontmatter is correct. Severity 🔴 Critical. |
| **Duplicate project codes** | Groups all `Logbook.md` files from `Projects/` + `Archive/Projects/` by the `proyecto` field; if two or more folders resolve to the same code, they are candidates for merging (see precedents: PR-7-30→PR-7-28 and IE-2-2-2-3 from 2026-07-01). Severity 🔴 Critical — direct impact on dashboards and actionables (tags fragmented across both folders). |
| `FOR-015` with fields that should not be there (if exists) | Reads FOR-015 frontmatter; alerts if it contains `completion`, `status`, `company`, `date_*`, `strategic_pillar`, or other non-canonical fields |
| Projects in `Projects/` without an entry in `Matriz-Estrategica-2026` | Cross-references `Projects/` folders with WikiLinks in the Matrix |
| Archived projects with broken references in `Projects/README.md` / `Matriz-Estrategica-2026` | If a folder was deleted (not archived) due to consolidation, its row in README/Matrix must also be deleted — a WikiLink to a folder that no longer exists anywhere (neither `Projects/` nor `Archive/Projects/`) is a dead link |

---

## Output

Findings table with severity:

| Project | Finding | Severity | Suggested action |
|---|---|---|---|
| PR-7-XX — Name | Incomplete frontmatter — missing `company` | 🔴 Critical | Complete manually |
| IE-X-X-X — Name | Not found in Strategic Matrix | 🔴 Critical | Add WikiLink in Matrix |
| PR-7-XX — Name | `confidentiality` missing — invisible in dashboards | 🔴 Critical | Add `confidentiality: "C1"` (or appropriate level) |
| IE-X-X-X — Name | `status: "🟡 In execution"` is not one of the 6 standard values | 🔴 Critical | Correct to the closest exact value from the canonical list |
| IE-X-X-X — Name (×2 folders) | Duplicate code in two different folders | 🔴 Critical | Merge following precedent PR-7-30→PR-7-28 / IE-2-2-2-3 (2026-07-01): consolidate Logbook, move Minutes/Transcripts, delete extra folder, clean README/Matrix |
