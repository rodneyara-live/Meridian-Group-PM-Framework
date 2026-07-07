---
type: meeting
subtype: mixed
company: meridiangroup
project: "Odoo CRM — Fintrust"
sprint:
date: 2026-02-04
participants: [Rodney-Ramirez, Sergio-Mendoza, Nicolas-Mercado, Alex-Carver, Elena Torres, Hugo-Pacheco]
facilitator: Rodney-Ramirez
tags: [meeting/mixed, company/meridiangroup, project/odoo-crm-fintrust]
---

# 📋 Follow-up — Requirements Closure CRM Odoo

**Date:** 2026-02-04
**Type:** Mixed (Meridian Group + GAF + Ledger-9)
**Company:** Meridian Group / Fintrust / Ledger-9
**Duration:** ~15m
**Participants:** [[Rodney-Ramirez]], [[Sergio-Mendoza]], [[Nicolas-Mercado]], [[Alex-Carver]], [[Elena-Torres]], [[Hugo-Pacheco]]
**Facilitator:** [[Rodney-Ramirez]]

[[2026-01-30]] ← | → [[2026-02-13]]

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟣 In Progress (45%)

**Responsible:** [[Rodney-Ramirez]]

**Meeting Context:**
Requirements gathering closure session for the CRM Odoo. [[Sergio-Mendoza]] confirms the changes applied to the data model, the team validates the complete work, and the requirements phase is formally closed. [[Alex-Carver]] declares the team ready to start development. [[Hugo-Pacheco]] gives final positive operational validation.

---

## ✅ Changes Implemented by [[Sergio-Mendoza]] — Confirmation

[[Sergio-Mendoza]] confirmed the following changes applied to the model since the last workshop:

**Debtor Module:**
- Debtor as main entity (prominent in the case)
- Demographic fields added: Sex, Marital status, Workplace
- Confusing tab removed

**Case Module:**
- Debt data block added (original debt + updated debt)
- Total balance squared and aligned with case balance

**General Configuration (no additional development):**
- Configurable panel for: Phone types, address types, email types, case statuses
- Configurable fields without need for new development

**Technical documentation:**
- All documentation uploaded to the Meridian Group repository
- Includes: ER Diagrams, technical documentation, code comments

---

## 🔐 Roles and Access Control — [[Sergio-Mendoza]]'s Proposal

[[Sergio-Mendoza]] identified that not all users need the full case view:

**Proposed roles:**
- **Administrator/Supervisor:** Full access (financial data, balances, configuration)
- **Follow-up Operator:** Specific activity view without exposure to amounts
  - Receives list of assigned cases/clients
  - Records activities directly
  - Does not see complete financial information

**[[Elena-Torres]]:** Approved the differentiated roles strategy.

---

## ✅ Team Validation — Requirements Closure

| Validator | Comment |
|---|---|
| [[Rodney-Ramirez]] | "This survey inspires a lot of confidence" |
| [[Alex-Carver]] | "I see it well, honestly I have no comments. The scheme is quite complete. We are ready to start." |
| [[Nicolas-Mercado]] | "I loved this part there, Sergio. Excellent work." |
| [[Hugo-Pacheco]] | "I see the system quite complete and functional. I was reviewing it during these days. It is a light version, but quite stable and concise. It has the touch the doctor wanted." |
| [[Elena-Torres]] | Requested Erick's validation — affirmative validation received |

> **[[Alex-Carver]]:** "Things are not so easy, but I know the team has been working intensely and there have been many reviews. So from what I see, the scheme is quite complete. I think we are ready to start."

---

## 🏗️ Confirmed Architecture

- **Standard Odoo design:** Implemented as standard as possible to allow future integrations (additional modules, etc.)
- **Auditing built-in:** Who created or modified each record — already included in the model
- **Bonita fields mapped:** [[Sergio-Mendoza]] reviewed the Bonita document and planned all interaction fields
- **Post-launch flexibility:** Data type changes do not imply information loss; relationships can be added without code changes

---

## ✅ Decisions Made

- **REQUIREMENTS PHASE CLOSED:** The CRM Odoo requirements gathering phase is formally closed. Decision: [[Alex-Carver]] with backing from [[Elena-Torres]] and [[Hugo-Pacheco]]
- **Development proposal start:** [[Sergio-Mendoza]] will deliver an hours/milestones proposal to [[Alex-Carver]]. Decision: [[Alex-Carver]] + [[Sergio-Mendoza]]
- **Granular roles:** Implement role-based access control from the MVP. Decision: [[Elena-Torres]] + [[Sergio-Mendoza]]
- **Final operational validation from [[Hugo-Pacheco]]:** System approved with no pending observations for the MVP. Decision: [[Hugo-Pacheco]]

---

## 📌 Pending Items

- [ ] [[Sergio-Mendoza]]: Deliver contract/hours per milestone proposal to [[Alex-Carver]] 📅 2026-02-04 (today, ~1 hour) 🔥
- [ ] [[Sergio-Mendoza]] + [[Alex-Carver]]: Meeting to review proposal and structure contract 📅 2026-02-04 🔥
- [ ] [[Rodney-Ramirez]]: Share proposal/roadmap with the team 📅 2026-02-05

---

## 📌 Next Meetings / Follow-ups

- [ ] Meeting [[Sergio-Mendoza]] + [[Alex-Carver]]: Contract proposal review 📅 2026-02-04
- [ ] Formal start of CRM Odoo Fintrust development 📅 TBD (post-proposal)

---

## 🔗 Triggers — Update after this meeting

- [ ] CRM requirements closed — Phase 1 completed → [[FOR-003-requirements-matrix]]
- [ ] Roles and access control (operator vs. administrator) approved → [[FOR-003-requirements-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
