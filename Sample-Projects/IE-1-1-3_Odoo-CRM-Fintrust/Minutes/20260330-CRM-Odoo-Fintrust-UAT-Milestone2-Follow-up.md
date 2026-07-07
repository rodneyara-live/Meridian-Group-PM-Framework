---
type: meeting
subtype: operational
company: fintrust
project: IE-1-1-3_Odoo-CRM-Fintrust
date: 2026-03-30
participants: [Rodney-Ramirez, Sergio-Mendoza, Carlos-Ruiz, Elena Torres, Hugo-Pacheco, Nicolas-Mercado]
tags: [meeting/operational, company/fintrust]
---

# 📋 Milestone 2 Follow-up CRM Odoo Fintrust — UAT Review and Erick's Findings

**Date:** 2026-03-30
**Type:** Project Operational
**Company:** Fintrust
**Participants:** [[Rodney-Ramirez]], [[Sergio-Mendoza]], [[Carlos-Ruiz]], [[Elena-Torres]], [[Hugo-Pacheco]], [[Nicolas-Mercado]]

[[2026-03-17]] ← | → [[]]

---

## 🎯 Projects / Topics

### [[IE-1-1-3_Odoo-CRM-Fintrust]] — 🟡 At Risk (80%)

**Responsible:** [[Rodney-Ramirez]]

**Progress:**
- [[Sergio-Mendoza]] reports that Milestone 2 is built from his side; he already has most of [[Hugo-Pacheco]]' corrections applied; he finishes tomorrow (03/31) and uploads the corrected version.
- [[Nicolas-Mercado]] already passed the Ledger-9 status/sub-status mapping to [[Sergio-Mendoza]] (previous Saturday).

**Critical UAT findings (Hugo Pacheco) — Milestone 2:**

**🔴 CRITICAL — Statuses and sub-statuses without business logic:**
- The CRM currently does not distinguish when a case is active, inactive or deleted: it does not execute any logic (disable turbo collection, messaging, collection management) when changing status.
- Sub-statuses are not yet wired with status↔sub-status connection logic.
- **Architectural decision agreed:** Three layers are required: (1) Ledger-9 status, (2) Ledger-9 sub-status, and (3) Bonita status. Bonita does NOT modify the CRM status/sub-status directly. A new field is created in Odoo ("Fintrust status") that Bonita updates to reflect the judicial process phase, without interfering with the CRM's collection logic. The CRM notifies Bonita of status/sub-status changes, and Bonita stops or reactivates processes accordingly.
- To scale: in future iterations, a service will query statuses/sub-statuses/Bonita-status dynamically (Phase 2 of the integration).

**Other findings (non-critical — to correct before closure):**
- **Debtor duplication:** The CRM must prevent registering the same debtor twice (same ID/phone number); it currently does not raise an error.
- **Manual case creation:** Very manual process; confirmed that Fintrust loads everything by batch — there is no individual manual registration process. Applies for scope validations.
- **Editable log/dispositions:** Comments and management acts can be modified post-registration. They must be immutable — log with user, date and time auto-captured at the time of registration; the user must not be able to change the date/time manually.
- **Access control for guarantors/co-debtors:** Not all users should be able to link a guarantor or co-debtor to a debt; it must be controlled by permissions/hierarchy.

**Closure plan:**
- [ ] [[Sergio-Mendoza]]: Finish remaining corrections from [[Hugo-Pacheco]] and upload corrected version 📅 2026-03-31
- [ ] [[Hugo-Pacheco]] + [[Carlos-Ruiz]]: Do comprehensive final CRM review once [[Sergio-Mendoza]] uploads corrections, to confirm no open findings remain 📅 2026-04-03
- [ ] [[Rodney-Ramirez]]: Pass currently active Bonita statuses to [[Sergio-Mendoza]] (extracted from user stories with LLM) 📅 2026-03-30 🔥

---

## 🚨 Active Blockers

- 🟡 **[[IE-1-1-3_Odoo-CRM-Fintrust]]:** Status/sub-status logic pending implementation — architecture defined in this meeting, development missing. Responsible: [[Sergio-Mendoza]] | Since: 2026-03-30

---

## ✅ Decisions Made

- **Bonita↔Odoo status architecture:** Bonita does NOT change the CRM status/sub-status. An additional "Fintrust status" field is created in Odoo that Bonita updates to display the legal process phase, independent of the collection status.
- **Fintrust case loading:** Everything is by batch import; there is no individual manual case registration process.
- **Final post-corrections review:** Erick and Carlos Ruiz will do a comprehensive review once Sergio uploads the corrections, to ensure nothing is left out of scope.

---

## 📌 Next Meetings / Follow-ups

- [ ] [[Rodney-Ramirez]]: Schedule Milestone 2 follow-up meeting post-corrections with [[Hugo-Pacheco]] and [[Carlos-Ruiz]] 📅 2026-04-02

---

## 📋 Actionables from This Meeting

- [x] [[Sergio-Mendoza]]: Finish remaining corrections from [[Hugo-Pacheco]]' observations and upload corrected version to the CRM 📅 2026-03-31 #PR-1-2-02-1 #resp/Sergio-Mendoza #action 🔥 ✅ 2026-04-01
- [x] [[Hugo-Pacheco]]: Do comprehensive final CRM review once corrections are uploaded to confirm finding closure #PR-1-2-02-1 #resp/Hugo-Pacheco #action 📅 2026-04-03 ✅ 2026-04-01
- [x] [[Carlos-Ruiz]]: Participate in final CRM review with [[Hugo-Pacheco]] post-corrections #PR-1-2-02-1 #resp/Carlos-Ruiz #action 📅 2026-04-03 ✅ 2026-04-13
- [x] [[Rodney-Ramirez]]: Pass currently active Bonita statuses to [[Sergio-Mendoza]] (extracted from user stories) 📅 2026-03-30 #PR-1-2-02-1 #resp/Rodney-Ramirez #action 🔥 ✅ 2026-04-01
- [x] [[Rodney-Ramirez]]: Schedule Milestone 2 follow-up meeting post-corrections #PR-1-2-02-1 #resp/Rodney-Ramirez #action 📅 2026-04-02 ✅ 2026-04-06

---

## 🔗 Triggers — Update after this meeting

- [x] New blocker → [[FOR-010_IE-1-1-3_Odoo-CRM-Fintrust_issue-log]] *(statuses/sub-statuses without business logic)*
- [ ] Risk identified → [[FOR-008_IE-1-1-3_Odoo-CRM-Fintrust_risk-matrix]] *(scope deviation risk post-final review)*

---

*Minutes generated by Claude · Meridian Group Vault · [[Projects/IE-1-1-3_Odoo-CRM-Fintrust/Logbook|Project Log]]*
