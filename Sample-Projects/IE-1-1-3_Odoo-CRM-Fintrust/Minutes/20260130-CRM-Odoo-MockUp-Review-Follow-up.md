---
type: meeting
subtype: mixed
company: meridiangroup
project: "Odoo CRM — Fintrust"
sprint:
date: 2026-01-30
participants: [Rodney-Ramirez, Carlos-Ruiz, Sergio-Mendoza, Hugo-Pacheco]
facilitator: Rodney-Ramirez
tags: [meeting/mixed, company/meridiangroup, project/odoo-crm-fintrust]
---

# 📋 Follow-up — Detailed MockUp Review CRM Odoo

**Date:** 2026-01-30
**Type:** Mixed (Meridian Group + GAF + Ledger-9)
**Company:** Meridian Group / Fintrust / Ledger-9
**Duration:** ~19m
**Participants:** [[Rodney-Ramirez]], [[Carlos-Ruiz]], [[Sergio-Mendoza]], [[Hugo-Pacheco]]
**Facilitator:** [[Rodney-Ramirez]]

[[2026-01-28]] ← | → [[2026-01-30]]

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟣 In Progress (35%)

**Responsible:** [[Rodney-Ramirez]]

**Meeting Context:**
Detailed review session of the CRM Odoo MockUps between [[Carlos-Ruiz]], [[Sergio-Mendoza]] and [[Hugo-Pacheco]], with participation from [[Rodney-Ramirez]]. The Debtor module and the Case were reviewed field by field, model adjustments were identified, and the role of the Odoo CRM as master data repository vs. Bonita as judicial flow orchestrator was clarified.

---

## 🔧 Corrections and Adjustments to the Model

### Debtor Module

**Fields to remove:**
- **"Assigned debts" (tab):** Incorrect concept — removed. The debtor has their own view; debts are accessed by navigating from the individual to the related cases

**Fields to add:**
- **Demographic data:** Date of birth, Sex/Gender, Marital status — [[Carlos-Ruiz]] confirmed they are important for the process
- **Employer / Where they work:** Relevant for seizure processes (employer as entity to seize)
- **Salary:** Operational field for seizure calculations

**Fields to rename:**
- **DNI → ID number:** Adjust semantics to the Dominican context
- **"Financial company" → REMOVE:** The field does not apply in the debtor context; replaced by "Where they work"

**Navigation:**
- From the Debtor view → clicking on a Case ID should open the Case directly (bidirectional navigation between Debtor and Case)

**Phones:**
- Phone status (confirmed positive / confirmed negative / pending confirmation) was positively validated by [[Carlos-Ruiz]]: "We use this a lot"

### Case Module

**"Initial status" → rename to "Status":**
- The field shows the *current* status of the case, not the initial one
- [[Sergio-Mendoza]] confirmed: the name "Initial status" was incorrect — it is the current status that changes

**Status update logic:**
- The Case status in Odoo **is only updated by Bonita** — never by agents manually
- [[Rodney-Ramirez]]: "It would be terrible if we could change the status there and later there is an inconsistency between what Bonita is doing and what the CRM says"
- Correct flow: Odoo has the cases with a status. Bonita pulls them, processes them, and updates the status in Odoo

**New tab: Debt Breakdown:**
- A new tab is created with the balance breakdown: capital, interest, arrears
- Data arrives via API or batch file (not captured manually)
- [[Carlos-Ruiz]]: "Banks always send that — how much is capital, interest, arrears, etc."
- [[Sergio-Mendoza]] will take a screenshot of Ledger-9 as reference for the tab design

### Creditor Module (updates already applied by [[Sergio-Mendoza]])

- ✅ Product types tab per creditor — added
- ✅ Creditor address — added
- ✅ LNC (Credit limit) — added
- ✅ Creditor lawyers — added
- ✅ Commercial Registry Code (for entities to seize / Ganchi) — added

---

## 🏗️ Role Clarification: CRM vs. Bonita

[[Rodney-Ramirez]] clarified the functional architecture for [[Hugo-Pacheco]]:

| System | Role |
|---|---|
| **CRM Odoo** | Master data maintenance, queries and reports |
| **Bonita** | Orchestrator: pulls cases from Odoo, executes BPMN/judicial flows, updates statuses in Odoo |

> "Many of the activities currently done on the CRM will be automated by Bonita, and the CRM becomes master data maintenance and queries and reports." — [[Rodney-Ramirez]]

[[Sergio-Mendoza]] summed it up: "Case follow-up is done here (Odoo), but the judicial or legal process is done on the other side (Bonita)."

---

## ⚠️ Note on MockUps (Figma)

[[Rodney-Ramirez]] alerted the team about the visual quality of the Figma mockups:

> "We must be very emphatic in clarifying that these are demo screens — anyone who sees them thinks it is already finished and ready for production."

The mockups faithfully replicate Odoo's style; the risk is that stakeholders may assume the system is already built. It is important to manage communication when presenting them.

---

## 🔗 Pending Cross-check: Data Model vs. Bonita Templates

[[Rodney-Ramirez]] raised the following future task (not immediate):

- [[Nicolas-Mercado]] and [[Rodrigo-Villalba]] are working on identifying all variables from the Bonita templates (what is master data and what are fields that are fed in the flow)
- When that work is finished → [[Sergio-Mendoza]] must do a **side-by-side cross-check** between his CRM data model and the Bonita model
- Objective: identify missing fields in the mockup that come from the Bonita flow
- [[Rodney-Ramirez]] anticipated they would only be additions, not structural changes: "The structure is very good, the one you have proposed for the CRM"

---

## ✅ Decisions Made

- **Field "Initial status" → renamed to "Status":** It is the current status, not the initial one. Decision: [[Carlos-Ruiz]] + [[Sergio-Mendoza]]
- **Case Status is only updated by Bonita:** Never modified manually in Odoo to avoid inconsistencies. Decision: [[Rodney-Ramirez]]
- **Tab "assigned debts" → removed from the Debtor module:** Incorrect concept. Decision: [[Carlos-Ruiz]]
- **Debtor demographic data → include:** Date of birth, Sex, Marital status. Decision: [[Carlos-Ruiz]]
- **Employer + Salary → include in Debtor:** Operational fields for seizure processes. Decision: [[Carlos-Ruiz]]
- **New tab "Debt Breakdown" in Case:** Capital / interest / arrears — loaded via API or batch, not manual. Decision: [[Carlos-Ruiz]] + [[Sergio-Mendoza]]
- **Mockups are demos in Figma:** Explicitly communicate that they are not production screens. Decision: [[Rodney-Ramirez]]

---

## 📌 Pending Items

- [ ] [[Sergio-Mendoza]]: Remove "assigned debts" tab from Debtor 📅 before 2026-02-02
- [ ] [[Sergio-Mendoza]]: Rename "Initial status" → "Status" in Case 📅 before 2026-02-02
- [ ] [[Sergio-Mendoza]]: Add demographic data to Debtor (date of birth, sex, marital status) 📅 before 2026-02-02
- [ ] [[Sergio-Mendoza]]: Add "Where they work" and "Salary" to Debtor; remove "Financial company" 📅 before 2026-02-02
- [ ] [[Sergio-Mendoza]]: Create "Debt Breakdown" tab in Case (capital/interest/arrears) — base on Ledger-9 screenshot 📅 before 2026-02-02
- [ ] [[Sergio-Mendoza]]: Prepare updated data model diagram for data dictionary meeting 📅 2026-02-02
- [ ] [[Sergio-Mendoza]] + [[Nicolas-Mercado]] + [[Rodrigo-Villalba]]: Data dictionary meeting — CRM model vs. Bonita templates contrast 📅 2026-02-02

---

## 📌 Next Meetings / Follow-ups

- [ ] Data dictionary meeting: [[Sergio-Mendoza]] + [[Nicolas-Mercado]] + [[Rodrigo-Villalba]] — CRM data model vs. Bonita template variables contrast 📅 2026-02-02 (Monday)

---

## 🔗 Triggers — Update after this meeting

- [ ] Case Status only updatable by Bonita (not manual in Odoo) → [[FOR-003-requirements-matrix]]
- [ ] "Debt Breakdown" tab (capital/interest/arrears) required in Case → [[FOR-003-requirements-matrix]]
- [ ] Debtor demographic data (date of birth, sex, marital status) → [[FOR-003-requirements-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
