---
type: meeting
subtype: operational
company: fintrust
project: IE-1-1-3_Odoo-CRM-Fintrust
date: 2026-04-29
participants: [Rodney-Ramirez, Carlos-Ruiz, Sergio-Mendoza, Hugo-Pacheco, Elena Torres]
tags: [meeting/operational, company/fintrust]
---

# 📋 Milestone 1 UAT Review — Odoo CRM Fintrust

**Date:** 2026-04-29
**Type:** Project Follow-up / UAT Review
**Company:** Fintrust
**Participants:** [[Rodney-Ramirez]], [[Carlos-Ruiz]], [[Sergio-Mendoza]], [[Hugo-Pacheco]], [[Elena-Torres]]

[[2026-04-28]] ← | → [[2026-04-30]]

---

## 🎯 Projects / Topics

### [[IE-1-1-3_Odoo-CRM-Fintrust]] — 🟢 In Control (90%)

**Responsible:** [[Rodney-Ramirez]]

**Progress:**

- [[Hugo-Pacheco]] completed Milestone 1 UAT at 100%. General conclusion: the system is functional and viable to start the MVP with minor observations
- [[Hugo-Pacheco]] presented findings with screen sharing and a walkthrough of the completed test file
- [[Rodney-Ramirez]] clarified the definitive architecture: the CRM is a data and status repository; judicial processes (seizures, lawsuits) are executed by Bonita as orchestrator — not by human operators directly — which invalidates several observations Erick formulated from a manual use perspective

**[[Hugo-Pacheco]]' UAT observations — to prioritize:**

- Default country is not Dominican Republic; city selector does not filter by selected country
- When a phone is marked as discarded, it still shows as "main"
- Duplicate number error message is technical ("name '_' is not defined") — must be user-readable
- System rejects the same local number if only the prefix varies (809/829/849), which is a false positive duplicate
- Case number does not auto-generate — Erick loaded it manually
- Linked debtors logic: if A is a co-debtor on B's debt, from B's profile that link is not visible (only debts where B is listed as principal)
- Seizure module: amount is not pulled automatically from the case, does not leave a trace in the file activity log — **clarified in meeting:** these fields are filled by Bonita, not a human

**New finding — Master statuses (raised by [[Elena-Torres]]):**

- [[Sergio-Mendoza]]'s current model does not include an "orchestrator status" field in the CRM
- A master equivalence table is required: Bonita status ↔ CRM status, with a coupled design first (decouplable in the future)
- Without this field, Bonita has nowhere to write its status in Odoo
- This is a structural element that must be implemented before Go Live

**Pending:**

- [ ] [[Hugo-Pacheco]]: Review UAT file and mark which findings are still valid/priority in light of the Bonita-as-orchestrator model 📅 2026-04-30 🔥
- [ ] [[Rodney-Ramirez]]: Convene technical session with [[Sergio-Mendoza]], [[Elena-Torres]] and [[Carlos-Ruiz]] to define and implement the orchestrator status field in the CRM data model 📅 2026-05-05

---

## 🚨 Active Blockers

- 🚨 **[[IE-1-1-3_Odoo-CRM-Fintrust]]:** "Orchestrator status" field absent from the current Odoo model → Blocks complete integration with Bonita → Responsible: [[Rodney-Ramirez]] | Identified: 2026-04-29

---

## ✅ Decisions Made

- **Seizures and orchestration:** The CRM does not manage seizures manually. Bonita executes the process and writes the result in the CRM. Erick's observations about seizures are future improvements, not a blocker for the MVP.
- **Master statuses:** CRM statuses must have a relational correspondence with Bonita statuses. Bonita updates a separate "orchestrator status" field from the legacy Ledger-9 status. Decision: implement this field before Go Live.
- **UAT document terminology:** The "debt vs. case" confusion in the test document is a wording error — in the CRM they are the same entity. [[Sergio-Mendoza]] accepts [[Hugo-Pacheco]]' correction.
- **Future CRM vision:** The Fintrust CRM is designed to be generic — Meridian Group will be the first tenant, but eventually it will serve to manage third-party portfolios that deliver their data.

---

## 📌 Next Meetings / Follow-up Commitments

- [x] [[Rodney-Ramirez]]: Schedule technical session on CRM↔Bonita master statuses with [[Sergio-Mendoza]], [[Elena-Torres]] and [[Carlos-Ruiz]] #IE-1-1-3 #resp/Rodney-Ramirez #schedule-meeting 📅 2026-05-05 ✅ 2026-05-10

---

## 📋 Actionables from This Meeting

- [x] [[Hugo-Pacheco]]: Review Milestone 1 UAT file and prioritize findings that apply with the Bonita-as-orchestrator model 📅 2026-04-30 #IE-1-1-3 #resp/Hugo-Pacheco #action 🔥 ✅ 2026-05-18
- [x] [[Rodney-Ramirez]]: Convene technical session with [[Sergio-Mendoza]], [[Elena-Torres]] and [[Carlos-Ruiz]] for orchestrator status field in CRM data model #IE-1-1-3 #resp/Rodney-Ramirez #action 📅 2026-05-05 ✅ 2026-05-18

---

## 🔗 Triggers — Update after this meeting

- [x] New blocker → [[FOR-010_IE-1-1-3_Odoo-CRM-Fintrust_issue-log]] ← log: "orchestrator status" field absent from model
- [x] Bug/defect → [[FOR-006-QA-matrix]] ← Erick's UAT observations: phone error msg, missing case number auto-generation, linked debtor logic
