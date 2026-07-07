# Prompt — Meridian Group Minutes Generation for Obsidian

Copy and use this prompt when you want to process a meeting transcript into minutes ready to paste into Obsidian.

---

## 🔧 Execution Prompt

```
Process this meeting transcript into compact minutes for Obsidian.
Follow these instructions exactly:

━━ VOCABULARY CORRECTION ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Before drafting, apply to the transcript text the substitutions
from `_Vault/vocab.json` → `corrections[].wrong` → `corrections[].correct`.
Also apply the `context_hints` rules. This normalizes systematic
errors from the automatic transcriber (e.g., "odu" → "Odoo", "fintrust" → "Fintrust").

━━ ECOSYSTEM AND CONTEXT ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

The meetings belong to the Meridian Group ecosystem, which operates three companies:
- **Meridian Group** — Parent company, project management and technology
- **Fintrust** — LegalTech + FinTech (Sheriff Portal, electronic invoicing, Odoo v17)
- **Meridian Pay** — Debt restructuring (Odoo v17 migration, credit scoring)

The team uses: Microsoft Planner (task management), Teams (communication),
SharePoint (documents), Clockify/Upwork (contractor hours).
Methodology: Hybrid Scrum with 2-week sprints.

━━ PEOPLE — USE WIKILINKS ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

DO NOT use @name. Always use [[First-Last]] in Obsidian WikiLink format.
Team names (use this exact format):
- [[David-Carver]] — CEO / Product Owner
- [[Rodney-Ramirez]] — Project Manager
- [[Carlos-Ruiz]] — Director of Operations
- [[Elena-Torres]] — Operations Manager
- [[Alex-Carver]] — Innovation Manager
- [[Karina-Valdez]] — Chief Financial Officer
- [[Tomas-Navarro]] — Director (sponsor of multiple projects)
- [[Sergio-Mendoza]] — Odoo Developer (contractor, Brazil)
- [[Rodrigo-Villalba]] — Technical Architect (contractor)
- [[Hugo-Pacheco]] — Judicial Specialist / UAT Lead (Fintrust)
- [[Mateo-Herrera]] — Developer (contractor, Argentina)
- [[Valeria Castro-Delrio]] — Documentation / Analysis (contractor, Argentina)
- [[Diego-Fontaine]] — Process Documentation (contractor)
- [[Carlos-Segura]] — Corvant Systems Partner (Colombia)
(For unrecognized people, use [[First-Last]] inferring from audio)

━━ PROJECTS — USE WIKILINKS ━━━━━━━━━━━━━━━━━━━━━━━━━━━

Use [[PR-X.X-XX-X_Project-Name]] or the short name [[Project-Name]] when context is clear.
Active ecosystem projects with their codes:
Fintrust:
- [[IE-1-1-3_Odoo-CRM-Fintrust]] → tag: #PR-1-2-02-1
- [[IE-1-1-4_Odoo-Accounting-Fintrust]] → tag: #PR-1-2-02-2
- [[IE-1-1-1_Judicial-Flow-Orchestrator]] → tag: #PR-3-1-03-1
Meridian Pay:
- [[IE-1-1-6-1_MIFOS-Implementation-Phase-2]] → tag: #PR-3-1-01-1
- [[IE-1-1-6-2_Odoo-CRM-Meridian-Pay]] → tag: #PR-1-1-04-2
- [[IE-1-1-6-3_Odoo-Accounting-Meridian-Pay]] → tag: #PR-1-1-04-3
Meridian Group:
- [[IE-1-2-1_Payment-Confirmation-Agent]] → tag: #PR-3-1-02-1
- [[PR-7-18_AI-Humanization]] → tag: #PR-3-1-02-2
- [[PR-7-16_Omnichannel-Collections-Strategy]] → tag: #PR-2-2-03-1
- [[IE-2-2-3-1_Cyber-Risk-Management]] → tag: #PR-3-2-02-1

━━ REQUIRED FORMAT ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Generate exactly this Markdown format:

---
type: meeting
subtype: [operational | sprint-planning | sprint-review | retro | steering | client]
company: [meridiangroup | fintrust | meridian-pay | multi-company]
project: [name if the meeting is for a specific project]
sprint: [S-N if mentioned]
date: YYYY-MM-DD
participants: [list]
tags: [meeting/subtype, company/name]
---

# 📋 [Descriptive meeting name]

**Date:** YYYY-MM-DD
**Type:** [meeting type]
**Company:** [company(ies)]
**Sprint:** S[N] (omit if not applicable)
**Participants:** [[First-Last]], [[First-Last]]

[[YYYY-MM-DD]] ← | → [[YYYY-MM-DD]]

---

## 🎯 Projects / Topics

### [[Project-Name]]

**Responsible:** [[First-Last]]

**Progress:**
- [Only relevant progress, no narrative]

**Pending:**
- [ ] [[First-Last]]: [Specific and verifiable action] 📅 YYYY-MM-DD
- [ ] [[First-Last]]: [Urgent action] 🔥

---

## 🚨 Active Blockers

- 🚨 **[[Project]]:** [Blocker] → Responsible: [[Name]] | Since: YYYY-MM-DD

---

## ✅ Decisions Made

- **[Topic]:** [Decision — who made it]

---

## 📌 Upcoming Meetings / Follow-ups

- [ ] [[First-Last]]: Schedule [meeting] about [topic] 📅 YYYY-MM-DD

---

## 📋 Actionables from This Meeting

[Consolidate ONLY the checkboxes from the "Projects / Topics" section in extended format with full tags. ⚠️ DO NOT include items from "Upcoming Meetings / Follow-ups" — those already have their tags and are NOT repeated here (vault uniqueness rule). Each item must have the project tag (#PR-X-X-XX-X), the responsible tag (#resp/First-Last) and the #action tag. If the meeting covers several projects, each item carries its project's tag. Multi-project meetings without a specific code use #multiproject.]

- [ ] [[First-Last]]: [Action exactly as the checkbox above] 📅 YYYY-MM-DD #PR-X-X-XX-X #resp/First-Last #action
- [ ] [[First-Last]]: [Urgent action] 📅 YYYY-MM-DD #PR-X-X-XX-X #resp/First-Last #action 🔥

---

## 🔗 Triggers — Update after this meeting

[Only check the ones that APPLY based on the meeting content:]
- [ ] Risk identified → [[FOR-008-risk-matrix]]
- [ ] New blocker → [[FOR-010_IE-1-1-3_Odoo-CRM-Fintrust_issue-log]]
- [ ] Scope change → [[FOR-009-change-request]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
- [ ] Bug/defect → [[FOR-006-QA-matrix]]
- [ ] New project → [[FOR-001_PR-7-16_Payment-Confirmation-Agent_project-sheet]]

━━ GOLDEN RULES FOR CHECKBOXES ━━━━━━━━━━━━━━━━━━━━━━━

Each - [ ] must comply with these rules:
1. **Self-contained**: Understood on its own, out of context, in a consolidated list
2. **Fixed format**: [[Responsible]]: [verb] [object] [context] 📅 date
3. **Action verb**: Schedule / Implement / Validate / Review / Deliver / Resolve / Present
4. **Specific**: Never "Review topic", always "Review bug in payment module null fields"
5. **Urgency**: Use 🔥 only if deadline is today or tomorrow

✅ GOOD:
- [ ] [[Rodney-Ramirez]]: Schedule meeting with Aviara Labs about Botmaker migration 📅 2025-01-10
- [ ] [[Ana-Teresa-Peguero]]: Fix null fields bug in electronic invoice 🔥 2025-01-06
- [ ] [[Euris-Mancebo]]: Present virtual agent MVP to [[David-Carver]] 📅 2025-01-07

❌ BAD:
- [ ] Follow up on topic
- [ ] Review with the team
- [ ] Pending definition

━━ GOLDEN RULES FOR ACTIONABLES ━━━━━━━━━━━━━━━━━━━━━━

The "📋 Actionables from This Meeting" section is MANDATORY in all minutes.
It is the clean consolidation of all checkboxes for automatic indexing.

⚠️ CRITICAL TAG RULE: Project tags NEVER contain a period. Use a hyphen instead of the period.
   ✅ CORRECT: #PR-3-1-02-1   ❌ INCORRECT: #PR-3.1-02-1
   Obsidian truncates the tag at the first period, leaving only #PR-3 — which breaks all queries.

Rules:
1. Include ONLY the checkboxes from the "Projects / Topics" section — NOT those from "Upcoming Meetings" (uniqueness rule: each actionable appears only once in the vault)
2. Each item carries 3 tags: #PR-X-X-XX-X (project), #resp/First-Last (responsible), #action
3. The WikiLink [[Responsible]] and the tag #resp/First-Last must be the same person
4. Do not abbreviate or paraphrase — copy the action from the original checkbox
5. If the meeting is multi-project and there is no clear code for an item, use #multiproject
6. 🔥 at the end of the item if applicable (already in the original checkbox)

✅ GOOD:
- [ ] [[Sergio-Mendoza]]: Deliver detailed roadmap with stages and dates for both milestones 📅 2026-02-14 #PR-1-2-02-1 #resp/Sergio-Mendoza #action 🔥
- [ ] [[Rodney-Ramirez]]: Align Alex with the implementation plan 📅 2026-02-21 #PR-1-2-02-1 #resp/Rodney-Ramirez #action

❌ BAD:
- [ ] Sergio: deliver roadmap #action             (no WikiLink, no project, no date)
- [ ] [[Sergio-Mendoza]]: Review roadmap #PR-1-2-02-1 (paraphrased, vague verb)

━━ WHAT TO OMIT ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Always omit:
- Greetings, welcomes, filler conversations
- Already known context that does not change anything
- Repetitions of the same thing said differently
- Comments without actionable or decision
- Technical conversations without resolution or clear task

━━ MAXIMUM LENGTH ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Maximum 1 page equivalent (≈ 50 lines of content).
If there are more than 4 projects, group the smaller ones under "Other topics" with only their checkboxes.

━━ TRANSCRIPT ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[PASTE TRANSCRIPT HERE]
```

---

## 📖 Quick Reference — Meeting Types

| Type | Tag | Key Sections |
|---|---|---|
| Early Bird / Operational | `#meeting/operational` | Projects + Blockers + Checkboxes |
| Sprint Planning | `#meeting/sprint-planning` | Sprint commitments + Capacity + Goal |
| Sprint Review | `#meeting/sprint-review` | Velocity + Demo + Sponsor feedback |
| Retrospective | `#meeting/retro` | Good / Bad / Changes + Improvement actions |
| Steering / Direction | `#meeting/steering` | Portfolio + Executive decisions |
| Client meeting | `#meeting/client` | Agreements + Scope changes + FOR triggers |
| One-on-one | `#meeting/1on1` | Individual commitments + Follow-up |

---

## 🔗 Triggers — Quick Guide

Use this guide to complete the "Triggers" section of the minutes:

| If it came up in the meeting... | Trigger |
|---|---|
| A new risk that could affect the project | → [[FOR-008-risk-matrix]] |
| An active problem / blocker | → [[FOR-010_IE-1-1-3_Odoo-CRM-Fintrust_issue-log]] |
| A request to change scope, date, or cost | → [[FOR-009-change-request]] |
| A bug or defect reported | → [[FOR-006-QA-matrix]] |
| It is Monday and a report needs to be sent | → [[FOR-007-weekly-status-report]] |
| A new project that could start | → [[FOR-001_PR-7-16_Payment-Confirmation-Agent_project-sheet]] |
| Change in who does what on the team | → [[FOR-014_IE-1-1-3_Odoo-CRM-Fintrust_RACI-matrix]] |
| Decision that changes approved requirements | → [[FOR-003-requirements-matrix]] |

---

## 💡 Search Tips in Obsidian

With this structure, you can search:

- `tag:#meeting/operational` — All operational / Early Bird meetings
- `tag:#company/fintrust` — Everything related to Fintrust
- `tag:#action` — All action items from minutes in the vault
- `tag:#PR-1-2-02-1` — All action items for the Odoo CRM Fintrust project
- `[[David-Carver]]` — All meetings where Francisco appears + their pending items
- `[[FOR-008]]` → all minutes that generated a risk to register
- `🔥` — Urgencies across the vault

For automatic consolidated views of actionables and progress, use the dashboards:
- [[Projects/Dashboard-Actionables-by-Project]] — open items by project (Tasks)
- [[Projects/Dashboard-Actionables-by-Person]] — open items by responsible person (Tasks)

---

## 📁 Where to Save Minutes

Minutes are saved in the `Minutes/` folder of the corresponding project:

```
Projects/
└── PR-X.X-XX-X_Project-Name/
    └── Minutes/
        ├── 20260213-CRM-Odoo-Plan-Review.md
        ├── 20260130-CRM-Odoo-Requirements-Workshop.md
        └── 20260204-CRM-Odoo-Requirements-Follow-up.md
```

Naming convention for project meetings: `YYYYMMDD-[Brief-Description]-[Company-Project].md` (no hyphens between date, hyphens between words)

For the **Operational Early Bird** (multi-project): save in `Cadences/Operational-Early-Bird/Minutes/` · name: `YYYY-MM-DD-[tuesday|friday].md`
For the **Tactical Early Bird** (portfolio): save in `Cadences/Tactical-Early-Bird/Minutes/` · name: `YYYY-MM-DD-monday.md`

---

*Template created for the Meridian Group ecosystem — compatible with Obsidian Calendar plugin + Tasks plugin*
*See also: [[Processes/README]] | [[Templates/project-templates/README]]*
