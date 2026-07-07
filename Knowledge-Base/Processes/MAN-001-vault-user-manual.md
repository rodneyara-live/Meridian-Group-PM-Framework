---
type: manual
code: MAN-001
title: "Meridian Group Vault User Manual"
author: "[[Rodney-Ramirez]]"
date: 2026-03-20
tags: [manual, vault, onboarding]
---

# MAN-001 — Meridian Group Vault User Manual

> **Who this is for:** Project Managers, analysts, and any team member who operates this vault. No advanced technical knowledge required. It does require careful reading.
>
> **Who this is NOT for:** AI tools. Claude has its own context document (`.claude/CLAUDE.md`). This manual is for beating hearts.

---

## Fundamental requirement: Cowork

This system **requires Cowork** (Anthropic's desktop application with Claude agent) to function sustainably. Without Cowork, operating this vault becomes manual maintenance of dozens of interconnected files — exactly what this system exists to avoid.

With a regular chat interface, each operation requires you to copy, paste, save, link, and verify manually. With Cowork, you give Claude direct access to the vault and he navigates, creates, updates, and cross-links. You provide the raw input and receive the output. The difference is not about convenience — it is about viability. A PM managing 30+ projects with a regular chat interface would need a week of administrative work that Cowork turns into a one-sentence instruction.

**Required stack:**
- **Obsidian** — vault reading interface and automatic dashboards
- **Cowork** — vault writing and management interface via Claude
- **Obsidian plugins** — see [[SETUP]] for technical requirements

---

## The interaction model

```
YOU provide the raw input
        ↓
   COWORK + CLAUDE
   reads the vault, executes, updates, cross-links
        ↓
YOU validate the output and make decisions
```

You do not copy folders. You do not paste content into files. You do not update links manually. You tell Claude what you want to work on, give him the raw material, and he does the rest inside the vault. When he finishes, he tells you what he needs from you to continue.

---

## Conventions in this manual

| Icon | Meaning |
|---|---|
| 🧑 **HUMAN ACTION** | This **cannot be delegated to Claude**. Requires your presence, your judgment, or your signature. If you do not do it, it does not happen. |
| 🤖 **COWORK** | Tell this to Claude in Cowork. He executes. |
| ✅ **VALIDATE** | Verify the output is correct. Not optional — Claude was not in your meeting. |

---

## Pattern 1 — Process a meeting

**Input you need to have:** the meeting transcript (text exported from Teams/Zoom, or your notes if there was no recording).

**What you do:**

🤖 Open Cowork and tell it something like:
> *"I have the transcript of today's Odoo CRM follow-up meeting. It is in Transcriptions/. Generate the minute, save it in Minutes/, update the Logbook, and tell me if there are any actionables that require my immediate attention."*

Claude will: read the transcript, identify participants and actionables, generate the minute with the correct format, save it in the correct project folder, update the Logbook, and list any decisions or blockers that need your eye.

✅ **You validate:** that the actionables are correctly assigned, that the recorded decisions reflect what was actually agreed, that no important nuance was lost in the transcript. Claude was not in the room — you were.

🧑 **The only thing Claude cannot do for you:** know whether what the transcript says reflects the real intent of what was said. If there was sarcasm, if someone said "yes" but meant "I'll think about it", if a date was proposed but not confirmed — you have that context.

---

## Pattern 2 — Update project progress

This is the only flow where human intervention is structural and irreplaceable, not due to Claude's limitations, but because no one else knows how much work was actually done.

🧑 **You decide the % progress for each task.** No shortcuts here. A task that is "almost ready" and has been at 90% for three weeks is a blocked task, not a task at 90%. Your professional judgment is the only valid input.

**What you do:**

🧑 Mentally or on paper, define the actual % for each task that had movement this week.

🤖 Tell Claude in Cowork:
> *"Update the FOR-015 for Odoo CRM. Tasks 1.2 and 1.3 moved to 60%, task 1.1 remains at 0% blocked. Recalculate completion, update the Logbook, and tell me if these numbers compromise the closing date."*

Claude will: update the percentages in the FOR-015, recalculate the average completion, update the `completion` field in the **Logbook** frontmatter (source of truth for dashboards), analyze whether `revised_end_date` needs to move, and give you his recommendation with the numbers.

🧑 **You decide** whether to move `revised_end_date`. Claude can recommend based on dates, but the decision of when to declare a deviation is yours. That decision moves the health traffic light on the dashboard for everyone.

---

## Pattern 3 — Open a new project

**Input you need to have:** the project charter or project sheet (FOR-002/FOR-001), transcripts of discovery sessions if they exist, and clarity on the project code and milestones agreed with the sponsor.

🤖 Tell Claude in Cowork:
> *"There is a new project: IE-2-1-1-1 Operational Quality Assurance. Sponsor: Elena Torres. I have the project charter in Documents/ and two discovery transcripts in Transcriptions/. Create the full project structure, generate the FOR-015, and add it to the portfolio."*

Claude will: create the project folder with the full standard structure, complete the README with data from the charter, generate the FOR-015 with the task plan, add the project to the Projects/README.md table, and tell you which fields need your confirmation before giving the go-ahead.

✅ **You validate:** the generated FOR-015. Dates are estimates — you know if they are realistic. The scope is what was agreed — you remember what was included and what went to the parking lot.

🧑 **The only irreplaceable thing:** confirming milestones, committed dates with the sponsor, and the assigned team. Claude can propose based on documents, but you made the commitments.

---

## Pattern 4 — Close a project and move to showcase

**Irreplaceable prerequisite:** formal sponsor acceptance. Without this, the project is not closed — it is abandoned.

🧑 Obtain sponsor acceptance (signature, email, message — whatever matches the project's formality level).

🤖 Tell Claude in Cowork:
> *"Odoo CRM was formally accepted by Elena Torres. Close the project: mark all tasks at 100% in the FOR-015, change the status to 🏆 Showcase, write the closing entry in the Logbook with the main result, and update the portfolio."*

Claude will: mark all tasks at 100% in the FOR-015, recalculate completion, change `status` and `completion` in the **Logbook** frontmatter (source of truth — not the README), write the closing entry in the Logbook, and update the Projects/README.md table.

✅ **You validate:** the closing entry in the Logbook. It is the historical record of the project's result — it deserves you to read it.

---

## Pattern 5 — Manage the portfolio (weekly view)

🤖 Before Monday's Tactical Early Bird:
> *"Give me a portfolio briefing for today's Early Bird. Which projects have yellow or red traffic lights, which have active blockers, and what decisions are pending from management."*

Claude reads all Logbooks, dashboards, and recent minutes, and delivers an executive summary ready for the meeting.

🤖 After the Early Bird:
> *"Transcript of today's Early Bird in Tactical-Early-Bird/Transcriptions/. Generate the minute, update the Portfolio-Logbook, and execute any status changes that were decided."*

🧑 **The irreplaceable part:** being in the meeting, understanding the political context of each decision, and confirming to Claude which status or priority changes are definitive vs. what was just exploratory conversation.

---

## Pattern 6 — Register a pending item in the Operational Backlog

For tactical or strategic tasks that do not belong to a formal project — or that cut across several — there is the Operational Backlog. It has no closing date, no FOR-015, and does not appear in the Early Bird. Its items do appear in all three actionable dashboards.

**Input you need to have:** the pending item in words, who is responsible, and an approximate deadline.

🤖 Tell Claude in Cowork:
> *"Add to the Operational Backlog: Elena Torres must deactivate the corporate ChatGPT — include reviewing which projects have other members before the shutdown. Date: April 15."*

Claude will: add the item to the `Operational-Backlog/Backlog.md` file with the correct format, including the three mandatory tags (`#PR-BACKLOG`, `#resp/First-Last`, `#action`), in the `🔜 Next` section.

✅ **You validate:** that the responsible person and the date are correct. Once saved, the item automatically appears in the actionable dashboards.

🧑 **The only irreplaceable thing:** deciding the relative priority of the item within the backlog. Position in the list is priority — items at the top are executed first. Claude can suggest where to insert it, but you define the hierarchy.

> **Note:** Backlog items live **only** in `Backlog.md`. Do not create backlog actionables in minutes or other vault files.

---

## What is yours and only yours

With Cowork, the list of what no system can do for you is reduced to this:

| What requires a human | Why Claude cannot replace it |
|---|---|
| Being in the meeting | Claude has no body or Teams connection |
| Defining the actual % progress of each task | No one else knows how much work was actually done |
| Deciding whether the closing date moves | Requires political and negotiation context not in the transcript |
| Formal sponsor acceptance | It is a contractual responsibility |
| Approving the generated FOR-015 | You made the commitments — you validate them |
| Strategic decisions (pause, change scope, reassign) | Require authority, not intelligence |
| Reading the closing Logbook before archiving | Deserves 2 minutes of your time |

Everything else — creating folders, generating documents, updating links, recalculating completion, moving statuses, formatting minutes, updating the dashboard — Claude does.

---

## Frequent errors

**"The dashboard does not show a project"**
→ The `Logbook.md` does not have the complete frontmatter or has the incorrect `type` field. It must be `type: log`. Tell Claude to review the Logbook frontmatter — particularly the `type`, `project`, `status`, and `completion` fields.

**"Actionables do not appear"**
→ The checkbox does not have the `#action` tag — without it the item is invisible to all dashboards. Also verify it has the project tag (`#PR-X-X-XX-X` for formal projects, `#PR-BACKLOG` for the operational backlog) and the responsible person tag (`#resp/First-Last`). Tell Claude to review the format of the corresponding file.

**"The traffic light is 🔴 but the project is doing fine"**
→ `revised_end_date` was moved at some point and was not restored. If the project returned to the original plan, tell Claude to match `revised_end_date` to `planned_end_date`.

**"I do not know what % a task is at"**
→ Ask the responsible person. If the responsible person also does not know, the problem is not the vault.

---

*MAN-001 · Meridian Group Vault · [[START-HERE]] · [[Knowledge-Base/README]] · [[SETUP]]*
