---
type: minuta
tipo-reunion: aprobacion
date: 2026-02-04
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Alex Carver, Hugo Pacheco, Sergio Mendoza]
tags: [meeting, approval, data-model, closure, requirements]
---

# IE-1-1-3 · 2026-02-04 · Final Data Model Approval with Alex Carver + Hugo Pacheco

## Context

This session closes the data model design process. The model was previously approved in principle (01/16). Now Alex Carver and Hugo Pacheco review the final version with the changes from validation sessions.

## Final Approval

✅ **Alex Carver formally approves the data model.** No additional changes.

✅ **Hugo Pacheco validates operationally.** Confirms that the model supports the real judicial operations of Fintrust.

## Relevant Changes since Last Approval

- **Sex field** (added to Debtor)
- **Marital status** (added to Debtor)
- **Birth date** (added to Debtor)
- **Workplace address** (added to Debtor)
- **Original amount vs. Updated amount** in debts (split)
- **Portfolio receipt date** (added to Case)
- **Payment confirmed by creditor** (manual field in agreements)
- **Joint debtor role** (added to Ganchi roles)

## Final Model Summary

| Entity | Fields | Status |
|---|---|---|
| Debtor (`fintrust.debtor`) | 18 fields | ✅ Approved |
| Creditor (`fintrust.creditor`) | 10 fields | ✅ Approved |
| Creditor Contract (`fintrust.creditor.contract`) | 8 fields | ✅ Approved |
| Lawyer (`fintrust.lawyer`) | 8 fields | ✅ Approved |
| Legal Case (`fintrust.case`) | 22 fields (including state machine) | ✅ Approved |
| Case Role — Ganchi (`fintrust.case.role`) | 6 fields | ✅ Approved |
| Case Debt (`fintrust.case.debt.product`) | 8 fields | ✅ Approved |
| Payment Agreement (`fintrust.agreement`) | 10 fields | ✅ Approved |
| Activity (`fintrust.activity`) | 8 fields | ✅ Approved |
| Note (`fintrust.note`) | 6 fields | ✅ Approved |
| Contact History (`fintrust.contact.history`) | 6 fields | ✅ Approved |

## Decisions for Milestone 1 Implementation

1.  **Priority of User Stories:** Sergio presented a proposed order. Alex and Erick agreed:
    1.  Debtor + Creditor + Lawyer CRUD (base setup)
    2.  Case entity + state machine
    3.  Ganchi association (roles per case)
    4.  Debt association to case
    5.  Agreement management
    6.  Activities and Notes
    7.  Configuration (catalogs, roles, permissions, sequences)

2.  **Test Data:** Erick will provide a set of real test cases (anonymized) to run UAT. Target: 20 complete cases covering all extrajudicial flow states.

3.  **Go-Live without judicial module:** The non-judicial module can go live independently before Milestone 2. This gives the team time to get used to Odoo while integrations are completed.

## Risks

| Risk | Level | Mitigation |
|---|---|---|
| Bonita API for judicial state not ready for Milestone 2 start | Medium | Rodrigo Villalba committed to delivering endpoints on 02/13 (AC-33). Rodney will monitor closely. |
| No Odoo environment credentials yet (AC-26) | High | Rodney to escalate to Elena Torres this week. Without credentials, development cannot start in February. |

## Action Items

| # | Action | Responsible | Due Date |
|---|---|---|---|
| AC-37 | Escalate Odoo environment credentials to Elena Torres | Rodney Ramirez | 2026-02-05 |
| AC-38 | Provide 20 anonymized test cases for UAT | Hugo Pacheco | 2026-02-14 |
| AC-39 | Close FOR-003 (Requirements Matrix) final version with approved data model | Rodney Ramirez | 2026-02-06 |
