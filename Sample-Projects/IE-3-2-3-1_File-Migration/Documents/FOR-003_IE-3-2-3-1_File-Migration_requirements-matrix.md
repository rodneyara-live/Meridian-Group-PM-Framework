---
type: document
for: FOR-003
project: "IE-3-2-3-1"
date_creacion: 2026-03-03
ultima_actualizacion: 2026-03-03
version: 1.0
tags: [document, requirements, project, file, migration]
---

# FOR-003 — Requirements Matrix
## File Migration

**Project:** File Migration (IE-3-2-3-1)
**Company:** [[Meridian Group]]
**PM:** [[Rodney-Ramirez]]
**Main source:** Formal project kickoff — 2026-03-03
**Version:** 1.0

---

## 1. Definitions

| Term | Definition |
|---|---|
| **Functional Requirement (FR)** | What the system/process must do — behaviors, flows and operations |
| **Non-Functional Requirement (NFR)** | How it must perform — quality, security, compliance, performance |
| **Business Requirement (BR)** | Why the project exists — strategic and operational needs |
| **Constraint (C)** | Condition that limits project design or execution |
| **Priority** | 🔴 Critical · 🟠 High · 🟡 Medium · 🟢 Low |
| **Status** | ⚪ Pending · 🟣 In analysis · ✅ Approved · ❌ Discarded |

---

## 2. Requirements Summary

| Category | Quantity |
|---|---|
| Business Requirements | 5 |
| Functional Requirements | 14 |
| Non-Functional Requirements | 7 |
| Constraints | 6 |
| **Total** | **32** |

---

## 3. Business Requirements

> Strategic and operational needs that justify the project. Source: FOR-002 v3.0 + kickoff 2026-03-03.

| ID | Requirement | Priority | Source | Status |
|---|---|---|---|---|
| BR-001 | Reduce file department operational costs through specialized outsourcing (personnel, space, maintenance) | 🔴 Critical | FOR-002 / POA-2026 | ✅ Approved |
| BR-002 | Free up physical spaces currently occupied by files to redirect them to higher-value activities | 🔴 Critical | FOR-002 / Kickoff | ✅ Approved |
| BR-003 | Have the new operational logistics model before March 30, 2026 | 🔴 Critical | Kickoff 2026-03-03 | ✅ Approved |
| BR-004 | Ensure no document is migrated without HL-quality digital backup | 🔴 Critical | Kickoff 2026-03-03 | ✅ Approved |
| BR-005 | Maintain operational continuity without interrupting access to critical documents throughout the transition | 🟠 High | FOR-002 | ✅ Approved |

---

## 4. Functional Requirements

### 4.1 Document Categorization and Classification

| ID | Requirement | Priority | Source | Responsible | Status |
|---|---|---|---|---|---|
| FR-001 | The process must physically separate originals from photocopies before any transfer. Photocopies with digital equivalent are not archived or transferred. | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-002 | Documents must be classified into two categories: **Permanent Local** (active mortgage, promissory notes in process) and **Transitory to offsite archive** (everything else). | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-003 | Original promissory notes are kept in local archive only when a client actively requests them. Their custody at offsite archive is the normal state. | 🟠 High | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-004 | Documents for active cases in mortgage registration or chattel registry remain in-house until process closure. Then they are transferred to offsite archive. | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |

### 4.2 Scanning and Digitization

| ID | Requirement | Priority | Source | Responsible | Status |
|---|---|---|---|---|---|
| FR-005 | All documents must be scanned at HL quality level before being packed in any batch for offsite archive transfer. HL scanning is a **mandatory gate**. | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-006 | The process must include batch-level scanning quality verification before authorizing dispatch. A batch is not dispatched if it has documents without confirmed HL scanning. | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-007 | High-criticality documents (promissory notes, deeds, original contracts) must be digitized and backed up before starting Phase 3 of physical migration. | 🔴 Critical | FOR-008 R-001 | [[Elena-Torres]] | ✅ Approved |

### 4.3 Transitory Local File

| ID | Requirement | Priority | Source | Responsible | Status |
|---|---|---|---|---|---|
| FR-008 | The local file must have: (1) one fireproof filing cabinet for permanent documents, and (2) two regular filing cabinets for transitory documents awaiting weekly dispatch. | 🟠 High | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-009 | The document entry flow to the transitory file must follow the protocol: document arrives → registered with case number → placed in the corresponding transitory cabinet. | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-010 | Transitory filing cabinets must be completely emptied once per week (Monday or Friday). Weekly offsite archive dispatch is not optional. | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |

### 4.4 Traceability and Inventory

| ID | Requirement | Priority | Source | Responsible | Status |
|---|---|---|---|---|---|
| FR-011 | Each batch of transferred documents must have a delivery-receipt form signed by Meridian Group and offsite archive with verified count. | 🔴 Critical | FOR-008 R-001 | [[Elena-Torres]] | ✅ Approved |
| FR-012 | The document inventory is the central traceability control. No document may migrate if it is not in the inventory. | 🔴 Critical | Kickoff 2026-03-03 | [[Elena-Torres]] | ✅ Approved |
| FR-013 | The process must allow validation at any time that 100% of migrated documents appear in the inventory and none is outside it. | 🟠 High | Kickoff 2026-03-03 | [[Rodney-Ramirez]] | ✅ Approved |

### 4.5 Destruction Policy (Pending)

| ID | Requirement | Priority | Source | Responsible | Status |
|---|---|---|---|---|---|
| FR-014 | The process must have a formal policy for destruction of notified/purified acts post-scanning (e.g., mass garnishments) before starting Phase 3. This policy requires formal management decision. | 🟠 High | Kickoff 2026-03-03 | [[David-Carver]] / [[Carlos-Ruiz]] | ⚪ Pending |

---

## 5. Non-Functional Requirements

| ID | Requirement | Category | Priority | Source | Status |
|---|---|---|---|---|---|
| NFR-001 | **Traceability:** Every document movement (transfer, query, loan, return) must be recorded with date, responsible person and case number. | Traceability | 🔴 Critical | FOR-002 / Kickoff | ✅ Approved |
| NFR-002 | **Security:** Documents in offsite archive custody must be in an area segregated from the provider's other clients, with restricted access control. | Security | 🔴 Critical | FOR-008 R-005 | ✅ Approved |
| NFR-003 | **Legal compliance:** The model must comply with Law 172-13 on Personal Data Protection and Superintendence of Banks regulations throughout its execution. | Regulatory | 🔴 Critical | FOR-002 | ✅ Approved |
| NFR-004 | **Provider SLAs:** The contract with offsite archive must establish maximum response times: urgent ≤ 2 hours, priority ≤ 24 hours, regular ≤ 48 hours. | Performance | 🟠 High | FOR-008 R-006 | ✅ Approved |
| NFR-005 | **Continuity:** At no point in the process can access to critical active documents be interrupted. High-turnover documents are digitized before migrating. | Availability | 🔴 Critical | FOR-002 / FOR-008 R-002 | ✅ Approved |
| NFR-006 | **Scanning quality:** The minimum digitization quality standard is HL (high resolution legible). Blurry, cropped or illegible scans are not accepted. | Quality | 🔴 Critical | Kickoff 2026-03-03 | ✅ Approved |
| NFR-007 | **Personnel management:** The transition of affected personnel must strictly comply with applicable labor law, with a communication plan coordinated with HR. | People | 🟠 High | FOR-002 | ✅ Approved |

---

## 6. Constraints

| ID | Constraint | Impact | Status |
|---|---|---|---|
| C-001 | **Operational deadline:** The new logistics model must be operational before March 30, 2026. | Schedule | ✅ Confirmed |
| C-002 | **No destruction of originals in Phase 1:** No originals are destroyed during the first project phase. Destruction policy is a later decision. | Scope | ✅ Confirmed |
| C-003 | **Provider already selected:** The provider is **offsite archive**. Evaluating alternative providers is not within scope of this project. | Scope | ✅ Confirmed |
| C-004 | **No IT system changes:** This project does not include modifications to information systems, transactional databases or implementation of new electronic document management systems. | Scope | ✅ Confirmed |
| C-005 | **Labor personnel:** Any change in the file department personnel structure requires prior coordination with HR and compliance with applicable labor law. | People | ✅ Confirmed |
| C-006 | **Scope changes:** All scope changes require FOR-009 Change Request approved by the Sponsor before execution. | Governance | ✅ Confirmed |

---

## 7. Requirements Pending Definition

| ID | Description | Blocked by | Responsible | Deadline |
|---|---|---|---|---|
| RP-001 | Formal policy for destruction of purified acts post-scanning (FR-014) — requires management decision | Decision by [[David-Carver]] / [[Carlos-Ruiz]] | [[Rodney-Ramirez]] | 2026-04-04 |
| RP-002 | Exact volume and document typology of the department — not yet inventoried | Start of inventory in Phase 1 | [[Elena-Torres]] | 2026-03-14 |
| RP-003 | Definitive contractual SLAs with offsite archive — pending negotiation | offsite archive commercial proposal + negotiation | [[Tomas-Navarro]] | 2026-04-04 |
| RP-004 | Detail of active documents by process (mortgage, chattel registry) that remain in-house | Inventory + coordination with operational areas | [[Elena-Torres]] | 2026-03-21 |

---

## 8. Requirements-to-Phase Traceability Matrix

| Requirement ID | Phase 1 — Analysis | Phase 2 — Preparation | Phase 3 — Migration | Phase 4 — Stabilization |
|---|---|---|---|---|
| BR-001, BR-002 | Inventory and cost analysis | Model design | Execution | Verify savings |
| BR-003 | ✅ Active target | ✅ Active target | — | — |
| BR-004, FR-005, FR-006, NFR-006 | Define HL checklist | Implement gate | Apply per batch | Audit |
| FR-001, FR-002, FR-003, FR-004 | Identify categories | Formalize flows | Apply categorization | Verify |
| FR-008, FR-009, FR-010 | Acquire cabinets | Define protocol | Operate model | Measure |
| FR-011, FR-012, FR-013, NFR-001 | Design inventory | Traceability protocol | Batch forms | Inventory audit |
| NFR-002, NFR-003, NFR-005 | — | offsite archive contract | Facility audit | Regulatory validation |
| NFR-004, FR-014 | — | SLA negotiation / destruction decision | — | SLA monitoring |
| NFR-007, C-005 | — | HR plan | Personnel transition | — |

---

## 9. Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2026-03-03 | [[Rodney-Ramirez]] | Initial version — gathered from the formal kickoff on 2026-03-03 with [[David-Carver]], [[Tomas-Navarro]], [[Elena-Torres]] and [[Rodney-Ramirez]] |

---

*FOR-003 Form · File Migration (IE-3-2-3-1) · [[Projects/IE-3-2-3-1_File-Migration/Documents/README]] · [[Knowledge-Base/Templates/project-templates/README|form index]]*
