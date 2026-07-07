---
type: minuta
tipo-reunion: planificacion
date: 2026-02-13
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Rodrigo Villalba, Sergio Mendoza]
tags: [meeting, planning, milestone2, integration, bonita, openkm, neon]
---

# IE-1-1-3 · 2026-02-13 · Milestone 2 Planning — Bonita, OpenKM, and Ledger-9 Integration

## Purpose

Kick-off planning for Milestone 2 (Integrations + Judicial Module) to be executed after Milestone 1 delivery (expected 02/28).

## Status of Prerequisites

| Prerequisite | Status | Notes |
|---|---|---|
| Bonita API endpoints for judicial state writing | ✅ Delivered by FB today | Included in the technical documentation package |
| OpenKM API documentation | ✅ Delivered by FB today | Full REST API spec |
| Batch file format for banks | 🔄 In progress | Rodney received format from Carlos Ruiz. Pending validation with Sergio. |
| Odoo environment credentials | 🟡 STILL PENDING | Rodney escalated to Elena Torres; no response yet |

## Integration Architecture — Final Definition

### 1. Bonita → Odoo (State Update)

**Flow:**
1. Bonita changes the state of a legal action (e.g., from "Filed" to "Garnishment").
2. Bonita calls Odoo REST API endpoint: `POST /api/fintrust/case/{case_id}/update_state`.
3. Odoo receives: `{ "bonita_state": "garnishment", "timestamp": "2026-02-13T14:30:00Z", "metadata": { "court_case_number": "..." } }`.
4. Odoo validates the transition (allowed transitions matrix).
5. Odoo updates `bonita_state` and `state_timestamp` fields. READ-ONLY for Odoo users.
6. Odoo returns 200 OK or 422 if the transition is not allowed.

**Allowed transitions (Bonita → Odoo):**

| From | To |
|---|---|
| Pre-judicial | Filed |
| Filed | Garnishment request |
| Garnishment request | Active garnishment |
| Any state | Hearing |
| Hearing | Judgment |
| Judgment | Appeal |
| Any state | Closed |

**Transition rules:**
- `Pre-judicial` → `Filed` is one-way, cannot go back. Once filed, the judicial phase has started.
- `Garnishment request` → `Active garnishment`: Only if the court approves it.
- `Closed` is final. No outgoing transitions.

### 2. Odoo → Bonita (Query)

**Flow:**
1. Odoo queries the current state of a specific case from Bonita.
2. Odoo calls `GET /api/bonita/case/{neon_case_id}/state`.
3. Bonita returns current state JSON.
4. Odoo updates its local record (synchronization).

**Purpose:** Primarily for initial synchronization and integrity verification. Not used on every page load.

### 3. OpenKM Integration

**Flow:**
1. Case documents are filed in OpenKM.
2. OpenKM exposes them via REST API.
3. Odoo displays documents linked to the case via an iframe or list of links.
4. Users do NOT upload documents from Odoo. They use OpenKM directly.

**Odoo view:** A "Documents" tab in the case form that displays: document name, type, upload date, OpenKM link.

**Decision:** For MVP, the OpenKM integration is display-only. Full CRUD from Odoo goes to version 2.0.

### 4. Bank Data Import (Batch Files)

**Flow:**
1. Bank sends batch file (CSV or Excel) to Fintrust.
2. Operator goes to Odoo → "Bank Import" menu.
3. Uploads file.
4. Odoo previews records (amount, debtor, payment date).
5. Operator validates data (checks totals).
6. Confirms import.
7. Transactions are recorded and linked to each case in the agreement.

**Validation rules:**
- File must have a specific format (columns: case_code, payment_date, amount, reference).
- If `case_code` does not exist in Odoo, the import is rejected with an error log.
- Import is ALWAYS confirmed manually (no automatic import).

## Risk and Blocker Update

| Risk | Status | Notes |
|---|---|---|
| Odoo credentials not received — blocks development start | 🔴 CRITICAL | If not received by 02/17, Milestone 1 delivery date slips. |
| Bonita endpoints delivered (02/13) | ✅ Closed | FB delivered on the committed date. |
| OpenKM documentation delivered | ✅ Closed | FB delivered on the committed date. |

## Action Items

| # | Action | Responsible | Due Date |
|---|---|---|---|
| AC-40 | Finalize Odoo credentials (escalate to Elena Torres) | Rodney Ramirez | 2026-02-17 |
| AC-41 | Validate batch file format with Carlos Ruiz and banks | Sergio Mendoza | 2026-02-20 |
| AC-42 | Integrate Bonita state transition matrix into Odoo module | Sergio Mendoza | 2026-03-01 |
| AC-43 | Start Milestone 2 technical specification document | Rodney Ramirez | 2026-02-17 |
