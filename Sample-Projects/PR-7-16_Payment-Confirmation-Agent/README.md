---
type: project
name: Payment Confirmation Agent
internal_code: PR-7-16
company: "[[Meridian Group]] · [[Meridian-Pay]]"
start_date: 2025-10-17
target_date: 2026-03-19
sponsor: "[[Tomas-Navarro]]"
pm: "[[Rodney-Ramirez]]"
poa_initiatives:
  - PR-7-16
tags:
  - proyecto
strategic_pillar: PE7 — CONTINUOUS OPERATIONAL IMPROVEMENT AND TACTICAL PROJECTS
---

> [!note] Internal code change
> Previous code: `"3.3.1.3"` → New code: `PR-3-1-02-1` *(POA system renumbering, 2025-02)*

# Payment Confirmation Agent

> Automation of bank payment reconciliation on **n8n**: cross-references DPI deposits (QuickBooks) with pending payments in Ledger-9 and automatically confirms high-reliability matches (≥85% score), eliminating manual work from the accounting department.

---

## Status and progress

> Operational status, completeness and blockers → [[Documents/FOR-015-task-plan|FOR-015]] (source of truth) · Narrative history → [[Logbook]]

---

## Strategic alignment (2026 Matrix)

This project executes the following initiative from the [[Matriz-Estrategica-2026]]:

| Code | Strategic Initiative | Strategic Priority |
|---|---|---|
| IE1.2.1 | Consolidate WhatsApp and Nova as main collection channels | PE7 — CONTINUOUS OPERATIONAL IMPROVEMENT AND TACTICAL PROJECTS |

## Context and objective

**Problem it solves:**
The accounting department manually confirmed each payment that agents registered in Ledger-9 against bank deposits in DPI (QuickBooks). This process generated high operational load, delays, and potential reconciliation errors.

**Main objective:**
Automated agent in n8n that cross-references pending payments in Ledger-9 with DPI deposits twice a day (10 AM and 3 PM, M-F), automatically confirms matches with score ≥85%, and notifies Accounting by email. Cases without match are left for manual review.

**Platform adopted:** n8n Automation — provider: **Blue Scarf Solutions** ([[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo Cuadra]])

**In scope:**
- JavaScript matching algorithm (217 lines) in 2 tiers: comment + amount/bank/date
- Confidence level logic: very_high (≥0.85), high (≥0.70), medium
- Automatic match confirmation via POST `/confirmar-pago` to Ledger-9
- Ledger-9 APIs: GET `/pagos/no-confirmados`, GET `/dpi/no-confirmados`, POST `/confirmar-pago`
- Email notifications via Microsoft Outlook OAuth2 to accounting@meridiangroup.io
- Audit table in Ledger-9 database (fields: Case ID, Amount, Date, Bank)
- Scheduled execution: cron 10:00 and 15:00, Monday–Friday

**Out of scope:**
- Independent database for the agent
- Structural modifications to the Ledger-9 system
- Complex bidirectional integration
- Management of complex cases requiring human intervention
- Mass user training
- Long-term maintenance (defined post-implementation)

---

## Team

| Role | Person |
|---|---|
| Sponsor | [[Tomas-Navarro]] |
| Project Manager | [[Rodney-Ramirez]] |
| Provider / n8n Development | Blue Scarf Solutions — [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] |
| Technical support — Ledger-9 APIs and data | [[Sofia-Vargas]] |
| Infrastructure / OAuth2 | [[Isabella Torres]] |
| Ledger-9 database (audit table) | [[Alonso-Bracamonte\|Miguel]] |
| Additional technical support | [[Carlos-Ruiz]] |
| Technical validation | [[Elena Torres\|Elena Torres]] · [[Karina-Valdez]] |
| Additional stakeholder | [[Alex-Carver]] · [[Daniela-Rivas]] |
| End users / Certification | Accounting Department ([[Damian-Orozco\|Euris]]) |

---

## Technology stack

- **n8n Automation** — agent orchestrator (2 workflows)
- **Ledger-9 API** — internal REST API (`http://192.168.0.150`)
- **DPI API** — deposits REST API (QuickBooks/DPI)
- **Microsoft Outlook OAuth2** — email notifications (Microsoft Graph API)
- **JavaScript** — matching algorithm logic (217 lines)

---

## Milestones and deliverables

| Milestone | Actual Date | Status |
|---|---|---|
| Formal project kickoff | 2025-10-17 | 🟢 Completed |
| DPI test data delivered — REQ-001 | Oct 2025 | 🟢 Completed |
| Algorithm design and first version — REQ-002 | Dec 2025 | 🟢 Completed |
| Ledger-9 APIs operational — REQ-003 | Dec 2025 | 🟢 Completed |
| 3-state payment system — REQ-004 | Dec 2025 | 🟢 Completed |
| Demo with real data (26 Ledger-9 / 55 DPI, 5 confirmed) | 2026-02-03 | 🟢 Completed |
| Email notification node (Outlook OAuth2) | 2026-02-09 to 14 | 🟢 Completed |
| Audit table in Ledger-9 ([[Alonso-Bracamonte\|Miguel]]) | Week Feb 10–14 | 🟢 Completed |
| Technical documentation v3.0 delivered (Blue Scarf) | 2026-02-12 | 🟢 Completed |
| Production deployment (Sofia + Isabella Torres) | 2026-03-13 | 🟢 Completed |
| Formal handoff to Innovation team | 2026-03-19 | 🟢 Completed |
| Formal project closure | 2026-03-19 | 🟢 Completed |

---

## Key requirements

| ID | Brief description | Responsible | Status |
|---|---|---|---|
| REQ-001 | Validated DPI test data | [[Sofia-Vargas]] | ✅ Completed |
| REQ-002 | Ledger-9-DPI matching algorithm | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] | ✅ Completed (v3.0) |
| REQ-003 | Ledger-9 APIs for algorithm support | [[Sofia-Vargas]] | ✅ Completed |
| REQ-004 | 3-state payment handling | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] | ✅ Completed |
| REQ-005 | Incremental testing with growing volumes | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo]] + [[Sofia-Vargas\|Sofia]] | ✅ Completed |
| REQ-006 | ≥70% reduction in manual accounting workload | Whole team | ✅ Completed (21 auto-confirmed payments since 03/09, 0 false positives) |

See full detail: [[Documents/FOR-003-requirements-matrix]]

---

## Success criteria

- Matching score ≥85% (very_high) or ≥70% (high) for automatic confirmation ✅ implemented
- False positive rate <5% — pending measurement in production
- Automatic execution 2×/day (10 AM and 3 PM M-F) ✅ operational
- Email notifications to accounting@meridiangroup.io ✅ implemented
- Audit table with Case ID, Amount, Date, Bank ✅ created
- Formal Accounting approval (sign-off) — **pending**
- ≥70% reduction in manual confirmation time — pending measurement

---

## System versions

| Version | Date | Main changes |
|---|---|---|
| v1.0 | 2025-12-17 | Initial algorithm: amount + bank + date + comment |
| v2.0 | 2025-12-18 | Tolerance adjustments, optional comment |
| v3.0 | 2026-01-27 | Tier system, deduplication, txn_id, improved notifications |

---

## Active documents

| Document | Type | Description |
|---|---|---|
| [[Documents/FOR-001-project-sheet\|FOR-001]] | Project Sheet | Executive summary |
| [[Documents/FOR-002-project-charter\|FOR-002]] | Project Charter | Official charter |
| [[Documents/FOR-003-requirements-matrix\|FOR-003]] | Requirements Matrix | REQ-001 to REQ-006 updated |
| [[Documents/FOR-008-risk-matrix\|FOR-008]] | Risk Matrix | Updated status Feb 2026 |
| [[Documents/FOR-014-RACI-matrix\|FOR-014]] | RACI Matrix | Roles and responsibilities |
| [[Documents/FOR-015-task-plan\|FOR-015]] | Task Plan | Source of truth for % progress |
| [[Documents/Meridian Group-Sistema-Confirmacion-Pagos-Documentacion-Final.pdf\|Tech Doc v3.0]] | Technical documentation | Blue Scarf Solutions — Feb 12, 2026 |
| [[Minutes/Payment Confirmation Agent Meeting 2026-02-03.pdf\|Minute Feb 3]] | Minute | Technical demo with real data |
| [[Minutes/Payment Confirmation Agent - Notifications Node Meeting.pdf\|Minute Feb 9]] | Minute | Notifications node and final plan |
| [[Minutes/20260304-Payment-Confirmation-Agent-Checkpoint\|Minute Mar 4]] | Minute | Checkpoint: conservative algorithm validated, closure path |
| [[Minutes/20260319-Paso-a-Produccion-Payment-Confirmation-Agent\|Minute Mar 19]] | Minute | Production deployment confirmed — Formal project closure |

---

## Actionable tracking

- Actionables view for this project: [[Actionables]]
- Global view by project: [[Projects/Dashboard-Actionables-por-Proyecto]]
- Global view by person: [[Projects/Dashboard-Actionables-por-Persona]]

---

## Related links

- [[POA-2026]] — Strategic plan
- [[Projects/Madrugador-Tactico/README]] — Portfolio tracking
- [[Projects/Madrugador-Operativo/README]] — Operational standups
- [[Knowledge-Base/Processes/README]] — Reference SOPs
