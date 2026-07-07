---
type: meeting
subtype: client
company: fintrust
project: "Odoo CRM — Fintrust"
sprint:
date: 2026-01-09
participants: [Rodney-Ramirez, Carlos-Ruiz, Sergio-Mendoza, Elena Torres, Nicolas-Mercado]
facilitator: Rodney-Ramirez
tags: [meeting/client, company/fintrust, project/odoo-crm-fintrust]
---

# 📋 Review with Carlos Ruiz — Odoo CRM / Ledger-9 Gaps

**Date:** 2026-01-09
**Type:** Client / Technical Analysis
**Company:** Fintrust / Meridian Group
**Duration:** ~1h33m
**Participants:** [[Rodney-Ramirez]], [[Carlos-Ruiz]], [[Sergio-Mendoza]], [[Elena-Torres]], [[Nicolas-Mercado]]
**Facilitator:** [[Rodney-Ramirez]]

[[2025-12-19]] ← | → [[2026-01-13]]

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟡 At Risk (15%)

**Responsible:** [[Rodney-Ramirez]]

**Meeting Context:**
In-depth Functional Analysis session between the Meridian Group team and [[Carlos-Ruiz]] (Ledger-9 operations) so that [[Sergio-Mendoza]] (Odoo consultant) thoroughly understands how Ledger-9 works before defining the data model and architecture of the new CRM in Odoo.

---

## 📋 Ledger-9 Walkthrough — [[Carlos-Ruiz]]

[[Carlos-Ruiz]] gave a complete functional tour of the Ledger-9 system, covering the following modules:

### Portfolio Types
- **Own portfolio:** The company (Meridian Group) owns the credit. It manages the judicial process directly.
- **Third-party portfolio:** The external creditor assigns management to Meridian Group. Fintrust operates as a service company for that creditor.

### Extrajudicial Process
- Initial notifications to the debtor
- Negotiation and payment agreements
- Payment plans and follow-up
- Escalation to judicial process when applicable

### Judicial Process
- **Retentive seizure:** preventive retention of assets or funds
- **Bailiff acts:** diligences executed by the judicial officer; Ledger-9 tracks each act
- **ISL A (time control):** tracking of critical procedural deadlines, with expiration alerts
- **Integration with OpenKM:** document management via REST API; all judicial file documents live in OpenKM
- **Judicial letter:** generation of formal communications to the judiciary
- **Asset/fund seizure:** formalization and tracking of real precautionary measures

---

## 🗂️ Data Model — Proposal by [[Sergio-Mendoza]]

### Architecture Decision: Case-Centric Model

**Ledger-9** is individual-centric: case data is stored tied to the individual.

**Odoo** will adopt a **case-centric** model: the case is the central entity; individuals are linked to the case.

#### Case Entities
Each case can have multiple actors with differentiated roles:
- Principal debtor
- Co-debtor(s)
- Guarantor(s)
- Spouse(s) of each of the above

**Confirmation from [[Carlos-Ruiz]]:** A case can have multiple principal debtors. The same individual can appear in multiple cases with different roles (debtor in case A, guarantor in case B, co-debtor in case C).

#### Individual Entity — Minimum Fields
| Category | Fields |
|---|---|
| Identification (mandatory) | ID or passport |
| Complementary data | Name, date of birth, sex |
| Phones | N records: phone type + number + status (valid / incorrect / out of service) |
| Addresses | N records: address type + data |
| Emails | N records |

**Critical rule — contact history:** Phones, addresses and emails are **never deleted**. They are kept in history with validity status to avoid duplicates and preserve traceability. When a number becomes invalid, it is marked; it is not deleted.

---

## 📑 Data Dictionary

There are three versions of the filing file / data dictionary:
1. **First version** (complete data model): covers all Bonita↔CRM interactions; prepared by [[Rodrigo-Villalba]]
2. **Updated filing file:** extended fields including co-debtors, guarantors, spouses
3. **Bonita version:** green tab = minimum required for MVP; red tab = extended fields

**Decision:** [[Nicolas-Mercado]] will normalize the three versions into a single unified master dictionary.

**[[Sergio-Mendoza]]'s modeling base:** Bonita green tab (minimum required) as the starting point for the Odoo model.

---

## 🔍 Gap Analysis — [[Sergio-Mendoza]]'s Conclusions

[[Sergio-Mendoza]] presented his gap analysis document with the following functional modules identified:

| Module | Status in Standard Odoo |
|---|---|
| Client management | Partial — only `res.partner` reusable |
| Case actors (debtor, co-debtor, guarantor, spouse) | Does not exist — custom development |
| Case management (judicial file) | Does not exist — custom development |
| Case assembly process | Does not exist — custom development |
| Integration with Bonita | Does not exist — custom development |
| Document management (OpenKM REST API) | Does not exist — custom development |
| Master statuses (judicial state machine) | Does not exist — custom development |
| Activity disposition (status traceability) | Does not exist — custom development |

**General conclusion:** Virtually the entire legal/judicial module requires custom development. Odoo provides the framework (ORM, XML views, workflow engine), which saves time compared to development from scratch, but the judicial collection business logic is 100% to be built.

---

## ✅ Key Functional Requirements — [[Elena-Torres]] and [[Carlos-Ruiz]]

### Multi-company (multi-creditor) — from day 1
The CRM must support multiple creditors from the first version. It is not a deferred feature.

### Master Statuses
- Hierarchical/multi-level classification of judicial statuses
- Flexible and extensible (initially judicial, then extrajudicial)
- Based on the "Master Statuses" document that the legal team will complete

### Activity Disposition — **IN MVP SCOPE**
Complete traceability log of each status change in the case:
- **Who** made the change (human manager, automated process, Bonita, RPA, external service)
- **When**
- **From what status to what status**
- Standardized descriptions for certain dispositions (managers follow predefined formats)

**[[Elena-Torres]]'s position:** This functionality must not be left out of the MVP because it is the only place where the creditor can consult the real status of their case. Ledger-9 currently does NOT have a case status query interface — that is a critical gap that Odoo must resolve.

### Dimensional Change History — [[Nicolas-Mercado]]
When a manager changes areas or an individual's data changes, the system must keep a temporal history: what data was valid in each period.

**Confirmation from [[Sergio-Mendoza]]:** Odoo has native field tracking — you configure which fields to monitor and the system automatically records who changed what and when.

---

## 🏗️ Ecosystem Architecture — [[Sergio-Mendoza]]'s Diagram

```
Odoo Meridian Group (Judicial CRM)
  ↕ [Integration Service]
Odoo Fintrust (Billing / Services)
```

- **Odoo Meridian Group:** replaces Ledger-9 in judicial case management; it is the current implementation
- **Odoo Fintrust:** manages debts, invoices and payments for the service that Fintrust charges its clients (creditors)
- **Debtor payments** go directly to the creditor's accounts (Meridian Group or others); Fintrust does NOT receive or retain money
- **Fintrust charges a service fee** to creditors for managing judicial processes
- To set that fee, Fintrust needs to know the exact cost of each type of judicial management (resources, stages, personnel involved) → this justifies [[Nicolas-Mercado]]'s presence on the project to ensure financial granularity

**Pending:** [[Sergio-Mendoza]] will coordinate a call with [[Elena-Torres]] to clarify the scope of Fintrust's accounting.

---

## ✅ Decisions Made

- **Case-centric model in Odoo:** The case is the central entity; individuals are linked with roles. Decision: [[Sergio-Mendoza]] with confirmation from [[Carlos-Ruiz]] and [[Elena-Torres]]
- **Mandatory contact history:** Phones/addresses/emails are never deleted — they are kept with validity status. Decision: [[Sergio-Mendoza]] with backing from [[Carlos-Ruiz]]
- **Odoo is the case status master:** Bonita orchestrates the process; Odoo records and is the source of truth for the case status. Bidirectional synchronization required. Decision: [[Rodney-Ramirez]] with [[Elena-Torres]]
- **Activity disposition in MVP:** Status change traceability is NOT deferred — it is part of the MVP scope. Decision: [[Elena-Torres]] with agreement from [[Rodney-Ramirez]]
- **Unified master dictionary:** [[Nicolas-Mercado]] consolidates the three versions of the filing file into one. Decision: [[Rodney-Ramirez]]
- **Modeling base = Bonita green tab:** [[Sergio-Mendoza]] models Odoo from the minimum required by Bonita. Agreement: [[Sergio-Mendoza]] with [[Elena-Torres]]
- **Fintrust does not manage direct payments:** Payments go to the creditor; Fintrust charges a service fee. Confirmation: [[Carlos-Ruiz]] and [[Elena-Torres]]

---

## 🚨 Brechas / Gaps Identified

- 🔴 **Ledger-9 has no case status query interface** — there is no screen to check what status a file is in. Odoo must build this capability from scratch.
- 🔴 **100% custom development required** for the judicial module — only Odoo's `res.partner` is reusable.
- 🟡 **Ununified data dictionary** — three divergent versions; pending normalization by [[Nicolas-Mercado]].

---

## 📌 Pending Items

- [ ] [[Sergio-Mendoza]]: Update MVP diagram with terminology corrections and improve didactic graphics 📅 2026-01-12
- [ ] [[Sergio-Mendoza]]: Meet with [[Rodrigo-Villalba]] to validate Odoo MVP proposal vs. Bonita↔Ledger-9 integration map 📅 2026-01-11 🔥
- [ ] [[Sergio-Mendoza]]: Call [[Elena-Torres]] to clarify scope of Fintrust's accounting/billing 📅 2026-01-12
- [ ] [[Nicolas-Mercado]]: Normalize and unify master data dictionary (three versions → one) 📅 2026-01-13
- [ ] [[Rodney-Ramirez]]: Present gap analysis + gaps list + effort estimates + roadmap to senior management 📅 2026-01-13 🔥
- [ ] [[Nicolas-Mercado]]: Join technical sessions with [[Sergio-Mendoza]] and [[Rodrigo-Villalba]] — ongoing

---

## 📌 Next Meetings / Follow-ups

- [ ] Meeting with Fintrust senior management: Present macro gap analysis + estimates + MVP roadmap 📅 2026-01-13 (Tuesday) 3:00 PM 🔥

---

## 🔗 Triggers — Update after this meeting

- [ ] Technical gaps identified → [[FOR-003-requirements-matrix]]
- [ ] Architecture decisions (case-centric model, Odoo as status master) → [[FOR-003-requirements-matrix]]
- [ ] Risk: 100% custom development required → [[FOR-008_IE-1-1-3_Odoo-CRM-Fintrust_risk-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
