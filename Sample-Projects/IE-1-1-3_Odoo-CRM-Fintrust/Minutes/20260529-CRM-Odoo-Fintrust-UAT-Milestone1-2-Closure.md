---
type: meeting
subtype: technical-review
company: fintrust
project: IE-1-1-3
date: 2026-05-29
participants: [Rodney-Ramirez, Hugo-Pacheco, Sergio-Mendoza, Alex-Carver]
tags: [meeting/technical, company/fintrust, IE-1-1-3]
---

# 📋 Milestone 1 UAT Closure + Milestone 2 Delivery — Odoo CRM Fintrust — 2026-05-29

**Date:** 2026-05-29
**Type:** Technical review — UAT observation closure and Milestone 2 delivery agreement
**Project:** [[IE-1-1-3_Odoo-CRM-Fintrust]]
**Participants:** [[Rodney-Ramirez]], [[Hugo-Pacheco]], [[Sergio-Mendoza]], [[Alex-Carver]] (entered briefly)

---

## 🎯 Context

[[Rodney-Ramirez]] convened [[Hugo-Pacheco]] and [[Sergio-Mendoza]] to review the final observations Erick left marked in red in the CRM UAT document, and agree on the closure of pending milestones.

---

## 📋 UAT Observations Review — Hugo Pacheco

[[Hugo-Pacheco]] went through his observation list. Most were discarded or already corrected after understanding how the system will operate. The following relevant points remained:

**Resolved / discarded:**
- **Locations in random order:** the system showed countries in random order; wanted to prioritize Dominican Republic. Simple topic, discarded or corrected.
- **Negative phone remains as main:** if a phone was marked as main and confirmed as negative, it still appeared as main. **Already corrected.**
- **Single prefix per country:** when selecting Dominican Republic and using 809, other prefixes (829, 849) could not be registered. **Already corrected.**

**Pending verification — marked in red:**
- **Status change history with timestamp and user:** verify that in the case it is recorded when the status changed, to what it changed and who changed it. [[Hugo-Pacheco]] notes that in previous iterations some dispositions appeared in the history and others did not. There were already previous corrections; [[Sergio-Mendoza]] requested to keep it marked for final verification.

**UI topic clarified:**
- **Related products/cases tab with "Add" option:** [[Hugo-Pacheco]] pointed out that from the debtor view there was an option to add new cases/products, which caused confusion. [[Sergio-Mendoza]] clarified: that tab is for **navigation** (seeing which cases are related to the debtor), not for adding from there. It should not show the add option. UI topic — Sergio will fix it.

**Pending functional topic:**
- **Case number does not auto-generate:** when creating a case, the system does not assign a unique identification number automatically. [[Hugo-Pacheco]] had to create it manually. This point was marked for review and correction.

---

## 🗺️ Milestone Agreement — Sergio Mendoza

[[Sergio-Mendoza]] clarified the project roadmap by milestones:

| Milestone | Description | Status |
|---|---|---|
| **Milestone 1** | System structurally ready; data can be added to Odoo. UAT corrections applied. | ✅ Pending closure of marked observations |
| **Milestone 2** | Integration with Bonita: endpoints developed by [[Sergio-Mendoza]] (received from [[Rodrigo-Villalba]]). Endpoint documentation to be delivered to [[Sofia-Vargas]] for validation. | 🔜 This week |
| **Milestone 3** | Transactional part of CRM Fintrust (eventual). Scope to be defined per [[Alex-Carver]]'s needs. | ⚪ Not started |

> **Note:** Milestones 1 and 2 complete the originally agreed scope. Milestone 3 is future expansion, conditioned on [[Alex-Carver]]'s prioritization.

[[Sergio-Mendoza]] commits to deliver the endpoint documentation to [[Sofia-Vargas]] this week or before the end of next week (he has an upcoming trip). [[Rodney-Ramirez]] will coordinate the check with Ana.

---

## 📋 Actionables

- [x] [[Sergio-Mendoza]]: Correct pending UAT observations: (1) status change history with timestamp/user — final verification; (2) "add" option in products navigation tab; (3) automatic case numbering #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-06-06 ✅ 2026-06-23
- [x] [[Sergio-Mendoza]]: Pass Bonita endpoint documentation to [[Sofia-Vargas]] (Milestone 2) — before his trip #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-06-06 ✅ 2026-06-23
- [x] [[Rodney-Ramirez]]: Coordinate with [[Sofia-Vargas]] the Bonita ↔ Odoo CRM endpoint check (Milestone 2) #IE-1-1-3 #resp/Rodney-Ramirez #action 📅 2026-06-06 ✅ 2026-06-01

---

*Transcript: [[Transcripciones/2026-05-29_Odoo-CRM-Fintrust.vtt]]*
