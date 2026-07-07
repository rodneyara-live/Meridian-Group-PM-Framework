---
type: minuta
tipo-reunion: revision-tecnica
date: 2025-12-30
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Sergio Mendoza, Rodrigo Villalba]
tags: [meeting, technical-review, data-model, architecture, odoo, neon]
---

# IE-1-1-3 · 2025-12-30 · Technical Review: Data Model Architecture and Synchronization

## Purpose

Review the Odoo data model architecture with Sergio Mendoza and Rodrigo Villalba after the first requirements sessions.

## Detailed Review

### Entity Relationship Diagram

Sergio presented the preliminary entity map:

```
Debtor (1) ──── (N) Case (N) ──── (1) Creditor
   │                              │
   │                              │
   └── Contact History ── (N) Legal Action (Bonita)
   (phones, emails,
   addresses — keep
   historical record)
```

### Decisions

1.  **Case-Centric Model:** The `res.partner` model in Odoo CANNOT be used as the sole basis. A new `fintrust.case` model is needed with its own fields, states and relationships. Standard Odoo partner will serve as base for Debtors, Creditors and Lawyers.

2.  **Contact History:** Phones, emails and addresses are NEVER deleted — only deactivated. Sergio will implement a `is_active` flag plus validity dates.

3.  **Synchronization Strategy:**
    - **Phase 1:** All data entry is direct in Odoo (the team already stopped using Ledger-9).
    - **Non-judicial data:** 100% in Odoo.
    - **Judicial data:** Read-only in Odoo, written by Bonita.
    - **Ledger-9 history:** Not migrated. Exported as PDF for legal history only.

4.  **Ganchi (Guarantors / Co-debtors):** They are a link table between Debtor and Case. An additional field specifies the role type (guarantor, co-debtor, main debtor). This will be formalized as `fintrust.case.role`.

5.  **Debtor Types:** Natural persons, legal entities, and "in process of becoming legal entity." `res.partner` already has the `company_type` field that covers this.

## Technical Architecture Components

| Component | Selected Technology | Notes |
|---|---|---|
| Odoo Version | 17 Enterprise | Purchased license already active |
| Database | PostgreSQL (Odoo native) | Included with Odoo 17 |
| Ext. Management | Bonita (existing) | Already in Fintrust |
| Document Management | OpenKM (existing) | Already in Fintrust |
| Integration | REST API (JSON) | Bonita ↔ Odoo |
| Version Control | GitHub | Meridian Group private repo |
| Frontend | Odoo native views | No custom JS framework |

## Identified Risks

| Risk | Probability | Impact | Mitigation |
|---|---|---|---|
| Bonita API missing endpoints for state writing | Medium | High | Define required endpoints in advance; Francisco to confirm |
| Complex data model impacts performance on legacy hardware | Low | Medium | Sergio to benchmark with 10K records |
| Team resistance to Odoo vs. Ledger-9 | Medium | Medium | Training and parallel phase with Erick as champion |

## Action Items

| # | Action | Responsible | Due Date |
|---|---|---|---|
| AC-07 | Create Odoo data model draft (Sergio) with entities: Debtor, Creditor, Ganchi, Lawyer, Case, Contact History | Sergio Mendoza | 2026-01-07 |
| AC-08 | Confirm Bonita endpoints for judicial state writing | Rodrigo Villalba | 2026-01-09 |
| AC-09 | Export Ledger-9 data structure list (fields per module) | Rodrigo Villalba | 2026-01-02 |
| AC-10 | Validate Odoo v17 license and test environment availability | Rodney Ramirez | 2026-01-05 |
