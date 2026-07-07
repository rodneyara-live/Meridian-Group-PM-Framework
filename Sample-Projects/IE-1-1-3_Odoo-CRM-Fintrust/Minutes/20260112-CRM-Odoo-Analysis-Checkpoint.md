---
type: meeting
subtype: internal
company: meridiangroup
project: "Odoo CRM — Fintrust"
sprint:
date: 2026-01-12
participants: [Rodney-Ramirez, Carlos-Ruiz, Sergio-Mendoza, Elena Torres, Alex-Carver]
facilitator: Rodney-Ramirez
tags: [meeting/internal, company/meridiangroup, project/odoo-crm-fintrust]
---

# 📋 Checkpoint — CRM Odoo Gap Analysis

**Date:** 2026-01-12
**Type:** Internal / Technical Checkpoint
**Company:** Meridian Group / Fintrust
**Duration:** ~33m
**Participants:** [[Rodney-Ramirez]], [[Carlos-Ruiz]], [[Sergio-Mendoza]], [[Elena-Torres]], [[Alex-Carver]]
**Facilitator:** [[Rodney-Ramirez]]

[[2026-01-09]] ← | → [[2026-01-13]]

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟣 In Progress (20%)

**Responsible:** [[Rodney-Ramirez]]

**Meeting Context:**
Checkpoint session where [[Sergio-Mendoza]] presented the CRM Odoo gap analysis diagram against the existing ecosystem (Ledger-9, Bonita, OpenKM). The team reviewed what is available in standard Odoo, what requires custom development, and how the specification delivery to GAF (Odoo implementing company) will be coordinated.

---

## 🗂️ Gap Analysis Diagram — [[Sergio-Mendoza]]

### Ecosystem Presented

[[Sergio-Mendoza]] presented a three-layer diagram structuring the integration ecosystem:

**Layer 1 — Standard Odoo (reusable components):**
- CRM and contacts (base module, mandatory)
- Sales and invoicing
- Purchases
- Basic document management (native Odoo — limited)
- API framework (built-in integration tools)
- Users and access

**Layer 2 — Custom Development Required:**
- **Legal case module:** judicial file management (central system entity)
- **Legal roles:** principal debtor, co-debtor, guarantor, spouse
- **Seizure management:** retentive, assets, funds
- **Legal API:** bidirectional Odoo↔Bonita integration
- **Preselected cases:** case selection logic for processing
- **External case identifier:** mapper to creditor systems
- **Legal document management:** integration with OpenKM (document send/search via REST)

**Layer 3 — External Integrations:**
- **Bonita:** BPMN orchestrator; Odoo sends it the case and receives status updates
- **OpenKM:** document management via REST API (upload, download, search)
- **Creditor's CRM:** integration contemplated but conditional (see debate below)

[[Carlos-Ruiz]] confirmed that the diagram correctly captures Bonita's three functional segments: document download/upload, evidence/compulsory/official letter management, and BPMN with retentive seizures, judicial letters and time control (ISL A).

---

## 🏦 Debate: Integration with Creditor CRM

[[Carlos-Ruiz]] noted that an integration with the creditor's external CRM (beyond Ledger-9 — any bank, cooperative or financial institution) was missing from the diagram. This generated an important debate about client onboarding strategy.

**Position of [[Elena-Torres]] and [[Rodney-Ramirez]]:**
Banks and institutional creditors will not open API access to their internal systems due to security restrictions. What Fintrust will receive in practice is a batch upload file with the cases to manage.

**[[Rodney-Ramirez]]'s metaphor:** Fintrust's CRM should be a "scaffolding" — a generic skeleton covering 80–85% of the data delivered by any client (bank, cooperative, financial institution) and operational with minimal modifications. It is not an exhaustive superstructure, but a generic and adaptable structure.

**Position of [[Alex-Carver]]:** The focus should be on the elementary data to manage any case: debt amount, balance, currency, case ID, ID number, multiple phones, relationships between parties. What Odoo needs is exactly what Bonita will ingest.

**Team agreement:** Direct API integration with creditor CRMs is out of immediate scope. The practical route is file upload. The CRM must be prepared to receive data from any client in a standardized way.

---

## 🔍 Key Requirement: Traceability and Timestamps — [[Alex-Carver]]

[[Alex-Carver]] identified a critical requirement that Ledger-9 currently does not meet: every activity and every status change must have its **timestamp** (who, when, from what status to what).

**Ledger-9's current gap:** When a case changes status in Ledger-9, there is no record of when the change occurred. Only the current snapshot is visible. This makes auditing and historical reporting impossible.

**Confirmation from [[Elena-Torres]]:** "That is a non-negotiable point." Odoo and Bonita must speak the same statuses and Odoo must record the traceability of each status transition as "activity disposition" — who, when, through what channel.

---

## 🏗️ Base Entities of the Data Model

[[Sergio-Mendoza]] identified the central entities that must start development:

- **Case** (judicial file — central entity)
- **Debtor** (debtor — role within the case)
- **Creditor** (creditor — portfolio origin)
- **Supplier** (case-related service provider)
- **Guaranty** (guarantor — role within the case)

These are the "basic entities to start" that form the model's core. The relationships between these entities (an individual can be a debtor in one case and a guarantor in another) are the heart of the case-centric model.

---

## 📦 Installation Status in Odoo Fintrust

| Module | Status |
|---|---|
| Accounting | ✅ Already installed and active |
| CRM | ⏳ Pending installation (one click) |
| Purchases | ⏳ Pending installation (one click) |
| Basic document management | ⏳ Module to be installed |
| Legal case module | 🔴 Custom development pending |

**Note:** Installing the missing standard modules (CRM, purchases) does not require development — it is immediate configuration.

---

## 🔄 Delivery Process to GAF

**[[Alex-Carver]]'s question:** What exactly does GAF need to start development? Functionality list? Database field list? Screen mockups?

**[[Sergio-Mendoza]]'s response:** Everything that appears in the diagram as non-standard (orange part + intersection). The delivery process is:
1. **User story** (describes the flow and objective)
2. **Mockup** of the screen or interface
3. **Database structure** (description of the table/model objective)
4. **Effort estimate** → GAF confirms development time

**Strategy agreed by [[Elena-Torres]]:** Do not wait until everything is complete to go to GAF. Deliver incrementally, module by module in order of priority and dependencies. Start with what the team has most certain and clear.

**Prioritization criteria:** [[Elena-Torres]] instructed [[Sergio-Mendoza]] to identify dependencies between modules and prioritize the development order considering what blocks what.

**Example of first priority module:** The address and phone structure — it is what the team has most clear and defined.

---

## 📄 Rodrigo Villalba Integration Document

[[Rodney-Ramirez]] clarified the difference between the available documents:

- **Filing file:** it is a minimum kickoff document — not the complete source
- **Complete data model** (tab in [[Rodrigo-Villalba]]'s document): lists all fields that interact between Bonita and Ledger-9 — **this is the document [[Sergio-Mendoza]] needs as reference**

[[Sergio-Mendoza]] confirmed that Francisco's integration document is what he needs to correctly map the fields. He has a meeting tomorrow AM with [[Rodrigo-Villalba]] to review it.

**Ledger-9 APIs master catalog:** [[Rodney-Ramirez]] reported that [[Ana-Teresa-Peguero]] already delivered the Ledger-9 APIs master catalog to [[Rodrigo-Villalba]]. The link will be shared in the project's WhatsApp group so the entire team has it as reference. The status of each API will be validated in tomorrow's meeting.

---

## ✅ Decisions Made

- **Creditor integration strategy:** There will be no direct API integration with bank/creditor CRMs. Data will arrive via batch upload file. The CRM must absorb that file in a standardized way. Decision: [[Rodney-Ramirez]] with backing from [[Elena-Torres]] and [[Alex-Carver]]
- **Incremental delivery to GAF:** Do not wait for everything to be ready. Prioritized modules will be delivered with user stories + mockups + DB structure. Decision: [[Elena-Torres]]
- **Prioritization by dependencies:** [[Sergio-Mendoza]] will identify dependencies between modules and establish the delivery order to GAF. Decision: [[Elena-Torres]] with [[Sergio-Mendoza]]
- **Reference document = Bonita's complete data model:** Not the minimum filing file, but [[Rodrigo-Villalba]]'s complete model with all Bonita↔Ledger-9 interactions. Decision: [[Rodney-Ramirez]] with [[Sergio-Mendoza]]
- **CRM and Bonita must speak the same statuses:** Odoo's status catalog must be identical to Bonita's to guarantee bidirectional synchronization. Decision: [[Elena-Torres]]
- **Mandatory timestamps on all activities:** Every activity and status change must record who, when and from what status to what. Non-negotiable for MVP. Decision: [[Alex-Carver]] with [[Elena-Torres]]

---

## 🚨 Brechas / Gaps Identified

- 🔴 **Ledger-9 does not record status change timestamps** — critical gap; Odoo must resolve it from the MVP: every status transition must be audited with date/time
- 🟡 **Document management in Odoo vs. OpenKM** — pending confirmation: Odoo's standard document management is basic; all the weight goes into the integration with OpenKM; must align with [[Rodrigo-Villalba]] what stays in Odoo and what goes to OpenKM
- 🟡 **Ledger-9 APIs catalog pending validation** — the catalog delivered by [[Ana-Teresa-Peguero]] must be validated in a meeting with [[Rodrigo-Villalba]] to confirm which APIs are operational

---

## 📌 Pending Items

- [ ] [[Sergio-Mendoza]]: Prepare formalized user stories + field mapping for priority modules, starting with address/phone structure, creditors and statuses 📅 2026-01-13
- [ ] [[Sergio-Mendoza]]: Meeting with [[Rodrigo-Villalba]] tomorrow AM to review Bonita↔Ledger-9 integration document and align fields 📅 2026-01-13 🔥
- [ ] [[Sergio-Mendoza]]: Update gap analysis diagram with adjustments discussed in this meeting 📅 2026-01-13
- [ ] [[Sergio-Mendoza]]: Identify dependencies between modules and establish priority order for delivery to GAF 📅 2026-01-13
- [ ] [[Rodney-Ramirez]]: Share link to the complete data model (Francisco's Bonita tab) in the project group 📅 2026-01-12 🔥
- [ ] [[Rodney-Ramirez]]: Share link to the Ledger-9 APIs master catalog (received from [[Ana-Teresa-Peguero]]) in the group 📅 2026-01-12
- [ ] Validate Ledger-9 APIs catalog: confirm status of each API with [[Rodrigo-Villalba]] 📅 2026-01-13

---

## 📌 Next Meetings / Follow-ups

- [ ] Meeting [[Sergio-Mendoza]] + [[Rodrigo-Villalba]]: Review Bonita↔Odoo integration document, field alignment and Ledger-9 APIs 📅 2026-01-13 AM 🔥
- [ ] Review meeting with [[Elena-Torres]] + [[Sergio-Mendoza]] (night): Finalize documentation for delivery to GAF 📅 2026-01-13 (night)
- [ ] Presentation to Fintrust senior management: Gap analysis + estimates + MVP roadmap 📅 2026-01-13 3:00 PM 🔥

---

## 🔗 Triggers — Update after this meeting

- [ ] Creditor batch upload strategy (no direct API integration) → [[FOR-003-requirements-matrix]]
- [ ] Decision: mandatory timestamps on activities/statuses → [[FOR-003-requirements-matrix]]
- [ ] Base data model entities (Case, Debtor, Creditor, Supplier, Guaranty) → [[FOR-003-requirements-matrix]]
- [ ] Ledger-9 APIs catalog pending validation → [[FOR-008_IE-1-1-3_Odoo-CRM-Fintrust_risk-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
