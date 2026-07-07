# FOR-014 — RACI Matrix

**Project:** Payment Confirmation Agent
**Code:** PR-7-16
**PM:** [[Rodney-Ramirez]]
**Date:** 2025-10-17

---

## Project Identification

| Field | Information |
| --- | --- |
| **Project Name** | Development of a Payment Confirmation Agent |
| **Code / Label** | PR-7-16 |
| **Main Sponsor** | [[Tomas-Navarro]] |
| **Project Manager** | [[Rodney-Ramirez]] |
| **Creation Date** | 2025-10-17 |

---

## RACI Matrix by Project Activities

| Activity / Deliverable | [[Tomas-Navarro\|Bruno]] (Sponsor) | [[Rodney-Ramirez\|Rodney]] (PM) | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo]] (Dev) | [[Sofia-Vargas\|Sofia]] (Technical Support) | [[Carlos-Ruiz\|Luis]] (Technical Support) | [[Elena Torres\|Elena Torres]] / [[Karina-Valdez\|Marian]] (Validation) | Accounting (Users) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **PROJECT MANAGEMENT** | | | | | | | |
| Project Charter | A | R | C | C | I | C | I |
| Requirements Matrix | A | R | C | C | C | C | C |
| Schedule Management | A | R | C | C | I | I | I |
| Progress Reports to Sponsor | A | R | I | I | I | I | I |
| Technical requirements validation | C | A | C | C | C | R | I |
| **PHASE 1 — DATA AND DESIGN** | | | | | | | |
| REQ-001: Delivery of 5 validated DPI cases | I | A | C | R | C | I | I |
| Matching algorithm logic design | I | A | R | C | C | C | I |
| Automatic confirmation criteria definition | C | A | R | C | I | C | C |
| **PHASE 2 — DEVELOPMENT** | | | | | | | |
| REQ-002: Matching algorithm development | I | A | R | C | C | C | I |
| REQ-003: Ledger-9 API creation | I | A | C | R | C | I | I |
| REQ-004: 3-state payment implementation | I | A | R | C | C | C | C |
| Algorithm-API integration | I | A | R | R | C | I | I |
| **PHASE 3 — TESTING AND VALIDATION** | | | | | | | |
| REQ-005: Testing 5 initial cases | I | A | R | R | C | C | C |
| REQ-005: Testing ~50 records | I | A | R | R | C | C | C |
| REQ-005: Full base testing (~120 records) | I | A | R | R | C | C | C |
| REQ-006: Manual time reduction measurement | C | A | C | C | I | I | R |
| Final validation and accounting sign-off | A | R | C | C | I | C | R |
| **DOCUMENTATION** | | | | | | | |
| Algorithm documentation | I | A | R | C | I | C | I |
| Ledger-9 API documentation | I | A | I | R | C | I | I |
| Usage process documentation for accounting | C | R | C | C | I | I | A |

---

## RACI Legend

| Code | Meaning | Description |
| --- | --- | --- |
| **R** | Responsible | Person who executes the activity and is responsible for completing it |
| **A** | Accountable | Person with final authority who is answerable for the result |
| **C** | Consulted | Person whose opinion is sought before making decisions |
| **I** | Informed | Person who must be kept informed about progress |

---

## Main Roles and Responsibilities

### [[Tomas-Navarro]] — Sponsor

- Executive decision-making and resource unblocking
- Formal approval of Charter and final deliverables
- Recipient of progress reports at key milestones
- Authority for significant scope changes

### [[Rodney-Ramirez]] — Project Manager

- Project management, schedule and team communication
- Preparation of Charter, requirements and progress reports
- Weekly coordination with [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo]] and as needed with [[Sofia-Vargas]]
- Tracking of active risks and issues

### [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo Cuadra]] — External Developer (Algorithm)

- Design and implementation of Ledger-9-DPI matching algorithm
- Implementation of 3-state payment logic
- Algorithm integration with Ledger-9 APIs
- Execution and adjustment during incremental testing phases
- Technical algorithm documentation

### [[Sofia-Vargas]] — Technical Support (Data and APIs)

- Provision of DPI test data (5 validated cases — IMMEDIATE ACTION)
- Creation and maintenance of Ledger-9 APIs for algorithm support
- Dataset provisioning in each testing phase (5, 50, 120 records)
- Technical validation that APIs meet specifications

### [[Carlos-Ruiz]] — Additional Technical Support

- Backup technical support during development
- Support in testing stages as required by the team

### [[Elena Torres|Elena Torres]] / [[Karina-Valdez]] — Technical Validation

- Technical validation of documented requirements
- Review and approval of algorithm design
- Participation in key technical reviews during the project

### Accounting Department — End Users

- Provision of baseline metrics (current manual confirmation time)
- Participation in validation phases with real data
- Formal approval (sign-off) of the working system
- Validation of ≥70% workload reduction

---

## Version Control

| Version | Date | Modifications | Author |
| --- | --- | --- | --- |
| 1.0 | 2025-10-17 | Initial RACI Matrix creation | [[Rodney-Ramirez]] |
