# Meeting Minutes — Meridian Group

This folder contains the templates and prompt for generating meeting minutes integrated with the Obsidian vault and the Meridian Group process ecosystem.

Minutes are not a historical record — they are the bridge between what was discussed and what gets done. Each minute must produce actionable checkboxes and trigger updates in the correct forms.

---

## Files

| File | Usage |
|---|---|
| [[MINUTES-template\|MINUTES-template.md]] | Base template to fill in manually or as an output structure |
| [[MINUTES-prompt\|MINUTES-prompt.md]] | Prompt for Claude: paste the transcript and generate the minutes ready for Obsidian |

---

## When to use each file?

**You have the meeting transcript** → Use `MINUTES-prompt.md`. Copy the full prompt, paste it into Claude along with the transcript, and you will get the formatted, ready-to-use minutes.

**You are taking live notes during the meeting** → Use `MINUTES-template.md` directly as a base to write in real time.

**You want to review the expected structure of minutes** → `MINUTES-template.md` is the reference.

---

## Supported Meeting Types

| Type | Obsidian Tag | Features |
|---|---|---|
| Operational / Early Bird | `#reunion/operativa` | Multiple projects, blockers, checkboxes per area |
| Sprint Planning | `#reunion/sprint-planning` | Sprint commitments, capacity, goal |
| Sprint Review | `#reunion/sprint-review` | Velocity, demo, sponsor feedback |
| Retrospective | `#reunion/retro` | Good / Bad / Changes + improvement actions |
| Steering / Direction | `#reunion/steering` | Portfolio, executive decisions |
| Client Meeting | `#reunion/cliente` | Agreements, scope changes, FOR triggers |
| One-on-one | `#reunion/1on1` | Individual commitments, follow-up |

Additional sections for Sprint Planning, Review, Retro, and Steering are available as commented blocks inside `MINUTES-template.md`.

---

## Key Conventions

**People:** Always use `[[First-Last]]` (WikiLink to `People/`), never `@name`. This creates automatic backlinks from team member profiles.

**Projects:** Use `[[Project-Name]]` to link to files in `Projects/`.

**Project traffic light:** Consistent with [[SOP-004-project-control-and-tracking|SOP-004]]:
- 🟢 In control — No active risks
- 🟡 At risk — Manageable deviations
- 🔴 Critical — Requires escalation

**Checkboxes:** Fixed format → `- [ ] [[Responsable]]: [verb] [object] [context] 📅 YYYY-MM-DD`

**Urgency:** `🔥` only if deadline is today or tomorrow. `🚨` for active blockers.

---

## The Triggers Section

The `🔗 Triggers` section at the end of each minute is mandatory. It connects what came up in the meeting with the forms where it must be formally recorded:

| If it came up in the meeting... | Form to update |
|---|---|
| New risk | [[FOR-008-risk-matrix\|FOR-008]] |
| Active blocker or issue | [[FOR-010-issue-log\|FOR-010]] |
| Scope / date / cost change | [[FOR-009-change-request\|FOR-009]] |
| Bug or defect | [[FOR-006-QA-matrix\|FOR-006]] |
| Weekly report (Monday) | [[FOR-007-weekly-status-report\|FOR-007]] |
| Change in requirements | [[FOR-003-requirements-matrix\|FOR-003]] |
| New project identified | [[FOR-001-project-sheet\|FOR-001]] |
| Role changes in the team | [[FOR-014-RACI-matrix\|FOR-014]] |

Without this section, knowledge stays trapped in the minutes and the system's forms do not get updated.

---

## Where to Save Generated Minutes

Minutes are not saved here — this folder only contains the templates. Generated minutes go into the Calendar plugin's daily note or a dedicated folder:

```
Knowledge-Base/
└── Meetings/
    └── YYYY/
        ├── YYYY-MM-DD Operational Early Bird.md
        ├── YYYY-MM-DD Sprint Planning S[N] [Company].md
        └── YYYY-MM-DD Meeting [Client or Topic].md
```

Naming convention: `YYYY-MM-DD [Type] [Company or Project].md`

---

## Useful Searches in Obsidian

With well-structured minutes you can search:

- `tag:#reunion/operativa` — All operational / Early Bird meetings
- `tag:#company/fintrust` — Everything related to Fintrust
- `[[David-Carver]]` in backlinks — Meetings where they appear + their pending items
- `[[FOR-008]]` in backlinks — Minutes that generated a risk to register
- `- [ ]` global — Consolidated list of all open pending items (Tasks plugin)
- `🔥` — Urgencies across the vault

---

## Related Links

- [[Processes/README]] — Project management SOPs (SOP-004 Tracking, SOP-008 Communication)
- [[Templates/project-templates/README]] — FOR forms triggered by minutes
- [[Organization/People/README]] — People directory for WikiLinks
- [[Projects/README]] — Active projects in the ecosystem
- [[START-HERE]] — Vault entry point
