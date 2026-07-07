---
type: document
for: FOR-004
project: "IE-1-1-3"
hito: Milestone 1 — Operational Core
date_preparacion: 2026-02-19
tags: [document, test-plan, uat, milestone1, project, odoo, crm, fintrust]
---

# FOR-004 — Test Plan
## UAT Milestone 1 — Operational Core

**Project:** Case Management Module — Odoo 17 CRM Fintrust
**Project Code:** IE-1-1-3
**Project Manager:** Rodney Ramirez
**UAT Lead:** Hugo Pacheco
**Testing Period:** From: 02/23/2026 · To: 02/27/2026
**Environment:** Test environment — Fintrust Odoo 17 instance
**Preparation Date:** 2026-02-19

---

## Testing Objectives

### Main Objective

Validate that the Operational Core of the Case Management Module (Milestone 1) meets the acceptance criteria for the 10 defined user stories, is coherently navigable across the 4 main modules, and is ready to receive Milestone 2 (Integrations).

### Specific Objectives

- [ ] Verify complete Debtor registration and management (multiple phones, addresses, emails with types)
- [ ] Verify Creditor registration and management with associated products
- [ ] Verify the Case model (creation, folio, READ-ONLY status from UI)
- [ ] Verify correct Debtor and Debt association to a Case
- [ ] Verify registration of Garnishments, Activities, Notes and Legal Actions
- [ ] Verify navigation between the 4 modules is coherent and bidirectional (DebtorCase)
- [ ] Verify the audit trail (chatter) captures key changes
- [ ] Verify the Configuration modules (taxonomies) work correctly

---

## Test Scenarios

### Module: Configuration (prerequisite for other modules)

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-001 | Create phone types (Mobile, Landline, Work, Reference) | Hugo Pacheco | High | Pending |
| TC-002 | Create address types (Residential, Work, Alternative, Family) | Hugo Pacheco | High | Pending |
| TC-003 | Create email types (Personal, Work) | Hugo Pacheco | Medium | Pending |
| TC-004 | Create garnishable product types | Hugo Pacheco | Medium | Pending |

### HU-001: Debtor Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-005 | Create debtor with basic data: full name, ID number, sex, marital status, workplace | Hugo Pacheco | High | Pending |
| TC-006 | Add at least 3 phones with different types to the debtor; verify type and priority are saved correctly | Hugo Pacheco | High | Pending |
| TC-007 | Attempt to register a duplicate phone for the same debtor — the system must prevent or warn | Hugo Pacheco | High | Pending |
| TC-008 | Add multiple addresses with types (residential + work) to the debtor; verify mandatory fields | Hugo Pacheco | High | Pending |
| TC-009 | Add emails to the debtor; verify that contact history (phones/emails/addresses) cannot be deleted, only deactivated | Hugo Pacheco | Medium | Pending |
| TC-010 | Query the debtor's change log (chatter): verify it shows which field changed, who changed it and when | Hugo Pacheco | Medium | Pending |

### HU-002: Creditor Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-011 | Create creditor with basic data: name, RNC, address, contacts, associated internal/external lawyer | Hugo Pacheco | High | Pending |
| TC-012 | Associate products to the creditor (e.g., credit card, personal loan, written-off loan) — verify product list by creditor displays correctly | Hugo Pacheco | High | Pending |

### HU-003: Debt Product Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-013 | Register a debtor's financial obligation: original capital, updated balance, product type | Hugo Pacheco | High | Pending |
| TC-014 | Verify the debt breakdown fields (capital / interest / late fees / legal fees / ITB) display correctly | Hugo Pacheco | High | Pending |

### HU-004: Legal Case Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-015 | Create legal case with automatically generated unique number and folio | Hugo Pacheco | High | Pending |
| TC-016 | Verify that case status is READ-ONLY from Odoo interface (cannot be changed manually — only Bonita can update it) | Hugo Pacheco | High | Pending |
| TC-017 | Verify that the case correctly displays its creditor and associated product | Hugo Pacheco | Medium | Pending |

### HU-005: Debtor-to-Case Association

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-018 | Associate a main debtor to a case; verify the main debtor field appears prominently | Hugo Pacheco | High | Pending |
| TC-019 | Associate multiple debtors to the same case with different roles (principal, spouse, guarantor, surety) | Hugo Pacheco | High | Pending |
| TC-020 | Navigate from the case to the debtor profile and vice versa (bidirectional navigation CaseDebtor) | Hugo Pacheco | High | Pending |
| TC-021 | Verify that the same debtor can appear in multiple cases without duplicating their information | Hugo Pacheco | Medium | Pending |

### HU-006: Debt-to-Case Association

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-022 | Associate a financial obligation (debt) to an existing legal case | Hugo Pacheco | High | Pending |
| TC-023 | Verify that the case total balance correctly reflects the sum of associated debts | Hugo Pacheco | High | Pending |

### HU-007: Garnishment Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-024 | Register a garnishment for a debtor: withholding entity, amount, application date | Hugo Pacheco | High | Pending |
| TC-025 | Verify garnishments are visible from the debtor profile and from the case | Hugo Pacheco | Medium | Pending |

### HU-008: Activity Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-026 | Create a follow-up activity in a case (type: call, visit, document) | Hugo Pacheco | High | Pending |
| TC-027 | Plan a future activity with date, time and assigned responsible person | Hugo Pacheco | Medium | Pending |
| TC-028 | Mark activity as completed; verify it is recorded in the history | Hugo Pacheco | Medium | Pending |

### HU-009: Notes Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-029 | Register an internal note in a case; verify it remains in the notes history | Hugo Pacheco | Medium | Pending |

### HU-010: Legal Actions Management

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-030 | Register a legal action associated with a case (e.g., notification, lawsuit, garnishment order) | Hugo Pacheco | High | Pending |
| TC-031 | Verify that actions generated by Bonita appear in Odoo as READ-ONLY | Hugo Pacheco | High | Pending |

### General Navigation Tests

| ID | Test Scenario | Responsible | Priority | Status |
|---|---|---|---|---|
| TC-032 | Verify complete navigation across the 4 modules: Non-Judicial Management, Judicial Management, Case Management, Configuration | Hugo Pacheco | High | Pending |
| TC-033 | Verify that submenus of each module are complete and accessible | Hugo Pacheco | High | Pending |
| TC-034 | Verify role-based access control: Administrator (full view) vs. Tracking Operator (activities only, no amounts) | Hugo Pacheco | Medium | Pending |

---

## Acceptance Criteria

### Technical Criteria

- [ ] System responds in less than 5 seconds for standard operations (create, save, query)
- [ ] No server errors (500) in any High priority TC flow
- [ ] Test environment is available and stable throughout the UAT period (23–27/02)

### Functional Criteria

- [ ] All 31 High priority test cases execute successfully (no blocking critical observations)
- [ ] At least 85% of Medium priority test cases execute successfully
- [ ] Bidirectional navigation CaseDebtor works across all flows
- [ ] Chatter (audit trail) captures changes on Debtors and Cases correctly
- [ ] Configuration modules allow creation and use of taxonomies in forms

### Business Criteria

- [ ] Hugo Pacheco validates that the real operational flow (Fintrust judicial process) can be executed on the module
- [ ] The data model is consistent with the requirements approved on 02/04/2026
- [ ] Case status is not manually modifiable (critical integrity control with Bonita)

---

## Resources and Responsibilities

### Test Team

| Role | Name | Responsibility | Estimated dedication |
|---|---|---|---|
| Test Coordinator / PM | Rodney Ramirez | Coordinate UAT sessions, consolidate observations, communicate with developer | 30% of the week |
| UAT Lead / Key User | Hugo Pacheco | Execute all test cases, document observations, approve functionality | 60–80% of the week |
| Developer / Technical Support | Sergio Mendoza | Address technical queries during UAT, correct critical observations in parallel with Milestone 2 | Available during business hours |

### Required Technical Resources

- [ ] Access to Odoo 17 test environment — Fintrust instance
- [ ] Preloaded test data: at least 3 debtors, 2 creditors, 2 example cases
- [ ] User credentials for Hugo Pacheco (Administrator role and Operator role)
- [ ] Access to chatter and active audit module

---

## Go-Live Criteria (Milestone 1)

### Mandatory Criteria (all must be met)

- [ ] All **High** priority test cases completed successfully
- [ ] ≥85% of **Medium** priority test cases completed successfully
- [ ] Case status READ-ONLY verified (TC-016)
- [ ] Bidirectional navigation CaseDebtor verified (TC-020, TC-032)
- [ ] Hugo Pacheco signs formal UAT approval
- [ ] Rodney Ramirez validates and signs

### Desirable Criteria

- [ ] 100% of Medium priority cases passed without observations
- [ ] Basic performance test: create 10 consecutive cases without perceptible degradation

---

## UAT Observation Management

Observations found during UAT will be classified as follows:

| Type | Definition | Action |
|---|---|---|
| **Critical** | Prevents use of the main flow. Must be resolved before production go-live. | Sergio corrects before 02/28 |
| **Major** | Incomplete or incorrect functionality but has a workaround. | Sergio corrects in buffer Mar 2–6 |
| **Minor** | UI/UX detail or unexpected behavior but does not block the flow. | Parking lot for next phase |

---

## Contingency Plan

If at the close of 02/27 there are critical observations unresolved, the team will evaluate:
1. Extend the correction window with Sergio until 02/28 (day planned for Milestone 2 delivery)
2. Postpone the start of UAT Milestone 2 until Milestone 1 critical issues are resolved
3. Escalate to Sponsor (Elena Torres) if the impact affects the final delivery date (03/07)

---

## Approvals

### Plan Approval

| Role | Name | Date | Signature |
|---|---|---|---|
| **Project Manager** | Rodney Ramirez | | |
| **UAT Lead** | Hugo Pacheco | | |
| **Developer** | Sergio Mendoza | | |

### Results Approval (to be completed at UAT closure)

| Role | Name | Date | Decision | Signature |
|---|---|---|---|---|
| **UAT Lead** | Hugo Pacheco | | Approved / Rejected | |
| **Project Manager** | Rodney Ramirez | | Approved / Rejected | |

### Final Decision

**MILESTONE 1 PRODUCTION GO-LIVE:** [ ] APPROVED [ ] REJECTED [ ] POSTPONED

**Approved Go-Live Date:** ___________________________

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2026-02-19 | Rodney Ramirez | Initial version — 34 test cases for HU-001 to HU-010 + navigation |
