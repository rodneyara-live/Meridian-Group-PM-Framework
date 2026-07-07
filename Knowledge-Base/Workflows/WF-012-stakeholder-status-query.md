---
type: workflow
code: WF-012
title: "Project Status Query — Stakeholder Mode"
author: "[[Rodney-Ramirez]]"
date: 2026-05-18
tags: [workflow, query, stakeholder, read-only]
---

# WF-012 — Project Status Query (Stakeholder Mode)

> **Purpose:** Allows any team member — sponsor, area lead, collaborator — to check a project's status without needing to be the PM or know the vault structure. Claude reads, synthesizes, and delivers a clear status sheet. **This workflow is read-only. It does not write anything to the vault.**

---

## Triggers — when this WF applies

Applies when someone who is not the PM asks in natural language about a project's status. Examples of phrases that trigger it:

- *"How's the mass mailing project going?"*
- *"Give me an update on PR-7-03"*
- *"What's pending on IE-1-1-3?"*
- *"What's been happening with Fintrust's Odoo lately?"*
- *"What are the active blockers for project X?"*
- *"Who has pending items on PR-7-03?"*
- *"When was the last meeting for this project?"*
- *"What's the estimated completion date?"*
- Any question about status, progress, blockers, actionables, or recent history of a project.

---

## Steps executed by Claude

### Step 1 — Identify the project

Claude resolves the mentioned name or code to the correct folder in `Projects/`. Accepts:
- Exact code: `PR-7-03`, `IE-1-1-3`
- Partial name: *"the mass mailing one"*, *"Fintrust's CRM"*, *"the IMPOSDOM one"*
- Sponsor or PM name: *"Veronica's project"* → searches for projects where she appears in the Logbook

If ambiguous (more than one project could match), Claude presents the candidate list and asks which one.

### Step 2 — Verify confidentiality

Claude reads the `confidentiality` field in the `Logbook.md` frontmatter before delivering any information:

| Level | Claude's action |
|---|---|
| `C1` | Delivers the full Status Sheet |
| `C2` | Delivers the Status Sheet and states: *"This project is classified as strategically sensitive (C2). Handle the information with discretion."* |
| `C3` | Does not deliver project details. Responds: *"This project is confidential (C3). To access its status, contact the PM directly."* |

### Step 3 — Read the sources

Claude reads in this order:

1. **`Logbook.md`** — frontmatter (status, completion, dates, blockers) + `## 📌 Current Status` section + the last 3 history entries.
2. **Recent minutes** — the last 2 minutes in the project's `Minutes/`, if they exist.
3. **`FOR-015`** (optional) — only if the question is specifically about tasks or progress percentages.

### Step 4 — Deliver the Status Sheet

Claude produces the **Status Sheet** with the standard format defined below. The tone is executive and direct — no vault jargon, no file paths, no internal mechanism exposure.

---

## Output format — Status Sheet

```
## 📋 Status Sheet — [Project Name] (`[Code]`)

| | |
|---|---|
| **Status** | [frontmatter status] |
| **Completion** | [progress bar] [%] |
| **PM** | [name] |
| **Estimated closure** | [revised_end_date] |
| **Last update** | [last event date] |

### Current situation
[Paragraph from ## 📌 Current Status of the Logbook, in direct language]

### Active blockers
[Blocker list — or "No active blockers" if none]

### Recent movements
- [Summary of the most recent Logbook entry]
- [Summary of the second most recent entry]
- [Summary of the third most recent entry]

### Pending actionables
[List of uncompleted next steps (open checkboxes) from recent entries, with responsible person and date]

---
*Source: Vault Logbook · updated [last event date]*
```

---

## Query variants

In addition to the full sheet, Claude answers specific questions:

| Question | What Claude does |
|---|---|
| *"Who has pending items on this project?"* | Lists uncompleted next steps, grouped by responsible person |
| *"When was the last meeting?"* | Searches for the most recent minutes and reports date, participants, and topic |
| *"What was agreed in the last meeting?"* | Summarizes the latest available minutes |
| *"Is it blocked?"* | Responds directly whether there are active blockers and what they are |
| *"Is it on schedule?"* | Compares `revised_end_date` with today's date and reports any deviation |
| *"Give me the project history"* | Lists all Logbook entries in reverse chronological order with one bullet each |

---

## Restrictions — what this WF does NOT do

- **Does not modify any file.** Not Logbook, minutes, FOR-015, or any other.
- **Does not create actionables.** If the stakeholder wants to register a pending item, they must ask the PM.
- **Does not make decisions.** If the question requires judgment ("should the completion date be moved?"), Claude reports the relevant data and clarifies that the decision is the PM's.
- **Does not access information from other projects** unrelated to the query.
- **Does not share C3 information** under any circumstances, regardless of who asks.

---

## Interaction example

> **Stakeholder:** How's the mass mailing project with IMPOSDOM going?

**Claude internally executes:** identifies PR-7-03 → verifies C1 → reads Logbook and latest minutes → generates sheet.

> **Claude responds:**
>
> ## 📋 Status Sheet — Mass Mail Collection Prototype (`PR-7-03`)
>
> | | |
> |---|---|
> | **Status** | 🟣 In progress |
> | **Completion** | ▓▓▓▓░ 78% |
> | **PM** | Rodney Ramirez |
> | **Estimated closure** | 2026-07-11 |
> | **Last update** | 2026-05-07 |
>
> ### Current situation
> The final requirements refinement was completed in the May 7 demo. The IMPOSDOM return logic is agreed: it operates 100% manually, without CSV; letters that do not come back physically are assumed delivered, and Joaquin Sarmiento uses the scanner to bulk update returns. Critical pending: Veronica is negotiating with IMPOSDOM to explore whether they can provide CSV in the future. There is a letter QR that currently leads nowhere — the fix is assigned in the app project (PR-7-18).
>
> ### Active blockers
> - Veronica in negotiation with IMPOSDOM to obtain CSV delivery confirmation (pending since 2026-05-09)
> - Colipos Dom: pending resolution, no owner defined
>
> ### Recent movements
> - **07-may** — Final refinement demo completed. IMPOSDOM confirmed as 100% manual. Return flow agreed.
> - **05-may** — Early Bird: refinement meeting scheduled for that day. Next step: business process.
> - **27-apr** — Scope redefined: project split into 3 (PR-7-03 letters, PR-7-15 visits, PR-7-18 app). FOR-003 updated to v1.3.
>
> ### Pending actionables
> - **Veronica:** Contact IMPOSDOM to negotiate CSV delivery confirmation 📅 2026-05-09
> - **Rodney Ramirez:** Register and escalate Colipos Dom pending item 📅 2026-05-09
>
> ---
> *Source: Vault Logbook · updated 2026-05-07*

---

## Operational notes

- If the vault does not have a Logbook for the mentioned project, Claude informs this and suggests the PM create the project record.
- If the Logbook exists but has not been updated in more than 3 weeks, Claude delivers the sheet with a note: *"⚠️ This information has not been updated in over 3 weeks. Verify with the PM if the status is still current."*
- This WF can be invoked by anyone with Cowork access, not just the PM.

---

*WF-012 · Meridian Group Vault · [[START-HERE]] · [[Knowledge-Base/Workflows/README]]*
