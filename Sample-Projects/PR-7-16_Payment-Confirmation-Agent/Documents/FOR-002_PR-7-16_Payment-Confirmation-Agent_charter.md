# FOR-002 — Project Charter

**Project:** Payment Confirmation Agent
**Code:** PR-7-16
**Date:** 2025-10-17
**Version:** 2.0

---

## General Information

| Field | Information |
| --- | --- |
| **Project Name** | Development of a Payment Confirmation Agent |
| **Project Code** | PR-7-16 *(formerly: 3.3.1.3)* |
| **Project Sponsor** | [[Tomas-Navarro]] |
| **Project Manager** | [[Rodney-Ramirez]] |
| **Preparation Date** | October 17, 2025 |
| **Document Version** | 2.0 |

---

## Purpose and Justification

| Field | Information |
| --- | --- |
| **Project Purpose** | Automate the payment confirmation process through a virtual agent that validates and reconciles payments registered in Ledger-9 with actual bank entries (DPI) using an intelligent matching algorithm. |
| **Business Justification** | The accounting department invests significant time manually confirming each payment registered in Ledger-9. This process generates: high operational load, delays in payment confirmation, potential reconciliation errors, and constant need for manual validation. |
| **Expected Benefits** | • Reduction of payment confirmation time by more than 70% · • Freed accounting resources for higher-value tasks · • Improved bank reconciliation accuracy · • Automated confirmations with high reliability · • Reduced human errors in payment assignment |

---

## Objectives

| Field | Information |
| --- | --- |
| **Project Objectives** | 1. Develop a matching algorithm that automatically reconciles Ledger-9 payments with bank deposits (DPI) · 2. Implement reconciliation logic based on: debtor name, amount, date and bank · 3. Automatically confirm payments with high confidence level (≥90% accuracy) · 4. Create Ledger-9 APIs to support algorithm operation · 5. Reduce operational load of the accounting department |

---

## Scope

| Field | Information |
| --- | --- |
| **Includes** | • Ledger-9-DPI matching algorithm (name, amount, date, bank) · • Automatic reconciliation logic with confidence level (high/medium/low) · • 3-state handling: found confirmed / not found / found pending · • Ledger-9 APIs for algorithm support · • Incremental testing: 5 → 50 → ~120 records · • Validation with real cases and adjustments based on accounting feedback |
| **Does Not Include** | • Independent database for the agent · • Structural modifications to the Ledger-9 system · • Complex bidirectional integration with Ledger-9 API · • Management of complex cases requiring human intervention · • Mass user training · • Long-term maintenance (defined post-implementation) |

---

## Assumptions and Constraints

| Field | Information |
| --- | --- |
| **Assumptions** | • DPI test data will be available from day 1 ([[Sofia-Vargas]]) · • Payments will have sufficient information for reliable matching · • [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] is available for development · • Internal team ([[Sofia-Vargas]] and [[Carlos-Ruiz]]) can provide technical support · • Current volume is manageable (~120 DPI vs ~21 Ledger-9) |
| **Constraints** | • Development by a single external resource (individual provider) · • Maximum development time: 2 months · • Only matches with confidence ≥90% will be automatically confirmed · • Dependency on [[Sofia-Vargas]] for test data and Ledger-9 APIs |

---

## Main Risks

| Field | Information |
| --- | --- |
| **Identified Risks** | 1. **Test data availability:** Delay in delivering validated cases — Mitigation: [[Sofia-Vargas]] confirmed delivery before noon · 2. **External developer availability:** Sole external resource — Mitigation: Close coordination and weekly follow-up · 3. **Input data quality:** Name variations or incomplete information — Mitigation: Algorithm will handle common variations and only confirm high-confidence matches · 4. **Algorithm scalability:** Performance with larger volumes — Mitigation: Incremental testing (5→50→120 cases) |

---

## Project Team

| Field | Information |
| --- | --- |
| **Team Structure** | **Sponsor:** [[Tomas-Navarro]] · **Project Manager:** [[Rodney-Ramirez]] · **External developer:** [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] (matching algorithm) · **Technical support — data and APIs:** [[Sofia-Vargas]] · **Additional technical support:** [[Carlos-Ruiz]] · **Technical validation:** [[Elena Torres\|Elena Torres]] · [[Karina-Valdez]] · **End users:** Accounting Department |

---

## High-Level Schedule

| Field | Information |
| --- | --- |
| **Total Duration** | 2 months (target: 8 weeks from 17-Oct-2025) |
| **Phase 1 — Data and Design (Week 1)** | [[Sofia-Vargas]] delivers 5 validated DPI-Ledger-9 cases (immediate) · [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo]] designs algorithm logic · Definition of automatic confirmation criteria |
| **Phase 2 — Development (Weeks 2–3)** | Matching algorithm development · Reconciliation logic implementation · 3-state payment handling · [[Sofia-Vargas]] creates Ledger-9 APIs |
| **Phase 3 — Testing and Adjustments (Weeks 3–4)** | Testing with 5 validated cases · Testing with ~50 records · Testing with full base (~120 DPI vs ~21 Ledger-9) · Adjustments and validation with accounting |
| **Main Milestones** | Day 1: Test data delivered · Week 2: Design approved · Week 4: First functional version · Week 5: Ledger-9 APIs created · Week 7: Testing completed · Week 8: Go-live |

---

## Resources and Budget

| Field | Information |
| --- | --- |
| **Required Resources** | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] (external, part-time) · [[Sofia-Vargas]] (internal) · [[Carlos-Ruiz]] (internal, support) |
| **Estimated Budget** | To be defined (external resource [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo]] — rate to be agreed) |

---

## Acceptance Criteria

| Field | Information |
| --- | --- |
| **Acceptance Criteria** | **Core functionality:** Algorithm reconciles Ledger-9 with DPI comparing name, amount, date and bank · **Accuracy:** Matching ≥90% · False positives <5% · **Scalability:** Works with 5, 50 and 120+ records in acceptable times · **Integration:** Ledger-9 APIs functional and validated by [[Sofia-Vargas]] · **Validation:** Accounting Department approval + measurable ≥70% reduction in manual confirmation · **Documentation:** Algorithm and APIs documented |

---

## Communication

| Field | Information |
| --- | --- |
| **Communication Plan** | Weekly follow-up between PM ([[Rodney-Ramirez]]) and developer ([[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo]]) · Coordination with [[Sofia-Vargas]] based on operational need · Progress report to Sponsor ([[Tomas-Navarro]]) at key milestones · Technical validation with [[Elena Torres\|Elena Torres]], [[Karina-Valdez]] and [[Carlos-Ruiz]] upon requirements completion |

---

## Approvals

| Role | Name | Date | Status |
| --- | --- | --- | --- |
| Sponsor | [[Tomas-Navarro]] | 2025-10-17 | Pending signature |
| Project Manager | [[Rodney-Ramirez]] | 2025-10-17 | Prepared |
| Technical validation | [[Elena Torres\|Elena Torres]] · [[Karina-Valdez]] · [[Carlos-Ruiz]] | Pending | Pending |

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | 2025-10-17 | [[Rodney-Ramirez]] | Initial version |
| 2.0 | 2025-10-17 | [[Rodney-Ramirez]] | Reformulation post follow-up meeting: technical scope simplification, reduction from 18 to 6 tasks, responsibility corrections, work sequence clarification |
