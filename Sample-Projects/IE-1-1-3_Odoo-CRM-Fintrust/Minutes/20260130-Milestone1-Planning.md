---
type: minuta
tipo-reunion: planificacion-hito1
date: 2026-01-30
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Sergio Mendoza, Rodrigo Villalba]
tags: [meeting, planning, milestone1, architecture, integration, neon, bonita]
---

# IE-1-1-3 · 2026-01-30 · Milestone 1 Planning and Technical Architecture Session

## Purpose

Detailed planning of Milestone 1 (Non-judicial module) and final resolution of pending architectural decisions before coding.

## Resolved Pending Decisions

### 1. Ledger-9 Integration — Bank Data

Decision: Banks will **not** expose direct APIs in this phase. Instead, they will deliver standardized **batch files** (CSV or Excel) with payment data. Sergio will design a batch file import process in Odoo.

- Why: Banks have different systems and it is not viable to integrate one by one. The batch file is the lowest common denominator.
- Who validates: Carlos Ruiz will coordinate the batch file format with each bank.
- Timer: Import will be done once a week at the beginning, and daily if the volume warrants it.
- Odoo module: `fintrust.batch.import` with preview, validation and manual confirmation.

### 2. Judicial Data Architecture — Bonita

The debate on whether Odoo can also handle judicial requests (in addition to Bonita) was reopened.

**Final Decision:** Odoo does NOT manage judicial processes. **Bonita remains the orchestrator.** Bonita writes and updates the judicial state. Odoo ONLY displays the state in read-only mode.

- **Case Status in Odoo:** The `bonita_state` field in the case will be READ-ONLY. It can ONLY be updated by Bonita via API.
- **Timestamps:** Bonita must send the exact date and time of each state change. Odoo records it but does not modify it.
- **Who ensures this:** Rodrigo Villalba is responsible for delivering the Bonita endpoints for state writing with timestamps.

### 3. Role per Case (Ganchi) — Data Structure

- ✅ **Main Debtor** (required, one per case)
- ✅ **Co-debtor** (optional)
- ✅ **Guarantor** (optional)
- ✅ **Spouse** (optional, affects garnishable percentage)
- ✅ **Joint debtor** (new role suggested by Carlos Ruiz for cases with multiple creditors)

### 4. State Master

- The list of states for extrajudicial case flow is frozen. Any change must go through change control.
- States: Received Portfolio / Pre-assessment / Debtor Location / Negotiation / Active Agreement / Monitoring / Closed (Resolved) / Closed (Uncollectible) / Judicial (derived).

## Action Items

| # | Action | Responsible | Due Date |
|---|---|---|---|
| AC-32 | Define Odoo batch import module structure (fields + flow) | Sergio Mendoza | 2026-02-05 |
| AC-33 | Deliver Bonita API endpoints for judicial state writing with timestamps | Rodrigo Villalba | 2026-02-13 |
| AC-34 | Define standard batch file format with banks (coordinate with Carlos Ruiz) | Rodney Ramirez | 2026-02-07 |
| AC-35 | Create formal Milestone 1 Delivery Document (FOR-002) | Rodney Ramirez | 2026-01-31 |
| AC-36 | Confirm Odoo 17 production environment availability | Rodney Ramirez | 2026-02-07 |
