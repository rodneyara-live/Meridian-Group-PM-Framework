---
type: workflow
code: WF-002
tags: [workflow, logbook, fors, task-plan]
updated: 2026-06-01
---
# WF-002 — Logbook and FORs

> Covers the creation and updating of the Logbook, FOR-015 (task plan), and FOR-007 (weekly report). The Logbook is the source of truth for all dashboards — errors in its frontmatter make the project invisible.

---

## A. Canonical frontmatter of `Logbook.md`

```yaml
---
type: log
project: "IE-X-X-X"
project_name: "Project Name"
company: "[[Company]]"
priority: P1
completion: 0%
baseline_date: "To be defined"
planned_end_date: "To be defined"
revised_end_date: "To be defined"
pm: "[[Rodney-Ramirez]]"
status: "⚪ To be defined"
last_event: "Brief description of the last known event."
confidentiality: "C1"
tags: [logbook]
# Optional GitHub fields — Innovation projects only:
# github-repo:
# origen: innovacion-github
# github-last-sync:
---
```

### YAML rules — no exceptions

| Rule | Correct | Incorrect |
|---|---|---|
| Text fields in double quotes | `project_name: "Odoo CRM"` | `project_name: Odoo CRM` |
| `project` with quotes | `project: "IE-1-1-3"` | `project: IE-1-1-3` |
| `status` with quotes and exact emoji | `status: "🟣 In progress"` | `status: 🟣 In progress` |
| `tags` inline, never block | `tags: [logbook]` | `tags:` + newline + `  - logbook` |
| ISO dates without quotes | `planned_end_date: 2026-04-30` | `planned_end_date: "2026-04-30"` |
| Undefined dates as string | `planned_end_date: "To be defined"` | empty field or `—` |
| `completion` with `%`, no quotes | `completion: 67%` | `completion: "67%"` |
| `priority` without quotes | `priority: P1` | `priority: "P1"` |
| `confidentiality` with quotes — **never absent** | `confidentiality: "C1"` | field omitted or empty |
| No fields outside the standard | Only spec fields + optional GitHub | `strategic_pillar:` or others |

**Valid values for `status`** (copy with exact emoji — exact string match, not just "has emoji"):
`"⚪ To be defined"` · `"🔵 Not started"` · `"🟣 In progress"` · `"⏸️ Paused"` · `"🏆 Showcased"` · `"❌ Canceled"`

> ⛔ Do not invent variants (`"🟡 In execution"`, `"✅ Closed"`, etc.). Dashboards filter with `contains(status, "exact text")` — any variant, however reasonable it seems, renders the project invisible in all dashboards with no visible error. Before writing a `status` outside this list of six, stop and use the appropriate one.
>
> `"❌ Canceled"` is a terminal state — it indicates that management formally decided the project will not continue. It is not used for temporary pauses (use `"⏸️ Paused"` for that). See the full cancellation protocol in `START-HERE.md` → "Cancel a project" section.

**Valid values for `priority`:**
`P1` (PE1, PE3) · `P2` (PE2, PE5) · `P3` (PE4, PE6, PE7/PR-7)

**Valid values for `confidentiality`** (mandatory, never omitted):
`"C1"` (default — general public) · `"C2"` (strategically sensitive) · `"C3"` (maximum confidentiality). See full levels in `START-HERE.md` → "Project confidentiality" section. A missing or empty field means the project disappears from Tactical Early Bird, Operational Early Bird, and Weekly Report — with no warning.

---

## A.1 Before creating a new project folder — mandatory check

> This check prevents the most common cause of duplicate projects in the vault: two different folders for the same code because nobody verified it already existed.

1. **Search for the code across the entire vault** before creating the folder (`grep -r "IE-X-X-X" .` or `grep -r "PR-7-XX" .`, or review [[Dashboards/Dashboard-Indice-Proyectos]] and `Projects/README.md`). If the code already has a folder in `Projects/` or `Archive/Projects/`, **do not create a second one** — use the existing one.
2. If the scope is different but related to an existing project, first evaluate whether it is truly a new project or a phase/front of the same project (see criteria in `START-HERE.md`). When in doubt, ask the PM before creating the folder.
3. When copying `_PROJECT-TEMPLATE`, verify that the resulting frontmatter has the 3 fields that are most often omitted by mistake: `status` (one of the 6 exact values), `confidentiality` (never empty), and `project` (unique code, not reused).

---

## B. Update the Logbook post-meeting (three parts)

### Part A — Frontmatter
Update `completion`, `status`, `last_event` (1 sentence, max ~120 chars), and dates if they change.

### Part B — `## 📌 Current Status`
Replace the existing paragraph with the project's current status. 3–5 sentences: what is happening, active alerts, next relevant milestone. It can be the executive summary of the new History entry or an edited version by the PM.

### Part C — New entry in `## History` (at the top)

```
## [emoji] [YYYY-MM-DD] — Most important event or milestone headline

**Status:** [lifecycle emoji] [text] · **Completion:** XX%

**Executive summary:** One sentence that any executive can read and understand the status.

**What happened:**
Narrative of what has occurred since the last entry.

**Active blockers:**
- 🔴 [Critical blocker] — [[Responsible]] 📅 YYYY-MM-DD
- 🟡 [Minor blocker]
- None.

**Next steps:**
- [ ] [[Responsible]]: Concrete action 📅 YYYY-MM-DD

**Related minutes:** [[Minutes/YYYY-MM-DD-type]]
```

> The next steps in the Logbook are **internal** project tracking — they do not carry dashboard tags (`#action`, `#PR-...`, `#resp/`).

---

## C. Generate FOR-015 (task plan)

**Typical invocation:** *"Generate the FOR-015 for [project]"*

**Required inputs:**
- FOR-002 Project Charter (or FOR-001 Project Sheet)
- FOR-003 Requirements Matrix (if it exists)
- Discovery/planning transcripts or minutes
- Number of milestones agreed with the sponsor

**FOR-015 frontmatter — only 4 fields:**

```yaml
---
type: task-plan
project: "IE-X-X-X"
project_name: "Project Name"
tags: [task-plan]
---
```

⛔ No status, completion, dates, or company fields. If they appear, delete them. Dashboards read the Logbook, not FOR-015.

**Rules:**
- Concrete and verifiable tasks (avoid "Review X" without context)
- Responsible person with WikiLink on each task
- Realistic dates based on transcripts/minutes
- `completion` = simple average of all task percentages — record in the **Logbook**'s `completion` field
- Claude calculates and proposes the percentage; the PM is responsible for the number being correct

**Filename:** `FOR-015_[Code]_[Project-Name]_task-plan.md`

> ⛔ Never use the generic template name (`FOR-015-task-plan.md`). Always use the full name with project code.

**Verify available numbering** in `Knowledge-Base/Templates/project-templates/README.md` before assigning a number to a new FOR.

When generating FOR-015 for a new project, also create `Logbook.md` with complete canonical frontmatter (Section A of this WF).

---

## D. Generate FOR-007 (weekly status report)

**Typical invocation:** *"Generate the FOR-007 for [project] for the week of [date]"*

- The "% Progress" comes from the **Logbook**'s `completion` field (calculated from individual FOR-015 percentages).
- If there is no FOR-015, the PM estimates and documents it as an estimate.
- FOR-007 takes the % from the Logbook — never the other way around.

**Filename:** `FOR-007_[Code]_[Project-Name]_weekly-status-report-[period].md`

---

## Last step — Commit and push

```bash
cd "/path/to/vault/Meridian-Group-Projects-Vault"
git add -A
git commit -m "feat([code]): logbook updated + [FOR created if applicable]"
git push
```
