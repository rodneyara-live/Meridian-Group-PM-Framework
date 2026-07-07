---
type: workflow
code: WF-001
tags: [workflow, minutes, transcripts]
updated: 2026-06-29
---
# WF-001 — Process Transcription → Generate Minutes

> **Typical invocation:** *"Process today's Early Bird transcription"* · *"Generate the minutes for this meeting"* · *"I have a transcription, generate the minutes"*

---

## Step 0 — Locate the transcription

- If the PM attached or pasted the transcription directly: use that.
- If the PM did not attach it: look in `Transcripciones-WIP/`. If there is more than one file, list them and ask the PM which one corresponds.
- If `Transcripciones-WIP/` is empty and the PM did not attach anything: stop and ask for the transcription.

### Auto-fetch (WF-014)

If the PM indicates they have not had time to download Teams transcripts, or if there are no VTT files in `Transcripciones-WIP/` but there are recent unprocessed meetings, remind the PM they can run `python _Vault/scripts/get_teams_transcripts.py` from the Windows VM to automatically download transcripts from the last 7 days (see [[WF-014-teams-transcript-autofetch]]).

---

## Step 0.5 — Correct transcription with vocab.json

Before processing, read `_Vault/vocab.json` and apply the substitutions from the `corrections` section to the raw transcription text. Also apply the contextual rules from `context_hints`. This normalizes systematic errors from the automatic transcriber (e.g., "odu" → "Odoo", "fintrust" → "Fintrust"). Do not modify the JSON or the worker script.

---

## Step 1 — Identify context

- If the file does not indicate a date, the PM must provide the meeting date. Note it clearly in the minutes.
- Identify the project(s) discussed.
- If there is no existing project: determine if it is discovery or initiation. For discovery/initiation, record in the minutes that the session is exploratory; do not move to a project folder until the code exists.
- If it is a multi-project meeting (≥ 2 projects): apply the **Multi-project meeting** validation flow before writing anything (see START-HERE).

---

## Step 2 — Generate the minutes

Use the full prompt in [[Knowledge-Base/Templates/meeting-minutes/MINUTES-prompt]].

**Mandatory formatting rules:**
- WikiLinks `[[First-Last]]` for people — never @mentions or plain text
- The `## 📋 Actionables from This Meeting` section goes **before** the Triggers
- Meeting scheduling commitments go in `## 📌 Next Meetings / Follow-up Commitments` with full tags — **do not** transcribe them to `## 📋 Actionables`
- Each actionable carries the three mandatory tags: `#IE-X-X-X` or `#PR-7-XX`, `#resp/First-Last`, `#action`

---

## Step 3 — Minutes destination

| Meeting type | Destination folder for minutes |
|---|---|
| Tactical Early Bird | `Cadences/Madrugador-Tactico/Minutes/` |
| Operational Early Bird | `Cadences/Madrugador-Operativo/Minutes/` |
| Single-project meeting | `Projects/[Project-Code]/Minutes/` |
| Multi-project meeting | PM indicates the folder; if not indicated, use the meeting folder (Early Bird) or the main project's folder |

---

## Step 4 — Move the transcription

| Meeting type | Destination folder for transcription |
|---|---|
| Tactical Early Bird | `Cadences/Madrugador-Tactico/Transcripciones/` |
| Operational Early Bird | `Cadences/Madrugador-Operativo/Transcripciones/` |
| Single-project meeting | `Projects/[Code]/Transcripciones/` |
| Multi-project meeting | PM indicates destination; if not, Early Bird or main project folder |

> Keep the original filename when moving. If it was already in the correct folder, do not move.

---

## Step 5 — Update Logbooks

Identify **all** projects with movement — not just those that generated actionables. Every mentioned project (status, decision, blocker) requires an entry in its `Logbook.md`.

For each project with movement, apply the [[WF-002-logbook-and-FORs]] flow:
- Update frontmatter: `completion`, `status`, `last_event`, dates if they change
- Replace the `## 📌 Current Status` section
- Add a new entry to the History at the top

> ⚠️ **The project `README.md` is not touched.** Never post-meeting.

---

## Step 6 — Closing checkpoint (meetings with more than one project)

Before finishing, produce this table:

| Project | Logbook written | Current Status updated | `last_event` frontmatter |
|---|---|---|---|
| IE-X-X-X — Name | ✅/❌ | ✅/❌ | ✅/❌ |

If it does not have a `Logbook.md` with valid frontmatter, notify: "Project X does not have a complete Logbook — it will not appear in the dashboards."

> FOR-015 (task plan) is optional and does not affect dashboards. It may or may not exist. Only mention it if the PM explicitly requested it.

---

## Last step — Commit and push

```bash
cd "/path/to/vault/Meridian-Group-Projects-Vault"
git add -A
git commit -m "feat([project-code]): minutes [YYYY-MM-DD] + logbook"
git push
```
