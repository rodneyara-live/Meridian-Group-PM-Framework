---
type: workflow
code: WF-006
tags: [workflow, executive-summary, portfolio]
updated: 2026-04-19
---
# WF-006 — Weekly Portfolio Executive Summary

> **Invocation:** *"Prepare the executive summary for the week of [start date] to [end date]. [Optional: I want to highlight [project]. Attached calendar screenshot.]"*
>
> **Output:** `Weekly-Executive-Summary-Week-[NN]-[YYYY-MM-DD].md` in `Reportes-Semanales/`
> **Required inputs:** week to cover (start and end dates). Optional: projects to highlight, upcoming week calendar screenshot.

> ⚠️ This flow is **read-only + synthesis**. It does not modify any `Logbook.md`. If an outdated logbook is detected during collection, notify the PM but do not modify it here.

---

## Phase 1 — Orientation

**Step 1.1 — Read the Portfolio Logbook**
Read `[[Cadences/Madrugador-Tactico/Logbook-Portafolio]]`. It is the starting point for understanding what was on the radar before the week to be covered.

---

## Phase 2 — Data collection

### Step 2.1 — Identify projects with movement

> ⚠️ **Critical anti-pattern:** Early Birds are a **partial view** of the portfolio — they only cover the projects prioritized in that session. Using them as the primary source produces systematic omissions. They are a **complementary** source.

**Mandatory mechanism — full sweep before reading any minutes:**

1. Read the frontmatter of **every** `Logbook.md` in all `Projects/` folders.
2. Check if the `last_event` field falls within the requested range.
3. Build the list of projects with movement **only from this sweep**.
4. Then read the Early Birds to complement.

**Inclusion criteria** (any of these):
- `last_event` in the `Logbook.md` frontmatter falls within the range
- `Logbook.md` has a History entry with a date within the range
- There are minutes in `[project]/Minutes/` with a date within the range

> Project without `Logbook.md` with complete frontmatter = invisible in dashboards. Notify the PM if detected.

### Step 2.2 — Collect data per project

For each project with movement:

| Data | Source |
|---|---|
| Current % completion | `Logbook.md` frontmatter → `completion` |
| Lifecycle status | `Logbook.md` frontmatter → `status` |
| Last event | `Logbook.md` frontmatter → `last_event` |
| What happened this week | `Logbook.md` — **History entries within range** (main narrative source) |
| Complement | Individual project minutes in `[project]/Minutes/` within range |
| Current blockers | "Active blockers" section of the latest History entry |
| Next steps | "Next steps" section with open checkboxes |

> ⚠️ `## 📌 Current Status` is background context, **not** the narrative. The narrative is built from History entries within the range.

### Step 2.3 — Review weekly minutes

In this order:
1. `Cadences/Madrugador-Tactico/Minutes/` — portfolio decisions (Monday)
2. `Cadences/Madrugador-Operativo/Minutes/` — technical standup (Tuesday and Friday)
3. `Projects/[project]/Minutes/` — for each project with movement that has minutes in range

### Step 2.4 — Classify by movement magnitude

| Level | Criterion this week | Treatment in the report |
|---|---|---|
| A — Major milestone | Go-live, phase closure, delivery, formal approval | Full narrative (own subsection) |
| B — Dense week | 2+ meetings in range, or `completion` advanced ≥10 pp | Full narrative (own subsection) |
| C — Single event | 1 meeting or 1 event, with or without blockers | 3–5 bullets in "Other projects with movement" |
| D — No movement | No entries in range in Logbook or minutes | Secondary table only, at end |

If the PM provided "projects to highlight", promote them one level (C→B, B→A).

> ⚠️ The absence of a 🔴 blocker **does not lower a project's level**. Level D is exclusively for projects with no recorded activity in the range.

### Step 2.5 — Coverage verification ⛔ MANDATORY

> Do not proceed to Phase 3 without this table. Omitting it invalidates the process.

Produce and verify that **all** `Projects/` folders are classified:

| Project | `last_event` in range | Source detected | Assigned level |
|---|---|---|---|
| IE-X-X-X — Name | ✅ / ❌ | Logbook / Early Bird minutes / Project minutes | A / B / C / D |

Rules:
- Every project with `last_event` in range → level A, B, or C. Never D.
- A level D project with `last_event` in range indicates a sweep error — reclassify.
- The table must list **all** projects in `Projects/`. If the row count is less than the number of folders, the sweep is incomplete.

---

## Phase 3 — Writing

Use the template `[[Knowledge-Base/Templates/TEMPLATE-weekly-executive-summary]]`.

**Document structure:**

| Section | Content | Position |
|---|---|---|
| Week balance | 2–3 paragraphs — the portfolio's "headline" for the week | 1 — opening |
| Traffic light — with movement this week | Table with Level A, B, and C projects | 2 |
| Urgent decisions and blockers | Table: blocker, project, responsible, deadline | 3 |
| Key things to monitor | Numbered list 5–10 items for the upcoming week | 4 |
| Rest of portfolio — no movement | Compact table with Level D projects and current status | 5 |
| *Signature + separator* | `*Meridian Group Vault…*` + `---` + `> 📎 Elaboration…` | 6 |
| Active projects this week | Subsection per Level A and B project | 7 |
| Other projects with movement | 3–5 bullets per Level C project | 8 |

**Style rules:**
- Project and person names always with WikiLinks
- Week balance: **2–3 separate paragraphs** each with a central idea. A single text block is a formatting error.
- Each Level A/B project subsection: **what happened → current blockers → urgent pending item**
- Level C bullets reflect **specific events from that week** — not a general project description
- 🔴 blockers: prevent technical progress or have immediate financial consequences. 🟡: situations under active control
- ⛔ Building narrative by copying `## 📌 Current Status` is prohibited — that section is the general status, not what happened this week

---

## Phase 4 — Save

```
Weekly-Executive-Summary-Week-[NN]-[YYYY-MM-DD].md
```
- `[NN]` = ISO week number (e.g., `16`)
- `[YYYY-MM-DD]` = preparation Sunday or Early Bird Monday date
- **Location:** `Reportes-Semanales/` at the vault root

---

## Variations

**No upcoming week calendar:** omit agenda section. Mention: *"Calendar not available at time of preparation."*

**Intra-week cut (board meeting):** same flow with reduced range. Add to title: `· Cut [YYYY-MM-DD]` and explanatory note in the balance.

**Week with extended holidays:** mention the reduced operational window in the balance. Prioritize blockers that advance or expire despite the holiday.

---

## Last step — Commit and push

```bash
cd "/path/to/vault/Meridian-Group-Projects-Vault"
git add -A
git commit -m "docs(reports): executive summary week [NN]-[YYYY]"
git push
```

---

## References
- [[Knowledge-Base/Templates/TEMPLATE-weekly-executive-summary]] — Output document template
- [[Cadences/Madrugador-Tactico/Logbook-Portafolio]] — Portfolio historical traffic light
- [[SOP-004-project-control-and-tracking|SOP-004]] — Control and tracking of individual projects
