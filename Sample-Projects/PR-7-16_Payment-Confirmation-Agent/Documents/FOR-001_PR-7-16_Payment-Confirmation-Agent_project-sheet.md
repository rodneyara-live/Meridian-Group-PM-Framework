# FOR-001 — Project Sheet

**Project:** Payment Confirmation Agent
**Code:** PR-7-16
**Date:** 2025-10-17
**Version:** 1.0

---

## Project Identification

| Field | Information |
| --- | --- |
| **Project Name** | Development of a Payment Confirmation Agent |
| **Project Code** | PR-7-16 *(formerly: 3.3.1.3)* |
| **Company / Entity** | [[Meridian Group]] · [[Meridian-Pay]] |
| **Sponsor** | [[Tomas-Navarro]] |
| **Project Manager** | [[Rodney-Ramirez]] |
| **Start Date** | 2025-10-17 |
| **Target Date** | 2025-12-12 |

---

## Strategic Alignment

| Field | Information |
| --- | --- |
| **BSC Perspective** | Internal Processes (OE3.1) / Financial (OE1.1) / Customer (OE2.2) |
| **Strategic Objective** | Automation and operational intelligence |
| **Strategic Initiative** | PR-7-16 — Deployment of Multichannel AI Agents |

---

## Description

| Field | Information |
| --- | --- |
| **Problem / Opportunity Description** | The accounting department invests significant time manually confirming each payment registered in Ledger-9 against bank deposits (DPI). This manual process generates high operational load, delays, and potential reconciliation errors. |
| **Main Objective** | Develop an agent that automatically reconciles Ledger-9 payments with DPI deposits using an intelligent matching algorithm, confirming with ≥90% reliability and reducing manual workload by >70%. |

---

## Scope

| Field | Information |
| --- | --- |
| **In Scope** | Ledger-9-DPI matching algorithm (name, amount, date, bank) · 3-state payment logic · Ledger-9 APIs · Incremental testing (5→50→120 records) · Validation with accounting |
| **Out of Scope** | Independent database · Structural modifications to Ledger-9 · Complex bidirectional integration · Mass training · Long-term maintenance |

---

## Main Deliverables

| Field | Information |
| --- | --- |
| **Deliverables** | 1. Functional matching algorithm (REQ-002) · 2. Ledger-9 APIs for support (REQ-003) · 3. 3-state payment system (REQ-004) · 4. Incremental testing results (REQ-005) · 5. Validation of ≥70% manual workload reduction (REQ-006) |

---

## Success Criteria

| Field | Information |
| --- | --- |
| **Success Criteria** | Correct matching rate ≥90% · False positives <5% · Processing ~120 records in <10 min · ≥70% reduction in manual confirmation time · Accounting sign-off · Technical approval ([[Elena Torres\|Elena Torres]], [[Karina-Valdez]], [[Carlos-Ruiz]]) |

---

## Project Team

| Role | Person |
| --- | --- |
| Sponsor | [[Tomas-Navarro]] |
| Project Manager | [[Rodney-Ramirez]] |
| External developer (algorithm) | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] |
| Technical support — data and APIs | [[Sofia-Vargas]] |
| Additional technical support | [[Carlos-Ruiz]] |
| Technical validation | [[Elena Torres\|Elena Torres]] · [[Karina-Valdez]] |
| End users | Accounting Department |

---

## Summary Schedule

| Phase | Period | Key activities |
| --- | --- | --- |
| Phase 1 — Data and Design | Oct 17–24, 2025 | DPI data delivery (REQ-001) · Algorithm design |
| Phase 2 — Development | Oct 24 – Nov 7, 2025 | Matching algorithm · Ledger-9 APIs · 3 states |
| Phase 3 — Testing | Nov 7–28, 2025 | Testing 5→50→120 cases · Adjustments · Accounting validation |
| Go-live | December 2025 | Production deployment |

---

## Stakeholders

| Field | Information |
| --- | --- |
| **Main Stakeholders** | [[Tomas-Navarro]] (Sponsor) · Accounting Department (end users) · [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] (developer) · [[Sofia-Vargas]] (technical support) · [[Elena Torres\|Elena Torres]] · [[Karina-Valdez]] · [[Carlos-Ruiz]] (technical validation) |

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | 2025-10-17 | [[Rodney-Ramirez]] | Initial creation based on Charter v2.0 |
