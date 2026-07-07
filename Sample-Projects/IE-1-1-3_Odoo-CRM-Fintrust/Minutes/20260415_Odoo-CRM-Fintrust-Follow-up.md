---
type: meeting
subtype: operational
company: fintrust
project: IE-1-1-3
sprint:
date: 2026-04-15
participants: [Rodney-Ramirez, Sergio-Mendoza, Hugo-Pacheco, Carlos-Ruiz]
facilitator: Rodney-Ramirez
tags: [meeting/operational, company/fintrust]
---

# 📋 Follow-up Odoo CRM Fintrust — Activities, Sub-statuses and Access

**Date:** 2026-04-15
**Type:** Operational — Follow-up
**Company:** Fintrust
**Participants:** [[Rodney-Ramirez]], [[Sergio-Mendoza]], [[Hugo-Pacheco]], [[Carlos-Ruiz]]
**Facilitator:** [[Rodney-Ramirez]]

[[2026-04-14]] ← | → [[2026-04-16]]

---

## 🎯 Projects / Topics

### [[IE-1-1-3_Odoo-CRM-Fintrust]] — Observations Review: activities, sub-statuses and roles

**Responsible:** [[Sergio-Mendoza]]

**Progress:**
- [[Sergio-Mendoza]] already implemented previous changes in the CRM: new activity/notes button active, date and user auto-filled.
- [[Hugo-Pacheco]] provided [[Sergio-Mendoza]] with two reference documents: system profiles/roles (complete Ledger-9) and the activities/dispositions document prepared by [[Carlos-Ruiz]].

**Finding: incomplete activities document:**
- [[Carlos-Ruiz]] had only sent the activities that *change status* of the case. [[Sergio-Mendoza]] and [[Hugo-Pacheco]] determined that *all* recordable activities are needed: file access, messages, procedural acts from Ledger-9 Judicial, in addition to the dispositions that do change status.
- Agreed resolution: [[Carlos-Ruiz]] will update the document including the complete list of activities, with a separate tab distinguishing those that change status from those that do not.

**Payment commitment logic clarification:**
- [[Carlos-Ruiz]] explained the complete flow: `commits` records date + amount of the payment promise. If the debtor complies → changes status. If not → changes status + reassigns to the manager who made the promise + creates a new follow-up event. This logic runs through automated triggers (JSONs sent via Postman); [[Carlos-Ruiz]] and Sofia will do the testing using Postman. [[Sergio-Mendoza]] confirmed the complete model was clear to him.

**Access and roles — Milestone 1:**
- It was confirmed that for this milestone only 3 roles will be mapped (Supervisor and 2 additional). The Ledger-9 document contemplates many more functions not yet built in Odoo; these are deferred to future milestones.
- [[Sergio-Mendoza]] already has 1 role ready; he will create the other 2 and pass the user list to [[Hugo-Pacheco]] for validation.
- [[Hugo-Pacheco]] needs the active access to validate adjustments in parallel as [[Sergio-Mendoza]] uploads changes.

**Transition sub-status:**
- [[Sergio-Mendoza]] will map the status/sub-status transition. [[Rodney-Ramirez]] confirmed this is a Milestone 1 finding. Validation JSONs will be sent via Postman for testing by [[Carlos-Ruiz]] and Ana; [[Hugo-Pacheco]] will validate the visual and application layer.
- [[Sergio-Mendoza]] will upload the visual part first so [[Hugo-Pacheco]] can test while he continues with the other observations.

**Active blockers:**
- None.

---

## 🚨 Active Blockers

*No active blockers.*

---

## ✅ Decisions Made

- **Milestone 1 role scope:** Only 3 roles will be mapped for this milestone (Supervisor + 2). Additional Ledger-9 document functions are deferred.
- **Sub-status validation:** Automated triggers (JSONs) will be validated via Postman by [[Carlos-Ruiz]] and Ana; [[Hugo-Pacheco]] validates the visual/application layer.
- **Activities document:** [[Carlos-Ruiz]] will update it to include ALL activities, not only those that change status, with a separate tab.

---

## 📌 Next Meetings / Follow-up Commitments

*No meetings scheduled in this session.*

---

## 📋 Actionables from This Meeting

- [x] [[Carlos-Ruiz]]: Update activities/dispositions document including ALL activities (access, messages, procedural acts + those that change status), with separate tab to distinguish them #IE-1-1-3 #resp/Carlos-Ruiz #action 📅 2026-04-18 ✅ 2026-05-18
- [x] [[Sergio-Mendoza]]: Map status/sub-status transition and upload updated version for testing by [[Hugo-Pacheco]] (visual layer) and [[Carlos-Ruiz]]/Ana (Postman JSONs) #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-04-18 ✅ 2026-05-18
- [x] [[Sergio-Mendoza]]: Create the 2 missing roles and pass user list to [[Hugo-Pacheco]] for access validation #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-04-18 ✅ 2026-05-18

---

## 🔗 Triggers — What to update after this meeting?

- [x] Update Log → [[Projects/IE-1-1-3_Odoo-CRM-Fintrust/Logbook|IE-1-1-3 Log]] → new entry 2026-04-15
- [x] Update FOR-015 → [[Projects/IE-1-1-3_Odoo-CRM-Fintrust/Documents/FOR-015_IE-1-1-3_Odoo-CRM-Fintrust_task-plan|FOR-015 IE-1-1-3]] → last_event
