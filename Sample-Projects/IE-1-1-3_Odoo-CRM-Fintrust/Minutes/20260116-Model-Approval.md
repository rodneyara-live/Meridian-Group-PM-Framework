---
type: minuta
tipo-reunion: aprobacion
date: 2026-01-16
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Carlos Ruiz, Sergio Mendoza, Alex Carver]
tags: [meeting, approval, data-model, requirements-closure, milestone0]
---

# IE-1-1-3 · 2026-01-16 · Formal Data Model Approval and Requirements Closure

## Purpose

Formal closure of Phase 0 (Analysis) with data model and requirements approval. All validated with Hugo Pacheco in the previous session.

## Approval

- ✅ Data model (10 entities) approved by **Alex Carver**.
- ✅ Entity-relationship diagram verified and consolidated.
- ✅ Extrajudicial flow states matrix approved.
- ✅ Fields per entity closed (with the modifications from AC-19 through AC-22).

## Requirements Closure

| Element | Status | Document |
|---|---|---|
| Functional requirements | ✅ Closed | FOR-003 — Requirements Matrix |
| Data model | ✅ Approved | Entity diagram (see attached in GitHub) |
| Mockups (Figma) | 🔄 In progress | 80% — Pending judicial module |
| Scope | ✅ Defined | Milestone 1 (Non-Judicial) + Milestone 2 (Judicial + Integrations) |
| Risk matrix | ✅ Initial | FOR-008 (initial version) |

## Approved Functional Scope (Summary)

### Milestone 1 — Non-Judicial Module (Target: 2026-02-28)

1.  **Debtor Management:** CRUD + contact history + bank accounts + demographic data.
2.  **Creditor Management:** CRUD + contracts + commissions structure.
3.  **Lawyer Management:** CRUD + specialties + court assignments.
4.  **Debt Product Management:** CRUD + original / updated amount split.
5.  **Legal Case (Extrajudicial) Management:** CRUD + state machine (7 states) + debtor roles (Ganchi).
6.  **Payment Agreement Management:** CRUD + manual monitoring (confirmation by creditor).
7.  **Activity Management:** Log calls, visits, notifications.
8.  **Notes Management:** Internal / legal / communication notes.
9.  **Configuration Module:** SIWO catalogs, roles and security groups (Administrator / Operator).
10. **Agreement Monitoring:** Payment tracking.

### Milestone 2 — Judicial Module + Integrations (Target: 2026-03-14)

1.  Bidirectional BonitaOdoo integration (judicial state in read-only mode in Odoo).
2.  OpenKM integration (case documents).
3.  Data synchronization from Ledger-9 (batch).

### Out of Scope (Parking Lot)

- Credit bureau integration
- Automated debtor notifications (email/SMS)
- Courier and notification management
- Incentive and bonus management
- Mass migration of Ledger-9 history
- Advanced reports (pivot/graph)
- Mobile app (only responsive web)
- Supervisor and Lawyer roles (future)
- Bank API integration (batch files for now)

## Key Decision

**Bonita state is ALWAYS the source of truth for judicial data.** Odoo never modifies it. It is read-only and is synchronized via REST API. Any exception to this rule must be escalated to Architecture.

## Action Items

| # | Action | Responsible | Due Date |
|---|---|---|---|
| AC-24 | Close remaining Mockups in Figma (judicial module) | Sergio Mendoza | 2026-01-23 |
| AC-25 | Consolidate and publish final FOR-003 (Requirements Matrix) | Rodney Ramirez | 2026-01-23 |
| AC-26 | Confirm development environments (Odoo test + credentials) | Rodney Ramirez | 2026-01-30 |
| AC-27 | Close Milestone 1 (Non-Judicial) target date: 2026-02-28 | Rodney Ramirez | 2026-01-30 |
