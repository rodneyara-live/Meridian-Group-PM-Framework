---
type: meeting
subtype: mixed
company: meridiangroup
project: "Odoo CRM — Fintrust"
sprint:
date: 2026-01-14
participants: [Rodney-Ramirez, Nicolas-Mercado, Elena Torres, Hugo-Pacheco, Sergio-Mendoza, Rodrigo-Villalba]
facilitator: Rodney-Ramirez
tags: [meeting/mixed, company/meridiangroup, project/odoo-crm-fintrust]
---

# 📋 Gap Analysis Review CRM Odoo — Client Session

**Date:** 2026-01-14
**Type:** Mixed (Meridian Group + Ledger-9 + GAF + Bonita Integration)
**Company:** Meridian Group / Fintrust / Ledger-9
**Duration:** ~65m
**Participants:** [[Rodney-Ramirez]], [[Nicolas-Mercado]], [[Elena-Torres]], [[Hugo-Pacheco]], [[Sergio-Mendoza]], [[Rodrigo-Villalba]]
**Facilitator:** [[Rodney-Ramirez]]

[[2026-01-12]] ← | → [[2026-01-16]]

> **Note:** This VTT was saved with the PLACEHOLDER tag in the original name, indicating provisional nomenclature at the time of recording.

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟣 In Progress (22%)

**Responsible:** [[Rodney-Ramirez]]

**Meeting Context:**
[[Sergio-Mendoza]] formally presented the Odoo CRM gap analysis to the expanded team — including [[Elena-Torres]] and [[Hugo-Pacheco]] from Ledger-9. The meeting covered: (1) Fintrust/Odoo's macro process, (2) the proposed entity-relationship model, (3) a critical debate on bidirectional status integration between Odoo and Bonita, and (4) the need to include judicial process fields generated in Bonita within the CRM.

---

## 🗂️ Fintrust Macro Process in Odoo — [[Sergio-Mendoza]]

[[Sergio-Mendoza]] presented the diagram of the general process that Odoo will need to manage, currently operating in Ledger-9 and migrating to Odoo:

**Functional modules identified:**

- **Non-Judicial Management:** Debtor registration, phones, addresses and debtor assets; collection follow-up; activities prior to legal instance
- **Judicial Management (Bonita as orchestrator):** Case processing, seizure management, judicial processes; Bonita acts as a black box for the BPMN flow
- **External integrations (future):** Bonita (already in use), OpenKM as document manager (via REST API)

**Odoo modules installed in the Fintrust instance to date:**
CRM, Contacts, Sales, Invoicing, Purchases, Accounting, Cost Center, Expenses, Inventory, Employees. All standard modules already installed.

**4 major custom processes identified by Sergio:**
1. Debtor management (phone and address registration)
2. Case management (file modeling — central entity)
3. Bonita integration API (case submission, status reception)
4. Activity management (chronological case tracking)

---

## 🏗️ Proposed Data Model — [[Sergio-Mendoza]]

### Base Entities (inherit from `res.partner`)

| Entity | Description |
|---|---|
| **Debtor** | Debtor — natural or legal person with the debt |
| **Creditor** | Creditor — bank/financial institution that assigns the portfolio |
| **Ganchi** | Entities to seize (banks, employers, institutions) |
| **Supplier** | Case supplier / system that sends the cases |

> **Clarification from [[Elena-Torres]]:** The "creditor" in Ledger-9 terms would be Banco de Reservas (or another bank). Meridian Group acts as intermediary/manager.

### Debtor Model

Custom fields identified on `res.partner`:
- `debtor_phone` (separate table: type, country code, number, valid?)
- `debtor_address` (separate table: type [home/office/other], address, valid?)
- `Deceased?` (boolean)
- `Gender` (male/female)
- N phones and N addresses per debtor — unlimited, 1:N relationship

### Creditor Model

Custom fields:
- Creditor code
- Creditor type
- Portfolio
- Currency (will support multiple currencies for regional expansion)
- Report frequency
- Main contact, billing contact, legal contact
- Reference (who provides the case)
- Active (yes/no)

### Case Model — Central Entity

Fields from Ledger-9's filing model taken as base:

| Field | Description |
|---|---|
| Bonita ID | Case identifier in Bonita |
| Ledger-9 external ID | For cross-reference with Ledger-9 / other systems |
| Batch ID | Upload batch identifier |
| Correlative | Sequential number |
| Filing date | Case entry date |
| Entry source | Case origin (system/file/manual) |
| Filing status | Status at time of filing |
| Rejection reason | If the case was rejected |
| Capital amount | Principal debt amount |
| Total balance | Total outstanding balance |
| Real estate? | Boolean: debtor has real estate |
| Guarantor? | Boolean |
| Spouse? | Boolean |
| Prior process | Has prior process? |
| Validated documents | Document validation status |
| Judicial address | Address for judicial notifications |
| Confirmed address | Boolean |
| Migration status | If coming from migration |
| Migration origin | Which system it migrated from |
| Current phase | Process phase |
| Created by / Modified by | Standard Odoo audit |

---

## 🏦 Debtor Bank Accounts — Include in the Model?

[[Elena-Torres]] clarified that **Ledger-9 does not handle debtor bank accounts**, and Fintrust will not need them either:

- The seizure is notified to a list of banking entities via bailiff (ministerial)
- The bank internally verifies if the debtor has an account and proceeds according to the order
- Fintrust operates "blindly" with respect to banks — it does not know which bank the debtor has an account with
- [[Hugo-Pacheco]] confirmed: the process is to send the list of clients to seize, the bank decides if it proceeds

> **Decision:** Debtor bank accounts are **outside the current model** (optional field in the future if a particular case justifies it).

---

## ⚙️ Critical Debate: Bidirectional Integration Bonita ↔ Odoo (Statuses)

This was the most extensive and technical debate of the meeting.

### Initial Position of [[Sergio-Mendoza]]

Based on his previous meeting with [[Rodrigo-Villalba]], Sergio understood that:
- Bonita would use the **"insert activity"** service (LEONa01) each time it changes status
- This would leave a historical record in Odoo's CRM
- But **the case status in Odoo would not be directly updated** — only the activity saying "Bonita changed to status X" would remain

### Position of [[Elena-Torres]] — NON-NEGOTIABLE

Elena Torres refuted this clearly:
> "We had agreed that yes. It must return the status because we had discussed it, it is bidirectional, I have to have the statuses updated in both places."

**Argument:** Odoo's CRM must be the **central query source** for each case status. Bonita is an orchestrator — it is not a CRM and does not have a general interface for customer service agents to query statuses. If Nova (service agent) takes a call from a debtor, she queries in Odoo, not in Bonita.

### Confirmation from [[Rodrigo-Villalba]]

Francisco clarified the current architecture:
- In Bonita's user stories, it is already contemplated that each status change calls the "insert activity" service in Odoo
- This records the Bonita status change in Odoo's case history
- The technical distinction: insert activity ≠ update the case's `status` field
- The "insert activity" service is flexible and can be extended to also update the case status if decided

### Agreed Resolution

**[[Elena-Torres]] defined the MVP requirement:**
> "From the MVP, everything Bonita does must leave a trace in Odoo."

This includes:
- Bonita's current case status (field in the Odoo case)
- Historical activity/log of each status change
- Even waiting periods (e.g.: "entered a 7-day waiting period on day X")

**Technical conclusion:**
- An additional service (or extension of the existing one) is needed to update the case status in Odoo, in addition to the activity log
- Elena Torres: "I would do it separately — one for activity, and within the activity I can decide whether to change the status or not with a parameter"
- Sergio: confirmed the model supports this without structural changes — it is additional business logic

---

## 📋 Judicial Process Fields (Bonita → Odoo)

[[Elena-Torres]] identified a gap: the fields generated during judicial processes in Bonita (appointed court, hearing date, etc.) are not contemplated in Odoo's data model.

**Elena Torres's argument:**
> "Bonita generates legal process data that Ledger-9 does not provide. I need to have that visible in Odoo."

Example: sub-cases / sub-processes — a loan can have 4 simultaneous active judicial processes. Odoo must be able to show all of them.

**[[Sergio-Mendoza]]'s response:**
- The proposed model already has the structure to support additional fields without refactoring
- Adding Bonita fields means adding one or two fields to the case + a new API service
- What is needed is a **Bonita flow analysis** to identify exactly which fields the judicial process generates

**Pending identified:** Analyze Bonita flows to extract the fields that must be synchronized to Odoo — Elena Torres will request this from the Bonita team.

---

## 🔄 Sub-Processes / Sub-Cases

[[Elena-Torres]] introduced the concept of Bonita sub-process:
- A case in Ledger-9 (1 loan) can generate multiple judicial processes in Bonita
- E.g.: 4 judicial processes opened simultaneously for the same loan
- Bonita handles them as sub-processes
- **Requirement:** Odoo must be able to display all active processes associated with a case

---

## ✅ Decisions Made

- **Debtor bank accounts:** Outside the current model. They are not recorded; the seizure operates blindly with the list of banking entities. Decision: [[Elena-Torres]] + [[Hugo-Pacheco]]
- **Bidirectional status integration Bonita ↔ Odoo is NON-NEGOTIABLE from MVP:** Every status change in Bonita must also update the case status field in Odoo, and leave a historical record (activity log). Decision: [[Elena-Torres]]
- **Status update service:** A parameter is added to the insert activity service (or a separate service) to update the case status in Odoo. Technical decision: [[Rodrigo-Villalba]] + [[Sergio-Mendoza]]
- **Model supports additional Bonita fields:** Adding judicial process fields generated by Bonita is extensible without structural refactoring. Decision: [[Sergio-Mendoza]]
- **Sergio's next deliverable:** User Stories for Monday (2026-01-19). Decision: [[Sergio-Mendoza]] with [[Elena-Torres]]

---

## 🚨 Gaps Identified

- 🔴 **Bidirectional statuses not originally contemplated:** Sergio understood that Bonita would only insert activities without updating the case status in Odoo. Resolved: requires additional service / extension of the existing one
- 🟡 **Bonita judicial process fields missing in Odoo model:** Appointed court, hearing date, and other data generated during judicial orchestration must be mapped. Pending Bonita flow analysis
- 🟡 **Bonita sub-processes without representation in Odoo:** A case can have N active sub-processes in Bonita; Odoo must be able to query them all
- 🟡 **Francisco + Sergio alignment pending:** Confirm with [[Rodrigo-Villalba]] the exact list of fields that Bonita will generate and that must be replicated in Odoo

---

## 📌 Pending Items

- [ ] [[Sergio-Mendoza]]: Deliver complete User Stories with mapped fields 📅 2026-01-19 🔥
- [ ] [[Sergio-Mendoza]]: Incorporate into the data model the fields identified in this session (bidirectional statuses, sub-processes) 📅 2026-01-19
- [ ] [[Rodrigo-Villalba]] + [[Sergio-Mendoza]]: Align on fields that Bonita generates during judicial processes to include in Odoo 📅 2026-01-16
- [ ] [[Elena-Torres]]: Validate with Bonita team the judicial flows and extract list of candidate fields to synchronize with Odoo 📅  2026-01-16
- [ ] [[Rodrigo-Villalba]]: Confirm technical design of update-status vs. insert-activity service 📅 2026-01-16
- [ ] [[Nicolas-Mercado]]: Pass notes from the final part of the meeting to [[Rodney-Ramirez]] (Rodney left before closing)

---

## 📌 Next Meetings / Follow-ups

- [ ] Meeting [[Sergio-Mendoza]] + [[Rodrigo-Villalba]]: Alignment on Bonita→Odoo fields and integration service design 📅 2026-01-16
- [ ] User Stories review with expanded team 📅 wk 2026-01-19

---

## 🔗 Triggers — Update after this meeting

- [ ] Bidirectional integration Bonita ↔ Odoo (statuses updated in both systems from MVP) → [[FOR-003-requirements-matrix]]
- [ ] Bonita judicial process fields in Odoo model → [[FOR-003-requirements-matrix]]
- [ ] Bonita sub-processes in Odoo → [[FOR-003-requirements-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
