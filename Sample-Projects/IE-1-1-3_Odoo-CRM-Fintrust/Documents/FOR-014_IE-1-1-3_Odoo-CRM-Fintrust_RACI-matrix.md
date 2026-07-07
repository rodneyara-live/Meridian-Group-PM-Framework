---
type: document
for: FOR-014
project: "IE-1-1-3"
date_creacion: 2026-02-19
tags: [document, raci, roles, project, odoo, crm, fintrust]
---

# FOR-014 — RACI Matrix

**Project:** Case Management Module — Odoo 17 CRM Fintrust
**Code:** IE-1-1-3
**Sponsor:** Elena Torres
**Project Manager:** Rodney Ramirez
**Creation Date:** 2026-02-19

---

## RACI Matrix by Project Activity

> **Column abbreviations:** OS = Elena Torres · RR = Rodney Ramirez · SC = Sergio Mendoza · EM = Hugo Pacheco · LM = Carlos Ruiz · RDC = Alex Carver · ED = Nicolas Mercado · FB = Rodrigo Villalba

| Activity / Deliverable | OS (Sponsor) | RR (PM) | SC (Dev) | EM (UAT) | LM (Business) | RDC (Business) | ED (Ops) | FB (Ext. Arch.) |
|---|---|---|---|---|---|---|---|---|
| **PROJECT MANAGEMENT** | | | | | | | | |
| Project Charter (FOR-002) | A | R | C | C | C | C | I | — |
| Test Plan (FOR-004) | I | A | C | R | I | I | I | — |
| Risk Matrix (FOR-008) | I | R | C | C | I | C | I | C |
| Weekly Status Reports (FOR-007) | I | R | C | I | I | I | I | — |
| Change Requests (FOR-009) | A | R | C | C | C | C | I | C |
| Issue Log (FOR-010) | I | R | C | C | I | I | I | C |
| **ANALYSIS AND REQUIREMENTS PHASE** | | | | | | | | |
| Gap analysis Odoo vs. Fintrust model | I | A | R | C | C | C | I | C |
| Functional analysis and Ledger-9 sessions | I | A | R | C | R | C | C | C |
| Data model definition (entities and relationships) | I | A | R | C | C | A | I | C |
| User Stories (HU-001 to HU-010) | I | A | R | C | C | C | I | — |
| MockUps / Functional view design | I | A | R | C | C | C | I | — |
| Formal requirements closure | A | R | C | C | C | C | I | — |
| **DEVELOPMENT PHASE — MILESTONE 1 (OPERATIONAL CORE)** | | | | | | | | |
| HU-001: Debtor Management | I | A | R | I | I | I | I | — |
| HU-002: Creditor Management | I | A | R | I | I | I | I | — |
| HU-003: Debt Product Management | I | A | R | I | I | I | I | — |
| HU-004: Legal Case Management | I | A | R | I | I | I | I | — |
| HU-005: Debtor-to-Case Association | I | A | R | I | I | I | I | — |
| HU-006: Debt-to-Case Association | I | A | R | I | I | I | I | — |
| HU-007: Garnishment Management | I | A | R | I | I | I | I | — |
| HU-008: Activity Management | I | A | R | I | I | I | I | — |
| HU-009: Notes Management | I | A | R | I | I | I | I | — |
| HU-010: Legal Actions Management | I | A | R | I | I | I | I | — |
| Configuration Module (taxonomies) | I | A | R | I | I | I | I | — |
| Role-based access control (Admin / Operator) | I | A | R | C | I | I | I | — |
| Formal Milestone 1 delivery | I | A | R | I | I | I | I | — |
| **DEVELOPMENT PHASE — MILESTONE 2 (INTEGRATIONS)** | | | | | | | | |
| Bidirectional BonitaOdoo integration (case status) | I | A | R | I | I | C | I | C |
| OpenKM integration (case documents) | I | A | R | I | I | I | I | C |
| Data synchronization from Ledger-9 (batch) | I | A | R | I | C | C | C | C |
| Formal Milestone 2 delivery | I | A | R | I | I | I | I | — |
| **UAT AND CERTIFICATION** | | | | | | | | |
| UAT execution Milestone 1 (Operational Core) | I | A | C | R | I | I | I | — |
| Consolidation and reporting of Milestone 1 observations | I | R | C | A | I | I | I | — |
| Correction of critical Milestone 1 observations | I | A | R | C | I | I | I | — |
| UAT execution Milestone 2 (Integrations) | I | A | C | R | I | C | I | C |
| Correction of Milestone 2 observations | I | A | R | C | I | I | I | C |
| Final approval and production go-live | A | R | C | C | I | C | I | — |
| **PROJECT CLOSURE** | | | | | | | | |
| Final Project Report (FOR-012) | I | R | C | C | I | I | I | — |
| Lessons Learned (FOR-013) | I | R | C | C | C | C | C | — |
| Access and technical documentation handover (GitHub) | I | A | R | I | I | I | I | — |

---

## RACI Legend

| Code | Meaning | Description |
|---|---|---|
| **R** | Responsible (Executes) | Person who performs the work and is responsible for completing it |
| **A** | Accountable (Approves) | Person with final authority who is answerable for the result. Only one A per activity. |
| **C** | Consulted | Person whose opinion is sought before making decisions or advancing |
| **I** | Informed | Person who must be kept aware of progress and results |
| **—** | Not applicable | Has no participation in this activity |

---

## Main Roles and Responsibilities

### Elena Torres — Project Sponsor

- Authorize formal project start and its resources
- Make strategic decisions when escalated by PM
- Approve scope changes impacting budget or critical dates
- Receive weekly status reports and act when required

### Rodney Ramirez — Project Manager

- Coordinate all project phases (analysis, development, UAT, closure)
- Manage communication between stakeholders and developer
- Consolidate and prioritize UAT observations
- Keep project documents (FORs) updated
- Escalate risks and issues to Sponsor when appropriate
- Formally freeze scope and manage change requests

### Sergio Mendoza — Lead Developer

- Design technical architecture of the module on Odoo 17
- Develop the 10 user stories of Milestone 1
- Develop Bonita, OpenKM and Ledger-9 integrations of Milestone 2
- Keep technical documentation updated on GitHub
- Address and resolve UAT observations within agreed deadlines
- Proactively report any technical blocker to PM

### Hugo Pacheco — UAT Lead / Key User

- Lead and execute all test cases from the Test Plan (FOR-004)
- Document observations in detail (steps to reproduce, evidence)
- Validate that Fintrust's real operational flow can be executed on the module
- Sign formal UAT approval at each milestone close
- Prioritize highest operational risk scenarios in UAT sessions

### Carlos Ruiz — Business Stakeholder

- Provide judicial and extrajudicial process requirements for Fintrust
- Validate that the data model correctly reflects business operations
- Clarify functional questions during analysis and Milestone 2 UAT
- Define integration strategy with external systems (Bonita, Ledger-9)

### Alex Carver — Business Stakeholder / Architecture

- Approve data model and entity relationships
- Validate business technical decisions (case structure, debtor roles)
- Supervise that development respects the defined architecture
- Align with Rodney on the implementation plan

### Nicolas Mercado — Operations

- Participate in functional analysis sessions as operational representative
- Support with data dictionary information (normalization)
- Receive status reports for internal operational coordination
- Coordinate with the team on test data availability

### Rodrigo Villalba — Architect / Integrations (External)

- Provide Bonita and OpenKM API technical documentation
- Technical consultant for bidirectional BonitaOdoo integration in Milestone 2
- Validate integration architecture before coding
- Coordinate access and availability of Bonita environment for UAT Milestone 2

---

## Version Control

| Version | Date | Changes | Author |
|---|---|---|---|
| 1.0 | 2026-02-19 | Initial version — 8 roles, 40+ activities mapped | Rodney Ramirez |
