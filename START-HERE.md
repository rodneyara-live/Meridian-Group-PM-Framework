---
type: orientation
tags: [vault, navigation, start, claude-instructions]
updated: 2026-07-01
---
# Meridian Group Framework — START HERE

Entry point to the portfolio management system of the **Meridian Group** — a multi-entity professional-services holding company.

> **Disclaimer:** Company names, product names, and personal data in this repo are fictionalized to protect confidentiality. The methodology, structure, and outcomes are real.

> **Operational stack:** Obsidian (reading and dashboards) + **Cowork** (writing and management via Claude). Without Cowork, operating this vault is manual work. With Cowork, one instruction replaces an hour of administration.

---

## Folder structure

```
meridiangroup-pm-framework/
│
│  — Root files —
├── START-HERE.md              ← you are here (operational instructions for Claude)
├── README.md                  ← framework overview
│
│  — Organization —
├── Organization/
│   ├── People/                ← team profiles
│   └── Partners/              ← partners and external contacts
│
│  — Knowledge base —
├── Knowledge-Base/
│   ├── Processes/             ← numbered SOPs (for humans)
│   ├── Workflows/             ← numbered WFs (operational instructions for Claude)
│   └── Templates/             ← minute templates and project templates (FOR)
│
│  — Sample projects —
├── Sample-Projects/           ← anonymized real projects
│   ├── IE-1-1-3_Odoo-CRM-Fintrust/
│   ├── IE-3-2-3-1_File-Migration/
│   └── PR-7-16_Payment-Confirmation-Agent/
│
│  — Sample outputs —
└── Sample-Weekly-Reports/     ← weekly executive portfolio summaries
```

---

## Quick navigation

| I'm looking for… | Go to… |
|---|---|
| SOP index | [[Knowledge-Base/Processes/README]] |
| Workflow index | [[Knowledge-Base/Workflows/README]] |
| Template index | [[Knowledge-Base/Templates/README]] |
| Team directory | [[Organization/README]] |
| Odoo CRM case study | [[Sample-Projects/IE-1-1-3_Odoo-CRM-Fintrust/README]] |
| File migration case study | [[Sample-Projects/IE-3-2-3-1_File-Migration/README]] |
| Payment agent case study | [[Sample-Projects/PR-7-16_Payment-Confirmation-Agent/README]] |
| Weekly executive report sample | [[Sample-Weekly-Reports/Executive-Summary-Week-27-2026-07-03]] |

---

## Instructions for Claude

> Invariant rules — apply to **all** write operations in the vault. Procedural details of each flow are in the WF files in `Knowledge-Base/Workflows/`.

### WikiLinks — always, without exception

Every reference to people, projects, companies, or partners **must** use WikiLink. Never plain text.

- **People:** `[[Alex-Carver]]`, `[[Rodney-Ramirez]]`, `[[Sofia-Vargas]]`
- **Projects:** `[[IE-1-1-3_Odoo-CRM-Fintrust]]` or short name if context is clear
- **Companies:** `[[Meridian-Group]]`, `[[Fintrust]]`, `[[Meridian-Pay]]`
- **Partners:** `[[Partners/Corvant-Systems]]`, `[[Partners/Andira-Partners]]`

> ⚠️ **Exception: Mermaid blocks.** WikiLinks `[[...]]` silently break the Mermaid parser. Always use plain text inside diagrams.

---

### Project codes — strict format

**Strategic Initiatives (PE1–PE6):** `IE-[PE]-[OE]-[IE]` or `IE-[PE]-[OE]-[IE]-[subproject]`
**Tactical Projects (PE7):** `PR-7-[NN]`

> ⚠️ **Single separator: hyphen `-`, never period.** Periods break WikiLinks and corrupt dashboard tags.

---

### FOR document naming

**Format:** `FOR-[NNN]_[Project-Code]_[Project-Name]_[document-type].md`

| Code | Type (slug) |
|---|---|
| FOR-001 | `project-sheet` |
| FOR-002 | `project-charter` |
| FOR-003 | `requirements-matrix` |
| FOR-004 | `test-plan` or `test-plan-[milestone]` |
| FOR-007 | `weekly-status-report` or `weekly-status-report-[period]` |
| FOR-008 | `risk-matrix` |
| FOR-009 | `CR-[NNN]-[description]` (change request) |
| FOR-010 | `issue-log` |
| FOR-014 | `raci-matrix` |
| FOR-015 | `task-plan` |

> ⛔ Never create a FOR with the generic template name. Always use the full name with project code from the moment of creation.
> Check available numbering in `Knowledge-Base/Templates/project-templates/README.md` before assigning a new number.

---

### Tags for minute actionables

```
#action              ← identifies the item as actionable
#IE-X-X-X            ← project code (PE1–PE6)
#PR-7-XX             ← tactical project code (PE7)
#resp/Name           ← responsible person (e.g. #resp/Sergio-Mendoza)
#schedule-meeting    ← commitment to schedule a future meeting
```

**Standard format:**
```
- [ ] [[Responsible]]: Verb object context 📅 YYYY-MM-DD #IE-X-X-X #resp/First-Last #action
```

**Where `#action` goes:** minutes (section `## 📋 Actionables`) and Operational Backlog. **Not** in next steps of Logbook.

**Uniqueness rule:** each actionable appears **only once** in the vault. Do not repeat in the Logbook if it is already in the minute.

---

### Traffic lights — two dimensions, never mix

**Project health** (automatically calculated by DataView — Claude **never** writes 🟢🟡🔴):
- 🟢 In control · 🟡 At risk · 🔴 Out of control

**Lifecycle status** (`status` field in Logbook frontmatter — Claude does update this):
- `"⚪ To be defined"` · `"🔵 Not started"` · `"🟣 In progress"` · `"⏸️ On hold"` · `"🏆 Showcase"` · `"❌ Canceled"`

> ⛔ **Exact match, no exceptions.** Do not invent variants (`"🟡 In execution"`, `"✅ Closed"`, etc.) — the dashboards filter by exact text, and any variant makes the project invisible in all of them with no visible error.

> **Status `❌ Canceled`:** Used when management formally decides the project will not continue. The project is **not archived or deleted** — it stays in `Projects/` as a visible historical record. Its folder remains intact.

**Progress** (from `completion` of the Logbook):
`░░░░░` 0% · `▓░░░░` 1–20% · `▓▓░░░` 21–40% · `▓▓▓░░` 41–60% · `▓▓▓▓░` 61–80% · `▓▓▓▓▓` 81–100%

---

### Project confidentiality — `confidentiality` field

Every project has the `confidentiality` field in its `Logbook.md` frontmatter. **The field is mandatory from creation — never omitted or left blank.** Three possible levels:

| Level | Meaning | Visible in |
|---|---|---|
| `"C1"` | General public — **default value** | Operational Early Bird · Tactical Early Bird · Weekly Report |
| `"C2"` | Strategic sensitive | Tactical Early Bird · Weekly Report (excluded from Operational) |
| `"C3"` | Maximum confidentiality | Direct stakeholders only (excluded from both early birds and reports) |

---

### Integrity rules — Single Source

| Layer | Document | When updated |
|---|---|---|
| **Dynamic** | `Logbook.md` — frontmatter + `## 📌 Current Status` + History entry | Post-meeting, always |
| **Planning** | `FOR-015` — individual task percentages | Only when the PM updates specific tasks |
| **Static** | Project `README.md` | Only when structural data changes |

> **Golden rule:** post-meeting → update **Logbook**. FOR-015 is only touched when task percentages change. The project **README** is **never** touched post-meeting.

---

### Multi-project meetings — validate before executing

When the meeting touches ≥ 2 projects, Claude must:
1. **Present scope proposal** — projects with movement, movement type, files to touch, minute destination, projects without valid `Logbook.md` marked with ⚠️
2. **Wait for PM confirmation** before proceeding with writes
3. Execute the updates

---

## Workflow Index

For the procedural detail of each flow, read the corresponding WF file before executing.

| WF | Operation | Read before… |
|---|---|---|
| [[WF-001-process-minutes-transcription\|WF-001]] | Transcript → Minute + Logbook update | Processing any transcript |
| [[WF-002-logbook-and-FORs\|WF-002]] | Create/update Logbook · Generate FOR-015 · Generate FOR-007 | Creating a new Logbook, updating YAML, generating any FOR |
| [[WF-006-weekly-executive-summary\|WF-006]] | Weekly Executive Portfolio Summary | Preparing the Tactical Early Bird summary |
| [[WF-008-github-sync\|WF-008]] | Sync individual GitHub repos | Processing a `-github.json` (backup, explicit invocation) |
| [[WF-009-vault-integrity\|WF-009]] | Verify vault integrity | Auditing projects or preparing the Tactical meeting |
| [[WF-011-whatsapp-message\|WF-011]] | Generate WhatsApp message post-meeting with agreements and actionables | Drafting any WhatsApp message after a meeting |
| [[WF-012-stakeholder-status-query\|WF-012]] | Project status query in read-only mode (non-PM stakeholders) | When someone asks about the status, progress, or pending items of a project |
| [[WF-013-early-bird-report-html\|WF-013]] | HTML executive portfolio report to share with management | When they request the early bird to share, HTML portfolio report |
| [[WF-014-teams-transcript-autofetch\|WF-014]] | Auto-download Teams transcripts via Graph API | Before executing `Get-TeamsTranscripts.ps1` on the Windows VM |

---

## Operations without their own WF

### Register a pending item in the Operational Backlog

For tactical tasks that **do not belong to any active vault project**:

**Destination file:** `Operational-Backlog/Backlog.md` — section `🔜 Next`

```
- [ ] [[First-Last]]: Verb object context 📅 YYYY-MM-DD #PR-BACKLOG #resp/First-Last #action
```

All three tags are mandatory. Do not create FOR-015, do not create Logbook, do not add to the Matrix.

### Update dashboards

Dashboards are automatic (DataView + Tasks). **Do not modify the files in `Dashboards/` directly.**
- To update progress → modify `completion` in the project's `Logbook.md`
- To update status → modify `status` in the project's `Logbook.md`
- For actionables → check checkboxes directly in the source minutes

---

## Vault maintenance

1. **New project** → **First verify the code does not already exist** (see WF-002 section A.1; never create a second folder for an existing code) → Copy `Projects/_PROJECT-TEMPLATE` → fill static fields, **including explicit `confidentiality` and `status` from the exact list of 6 values** → generate FOR-015 (WF-002) → add to `Projects/README.md`
2. **New person** → Copy `People/_PERSON-TEMPLATE` → fill profile
3. **New partner** → Copy `Organization/Partners/_PARTNER-TEMPLATE` + contact in `Contacts/`
4. **New project minute** → WF-001 → save in `Projects/[project]/Minutes/` → WF-002 (Logbook)
5. **New SOP or FOR** → Follow existing numbering → update subfolder README

---

### Session close — mandatory commit

> **Every session with at least one write ends with commit and push.**

```bash
git add -A
git commit -m "type(scope): description"
git push
```

**Message format:** `"feat(IE-1-1-3): minute 2026-04-19 + logbook"` · `"docs(vault): update README"` · `"fix(FOR-015): fix PR-7-16 frontmatter"`. No generic messages like `"update"` or `"changes"`.

---

*Meridian Group Framework · START-HERE updated 2026-07-07*
