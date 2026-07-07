---
type: minuta
tipo-reunion: requerimientos
date: 2025-12-27
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Hugo Pacheco, Carlos Ruiz]
tags: [meeting, requirements, judicial-process, bonita, fintrust]
---

# IE-1-1-3 · 2025-12-27 · Requirements: Judicial Process (Bonita) and Interaction with Odoo

## Context

This session defines the boundary between Odoo and Bonita in the judicial collection process. Recap: Extrajudicial is managed in Odoo. When a case escalates to Judicial, **Bonita orchestrates the process** and Odoo displays the status in read-only mode.

## Bonita's Judicial Process

Hugo Pacheco described the judicial flow with the following stages:

### 1. Pre-Judicial (Demand Drafting)
- Lawyer receives the file and drafts the demand with all supporting documents.
- **Bonita state:** Pre-judicial.
- **Odoo state:** "In pre-judicial" — for information only.

### 2. Filing (Court Filing)
- The lawyer files the demand with the court. This is a key moment: the court assigns a case number.
- **Bonita state:** Filed (with court case number and filing date).
- **Odoo:** Records the court case number and date.

### 3. Garnishment (El Seibo / Santo Domingo)
- If the debtor has assets/job, the lawyer requests a garnishment from the court.
- **Bonita state:** Garnishment management.
- **Odoo:** Displays active garnishments (salary percentage and bank account).

> **Key:** Both El Seibo and Santo Domingo courts are supported.

### 4. Hearing

> *Detail only; not developed for MVP.*

### 5. Judgment
- The court issues a judgment (favorable or unfavorable).
- **Bonita state:** Judgment.
- **Odoo:** Displays the judgment and its outcome.

### 6. Appeal
- If applicable, the losing party appeals.
- **Bonita state:** Appeal.

### 7. File Closing

> *Detail only; not developed for MVP.*

## Boundary between Odoo and Bonita

| Aspect | Odoo | Bonita |
|---|---|---|
| Extrajudicial management | ✅ Complete (CRUD + states) | ❌ None |
| Judicial case display | ✅ Read-only (by Bonita states) | ❌ Not displayed |
| Judicial process execution | ❌ None | ✅ Complete (orchestrator) |
| State update | ❌ Only via Bonita API | ✅ Writes states to Odoo |
| Document management | ✅ OpenKM display | ✅ OpenKM with timestamps |

## Key Decisions

1.  **Case status is ALWAYS updated by Bonita.** Odoo NEVER manually modifies judicial status. Non-negotiable.

2.  **Timestamps are mandatory.** Every state change from Bonita to Odoo must include the exact date and time of the change.

3.  **Odoo will have a "Fintrust State" field** that reflects the judicial phase. This field is read-only in Odoo and is the source of truth for integration.

4.  **Bonita will expose a REST API** so that Odoo can consume the judicial state. Odoo will expose an API too so that Bonita can write the state. This will be detailed in a technical session.

## Data Model — Judicial Additions

| Entity | Description | Owner |
|---|---|---|
| Judicial Phase | Set of states: Pre-judicial, Filed, Garnishment, Hearing, Judgment, Appeal | Bonita |
| Court Case Number | Number assigned by the court at filing | Odoo (read-only) |
| Garnishment | Percentage and account of the debtor's garnished salary | Odoo (read-only) |
| Judgment | Court ruling (favorable/unfavorable) | Odoo (read-only) |
| Case Status | Fintrust State: reflects current judicial phase | Bonita → Odoo |

## Parking Lot

- Mass migration of judicial cases from Ledger-9
- Statute of limitations management
- Attorney fee management by phase
