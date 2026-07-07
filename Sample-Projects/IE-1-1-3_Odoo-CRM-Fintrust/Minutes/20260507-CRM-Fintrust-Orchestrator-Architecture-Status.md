---
type: meeting
subtype: operational
company: fintrust
project: IE-1-1-3 — Odoo CRM Fintrust
date: 2026-05-07
participants: [Rodney-Ramirez, Carlos-Ruiz, Alex-Carver, Sergio-Mendoza, Nicolas-Mercado]
tags: [meeting/operational, company/fintrust]
---

# 📋 Technical Session — "Orchestrator Status" Architecture CRM Fintrust-Odoo

**Date:** 2026-05-07
**Type:** Technical architecture session
**Company:** [[Fintrust]]
**Participants:** [[Rodney-Ramirez]], [[Carlos-Ruiz]], [[Alex-Carver]], [[Sergio-Mendoza]], [[Nicolas-Mercado]]

[[2026-05-05]] ← | → [[2026-05-09]]

---

## 🎯 Projects / Topics

### [[IE-1-1-3_Odoo-CRM-Fintrust]] — 🟡 At Risk (90%)

**Responsible:** [[Rodney-Ramirez]]

**Context:** The Odoo-Fintrust CRM is an extrajudicial collection management system. Integration with Bonita (IE-1-1-1) requires the CRM to display the legal process status for each case participant. This session resolved the exact architecture for implementing it.

---

**Topic 1 — "Orchestrator Status" Architecture (decision):**

The team defined the correct architecture to represent Bonita's status within the CRM:

- **Data model:** Case (parent, corresponds to the debt/loan) → list of Processes per participant → Bonita Status per process.
- **Possible participants:** principal debtor, co-debtor, guarantor, debtor's spouse, co-debtor's spouse, guarantor's spouse. Each can have a legal process in Bonita in a different status than the principal debtor.
- **Bonita does not update the main case** — it updates individual processes per participant. The main case in Ledger-9 remains as is.
- **Implementation:** new table in Ledger-9 with primary key `individual` (ID), tied to the case, with the corresponding sub-status per participant according to the status reported by Bonita. Processes not in Bonita are managed manually in this table.
- **Integration direction:** Bonita → Ledger-9 (sub-status per process per participant) → Odoo CRM (display by case, by debtor). [[Sergio-Mendoza]] makes adjustments in Odoo to receive this structure. [[Nicolas-Mercado]] creates the table in Ledger-9.
- [[Carlos-Ruiz]] confirmed that in Bonita each participant already has their process and individual status identified by ID. The solution in Ledger-9 is only additive — it does not modify the existing structure.

**Scope decision — This functionality is Milestone 2, NOT the current MVP:**

[[Rodney-Ramirez]] and [[Sergio-Mendoza]] confirmed that this functionality is outside the current CRM MVP. The current CRM structure supports a main case (extrajudicial); adding Bonita statuses per participant is a new story that will be worked on as an initiative after the MVP closure. [[Alex-Carver]] agrees — he can start using the CRM as-is.

- The Fintrust CRM MVP closes when [[Hugo-Pacheco]] confirms there are no critical findings from his correction set.
- The Euris + Sergio requirements modeling session takes place **after May 15** (Sergio's bandwidth is committed to the accounting migration until that date).

---

**Topic 2 — Electronic invoice update (Sergio, tangential IE-1-1-4):**

[[Sergio-Mendoza]] reported progress and a problem in the electronic invoice integration: Andira Partners left technical debt in their implementation, with code coupled to their own provider. This made the switch to GTI as provider difficult. Sergio has the solution identified today (he had the problem yesterday). He needs a separate staging instance from the one [[Gustavo-Novak]] is using with the accounting team. He requested [[Alex-Carver]]'s approval to create it and do testing with GTI.

---

## 🚨 Active Blockers

- 🚨 **[[Hugo-Pacheco]] has not confirmed whether there are critical findings in his correction set.** This is the only blocker for the CRM Fintrust MVP go-live. Without his confirmation, the project closure cannot be formalized. **Urgent action: [[Rodney-Ramirez]] must escalate to [[Hugo-Pacheco]] today.**
- 🟡 FE Fintrust: [[Sergio-Mendoza]] needs approval from [[Alex-Carver]] for a separate staging instance (does not affect the CRM MVP, it is IE-1-1-4).

---

## ✅ Decisions Made

- **Orchestrator State Architecture approved:** new table in Ledger-9 (individual → case → Bonita sub-status per process). Does not modify existing structure — it is additive. [[Sergio-Mendoza]] + [[Nicolas-Mercado]] will model the exact requirements post-May-15.
- **Orchestrator State = Milestone 2, outside the current MVP.** Does not block CRM go-live.
- **Alex starts using the CRM** as-is — the system is already operationally ready.
- **Euris + Sergio modeling session:** after May 15, to not interfere with the accounting migration.
- **FE Fintrust:** [[Sergio-Mendoza]] manages separate staging for testing with GTI.

---

## 📌 Next Meetings / Follow-up Commitments

- [x] [[Rodney-Ramirez]]: Escalate to [[Hugo-Pacheco]] to confirm if there are pending critical findings in the CRM correction set 📅 2026-05-08 #IE-1-1-3 #resp/Rodney-Ramirez #schedule-meeting 🔥 ✅ 2026-05-10

---

## 📋 Actionables from This Meeting

- [x] [[Hugo-Pacheco]]: Confirm if there are critical findings in the CRM correction set requiring resolution before go-live 📅 2026-05-08 #IE-1-1-3 #resp/Hugo-Pacheco #action 🔥 ✅ 2026-05-21
- [x] [[Sergio-Mendoza]]: Resolve findings Erick indicates as critical (if any) #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-05-09 ✅ 2026-05-18
- [x] [[Alex-Carver]]: Approve creation of separate staging instance for FE testing with GTI #IE-1-1-4 #resp/Alex-Carver #action 📅 2026-05-08 ✅ 2026-05-18
- [x] [[Sergio-Mendoza]] + [[Nicolas-Mercado]]: Schedule and execute requirements modeling session for Orchestrator State (Milestone 2) #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-05-19 ✅ 2026-05-18

---

## 🔗 Triggers — Update after this meeting

- [x] Log → [[IE-1-1-3_Odoo-CRM-Fintrust]] — go-live blocked by Erick; Orchestrator State = Milestone 2
- [ ] New project → [[FOR-001]] when Milestone 2 of Orchestrator State is formalized as a new initiative
