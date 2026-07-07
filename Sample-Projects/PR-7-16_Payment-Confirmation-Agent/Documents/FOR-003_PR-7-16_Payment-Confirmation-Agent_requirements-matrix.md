# FOR-003 — Requirements Matrix

**Project:** Payment Confirmation Agent
**Code:** PR-7-16
**Date:** 2025-10-17
**Last update:** 2026-02-21
**Version:** 3.0

---

## Project Identification

| Field | Information |
| --- | --- |
| **Project Name** | Development of a Payment Confirmation Agent |
| **Code / Label** | PR-7-16 *(formerly: 3.3.1.3)* |
| **Main Sponsor** | [[Tomas-Navarro]] |
| **Project Manager** | [[Rodney-Ramirez]] |
| **Approval Status** | REQ-001 to REQ-005 completed · REQ-006 in final validation |
| **Platform implemented** | n8n Automation — Blue Scarf Solutions ([[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]]) · v3.0 delivered 2026-02-12 |

---

## 1. User Stories Matrix

| ID | User Story | Priority | Effort | Responsible | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| REQ-001 | As an agent developer I want access to validated DPI test data to confirm that my matching algorithm works correctly | Must | S | [[Sofia-Vargas]] | ✅ Completed | Data delivered Oct 2025. Allowed algorithm development to start. |
| REQ-002 | As a confirmation agent I want to automatically match Ledger-9 payments against DPI to identify which deposits correspond to which debtors | Must | L | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] | ✅ Completed | Implemented in n8n (JavaScript 217 lines, 2 tiers, confidence scores). v3.0 delivered 2026-02-12. |
| REQ-003 | As an agent developer I want the necessary Ledger-9 APIs to be created so the algorithm can operate correctly | Must | S | [[Sofia-Vargas]] | ✅ Completed | GET /pagos/no-confirmados, GET /dpi/no-confirmados, POST /confirmar-pago. Operational since Dec 2025. |
| REQ-004 | As a confirmation agent I want to handle 3 payment states (found confirmed, not found, pending) to process each case correctly | Must | S | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] | ✅ Completed | Implemented. very_high/high → automatic confirmation. medium → pending manual review. |
| REQ-005 | As a Project Manager I want to validate the algorithm with progressively larger data volumes to confirm scalability and performance | Must | M | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo]] + [[Sofia-Vargas\|Sofia]] | ✅ Completed | Demo Feb 3: 26 Ledger-9 / 55 DPI, 5 confirmed (91.67%-100%). System in daily operation. |
| REQ-006 | As an accounting user I want the system to automatically confirm payments with high reliability to reduce my manual workload | Must | XL | Whole team | 🟣 In Development | System operational and confirming payments daily. Pending formal Accounting sign-off. |

**Priority Legend:**
- **Must** — Critical. Without this the project does not work.
- **Should** — Important. Adds significant value.
- **Could** — Desirable. Improves experience.
- **Won't** — Out of scope. Not included in this phase.

**Effort Legend:**
- **XS** — 1–4 hours (minor configuration)
- **S** — 1 day (simple task)
- **M** — 2–3 days (standard development)
- **L** — 1 week (complex functionality)
- **XL** — >1 week (should be split)

**Requirement States:**
- **Defined** — Clear and documented requirement.
- **In analysis** — Technical team evaluating feasibility.
- **Approved** — Ready for development.
- **In Development** — Under active construction.
- **Blocked** — Identified impediment.
- **Completed** — Finished and validated by user.

---

## 2. Requirements Detail

### REQ-001: Validated DPI Test Data

**User Story:**
As a confirmation agent developer
I want access to validated DPI test data with confirmed correct cases
to validate that my matching algorithm works correctly and is not working "in the dark"

**Acceptance Criteria:**
- [ ] Condition 1: Receive at least 5 DPI cases with confirmed matching against Ledger-9
- [ ] Condition 2: Cases must include debtor name, amount, date and bank
- [ ] Condition 3: Each case must be marked as "correct" with the corresponding Ledger-9 ID
- [ ] Condition 4: Data must be manually validated successful cases (do not mix correct and incorrect initially)
- [ ] Condition 5: Delivery before noon on project start day

**It is done when:**
- [ ] [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo]] confirms receipt of the 5 test cases
- [ ] Data has all necessary information for matching
- [ ] Cases are validated as correct by [[Sofia-Vargas]]
- [ ] [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo]] can start algorithm development

**Dependencies:** [[Sofia-Vargas]] access to DPI and Ledger-9 database

**Required test data:** 5 DPI records with corresponding manual validated match in Ledger-9

---

### REQ-002: Ledger-9-DPI Matching Algorithm

**User Story:**
As a payment confirmation agent
I want to automatically match payments registered in Ledger-9 against unidentified deposits in DPI
to automatically reconcile which bank deposits correspond to which debtors

**Acceptance Criteria:**
- [ ] Condition 1: Algorithm must compare records using: debtor name, amount, date and bank
- [ ] Condition 2: Must handle name variations (upper/lower case, common abbreviations)
- [ ] Condition 3: Must calculate a match confidence level (high/medium/low)
- [ ] Condition 4: Only automatically confirm matches with high reliability (≥90%)
- [ ] Condition 5: Must correctly process the full base (~120 DPI records vs ~21 Ledger-9)
- [ ] Condition 6: Algorithm post-processing must work correctly

**It is done when:**
- [ ] Algorithm processes the full base and generates match reports
- [ ] Correct matching success rate is ≥90%
- [ ] Low confidence cases are marked for manual review
- [ ] Functionality validated with growing volumes (5 → 50 → 120+)
- [ ] [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo]] confirms algorithm is stable and accurate

**Dependencies:** REQ-001 (test data), REQ-003 (Ledger-9 APIs)

**Required test data:** Complete DPI database, Ledger-9 records with confirmed payments

---

### REQ-003: Ledger-9 APIs for Algorithm Support

**User Story:**
As a confirmation agent developer
I want the necessary Ledger-9 APIs to be created
so that the matching algorithm can operate correctly with the Ledger-9 system

**Acceptance Criteria:**
- [ ] Condition 1: APIs allow the matching algorithm to operate
- [ ] Condition 2: APIs are functional and stable
- [ ] Condition 3: Usage documentation is clear for [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo]]
- [ ] Condition 4: APIs integrate correctly with the developed algorithm

**It is done when:**
- [ ] APIs are created and working in test environment
- [ ] [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo]] confirms he can integrate them with the algorithm
- [ ] [[Sofia-Vargas]] validates that APIs meet technical specifications
- [ ] API usage is documented for future reference

**Dependencies:** REQ-002 (algorithm in development to define exact needs)

**Required test data:** Ledger-9 test environment with sandbox data

---

### REQ-004: Payment State Handling

**User Story:**
As a payment confirmation agent
I want to correctly handle the 3 possible payment states
to process each case appropriately and escalate those requiring human intervention

**Defined states:**
- **Found and Confirmed** → Agent automatically confirms the payment
- **Not Found** → System marks deposit as "unassigned" for manual review
- **Found but Pending** → System marks payment as "pending approval"

**Acceptance Criteria:**
- [ ] Condition 1: "Found and Confirmed" state → Agent automatically confirms
- [ ] Condition 2: "Not Found" state → Marks deposit as "unassigned" for manual review
- [ ] Condition 3: "Found but Pending" state → Marks payment as "pending approval"
- [ ] Condition 4: Each state is recorded in algorithm log
- [ ] Condition 5: Users can easily identify each state in the results

**It is done when:**
- [ ] All 3 states are processed correctly in the algorithm
- [ ] Pending and not found cases are appropriately identified
- [ ] Accounting department can easily identify cases requiring attention
- [ ] Validated with real cases of all 3 types

**Dependencies:** REQ-002 (matching algorithm)

**Required test data:** Test cases representing each of the 3 states

---

### REQ-005: Incremental Testing with Growing Volumes

**User Story:**
As a Project Manager
I want to validate the algorithm with progressively larger data volumes
to confirm that the system scales correctly and works under real production conditions

**Acceptance Criteria:**
- [ ] Condition 1: First validation with 5 confirmed correct cases
- [ ] Condition 2: Second validation with ~50 records (mixed cases)
- [ ] Condition 3: Third validation with full base (~120 DPI vs ~21 Ledger-9)
- [ ] Condition 4: Processing time remains acceptable at all volumes (<10 min)
- [ ] Condition 5: Matching accuracy remains ≥90% at all volumes
- [ ] Condition 6: [[Sofia-Vargas]] provides the necessary datasets for each phase

**It is done when:**
- [ ] All 3 testing phases with growing volumes are completed
- [ ] Performance and accuracy remain within acceptable parameters
- [ ] [[Partners/Contacts/Jose-Ricardo-Cuadra|Jose Ricardo]] confirms algorithm is stable at scale
- [ ] System behavior with different volumes is documented
- [ ] Accounting department validates results with real data

**Dependencies:** REQ-001 (test data), REQ-002 (complete algorithm), REQ-003 (APIs working)

**Required test data:** DPI and Ledger-9 data in incremental volumes provided by [[Sofia-Vargas]]

---

### REQ-006: Accounting Manual Workload Reduction

**User Story:**
As an accounting department user
I want the agent to automatically confirm payments with high reliability
to reduce my manual confirmation time by more than 70% and focus on complex cases

**Acceptance Criteria:**
- [ ] Condition 1: Agent automatically processes at least 70% of daily payments
- [ ] Condition 2: False positive rate <5%
- [ ] Condition 3: Cases requiring manual review are clearly identified
- [ ] Condition 4: Average confirmation time per payment is reduced by >70%
- [ ] Condition 5: Accounting department validates and approves functionality
- [ ] Condition 6: End users can effectively operate the system

**It is done when:**
- [ ] Confirmation time is measured before and after the agent
- [ ] Target 70% reduction in confirmation time is achieved
- [ ] Accounting department gives formal approval (sign-off)
- [ ] System usage process is documented
- [ ] Technical team ([[Elena Torres\|Elena Torres]], [[Karina-Valdez]], [[Carlos-Ruiz]]) approves final requirements

**Dependencies:** All previous REQs completed

**Required test data:** Baseline metrics of the current manual process

---

## 3. Non-Functional Requirements

| Category | Element | Detail |
| --- | --- | --- |
| **Performance** | Processing time | Full base processing in <10 minutes for ~120 records |
| | Concurrent users | Not applicable (automated agent) |
| | Availability | Execution based on operational need (daily or on demand) |
| **Accuracy and Quality** | Success rate | ≥90% correct matching |
| | False positives | <5% per Charter |
| | Variation handling | Process common name variations (upper/lower case, abbreviations) |
| **Security and Access** | Authentication | Per [[Meridian Group]] standards for Ledger-9 access |
| | Permissions | Only authorized accounting personnel access results |
| | Audit | Log of all automatic confirmations with confidence level |
| **Integrations** | Source systems | DPI (Unidentified Deposits) — bank database |
| | Target systems | Ledger-9 CRM — via APIs created by [[Sofia-Vargas]] |
| | Execution frequency | Based on operational need (initially on demand) |
| **Data and Storage** | Estimated volume | ~120 DPI records, ~21 Ledger-9 payments (current volumes) |
| | Retention | Matching logs for auditing per [[Meridian Group]] policies |
| | Scalability | Must work with larger volumes in the future |

---

## 4. Approvals

| Role | Name | Date | Status |
| --- | --- | --- | --- |
| Project Sponsor | [[Tomas-Navarro]] | 2025-10-17 | ⏳ Pending final sign-off |
| Technical provider | Blue Scarf Solutions ([[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]]) | 2026-02-12 | ✅ v3.0 documentation delivered |
| Technical support | [[Sofia-Vargas]] | 2025-10-17 | ✅ APIs and data completed |
| Technical validation | [[Karina-Valdez]] | 2026-02-03 | ✅ Participated in Feb 3 demo |
| End users | Accounting ([[Damian-Orozco\|Euris]]) | Pending | ⏳ Sign-off pending |
| Project Manager | [[Rodney-Ramirez]] | 2026-02-21 | Updated |

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | 2025-10-17 | [[Rodney-Ramirez]] | Initial version based on Project Charter |
| 2.0 | 2025-10-17 | [[Rodney-Ramirez]] | Reformulation post meeting: simplification from 18 to 6 tasks, responsibility corrections, emphasis on REQ-001 |
| 3.0 | 2026-02-21 | [[Rodney-Ramirez]] | Update to real status: REQ-001 to REQ-005 completed, REQ-006 in validation. Reflects n8n platform (Blue Scarf Solutions v3.0), Feb 3 demo and daily operation. |
