

# FOR-002 — Project Charter
## Odoo 17 CRM Fintrust

---

## General Information

| Field | Information |
| --------------------------- | ----------------------------------------------- |
| **Project Name** | Case Management Module — Odoo 17 CRM Fintrust |
| **Project Code** | IE-1-1-3 |
| **Project Sponsor** | [[Elena-Torres]] |
| **Project Manager** | [[Rodney-Ramirez]] |
| **Lead Developer** | Sergio Mendoza |
| **Organization** | Meridian Group / Fintrust |
| **Preparation Date** | 2026-02-19 |
| **Document Version** | 1.0 |

---

## Purpose and Justification

| Field | Information |
| --- | --- |
| **Project Purpose** | Develop a custom Case Management module integrated in Odoo 17 that enables Fintrust to manage receivables management legal processes in a centralized and structured manner. |
| **Business Justification** | Fintrust operates in the legal-financial receivables management sector and requires a platform that unifies management of debtors, creditors, judicial files, garnishments and legal actions. Odoo's native CRM module does not cover these domain-specific requirements, necessitating a custom extension on the already installed and production-ready Odoo 17 infrastructure. |
| **Expected Benefits** | Centralization of case and debtor information on a single platform; complete traceability of judicial and non-judicial actions; reduction of errors from manual file handling; audit trail (chatter) for compliance and control; scalable technology base for future integrations (DGII, WhatsApp, NetCollector). |

---

## Objectives

| Field | Information |
| --- | --- |
| **Main Objective** | Deliver a functional Case Management module on Odoo 17, covering the 10 defined and validated user stories, in production for Fintrust before March 7, 2026. |
| **Secondary Objectives** | (1) Ensure data model integrity while respecting Odoo's base architecture (res.partner). (2) Enable complete change traceability per file. (3) Complete UAT with the internal team within established deadlines. |

---

## Scope

### Includes — 10 User Stories

| ID | User Story | Description |
| --- | --- | --- |
| HU-001 | Debtor Management | Registration and management of debtors with multiple phones (with type and priority), multiple addresses, emails and historical tracking. |
| HU-002 | Creditor Management | Registration of creditors with contact data, associable to judicial cases. |
| HU-003 | Debt Product Management | Control of debtor's financial obligations: original capital, current balance, credit product type. |
| HU-004 | Legal Case Management | Creation and management of legal files with unique number, folio and process status. |
| HU-005 | Debtor-to-Case Association | Linking one or more debtors to a case, with roles (principal, spouse, guarantor) and individual statuses. |
| HU-006 | Debt-to-Case Association | Linking financial obligations to a case to support legal actions. |
| HU-007 | Garnishment Management | Registration of garnishments applied to debtors, with withholding entities and retention details. |
| HU-008 | Activity Management | Operational tracking and planning of activities per case (calls, visits, documents). |
| HU-009 | Notes Management | Registration of observations and internal notes history per file. |
| HU-010 | Legal Actions Management | Registration and tracking of legal actions associated with a case. |

### Menu Structure (4 modules)

| Menu | Submodules |
| --- | --- |
| **Non-Judicial Management** | Debtors, Creditors, Garnishees, Suppliers, Debt Products |
| **Judicial Management** | Blacklists, Acts, Garnishments, Lifts, Legal Processes |
| **Case Management** | Cases, Activities |
| **Configuration** | Phone types, Address types, Email types, Garnishable product types, Products and Services |

### Does NOT Include (Out of Scope)

| Excluded | Reason |
| --- | --- |
| Electronic Invoicing (DGII) | Separate project; in progress with Andira Partners (IE-1-1-3) |
| WhatsApp Business API Integration | Separate project; pending strategic definition |
| Data migration — Meridian Pay instance | Coordination pending with internal resources |
| Accounting and purchasing modules | Already implemented by Andira Partners; in production |
| Andira Partners post-production support | Andira Partners has concluded its phase; CRM is Meridian Group internal development |

---

## Assumptions and Constraints

| Field | Information |
| --- | --- |
| **Assumptions** | (1) Odoo 17 is installed and in production for the Fintrust instance. (2) The base accounting and purchasing modules are already implemented by Andira Partners. (3) Test environments are available for Fintrust. (4) Functional requirements have been validated and closed (January–February 2026). (5) Sergio Mendoza has full availability during the development period. (6) The functional design documents, user stories and timeline are the scope baseline. |
| **Constraints** | (1) Final delivery date is immovable: March 7, 2026. (2) Development must respect Odoo's standard architecture (res.partner as contact base). (3) The development budget does not include additional hours for undocumented scope changes. (4) Any scope change must be processed via FOR-009 Change Request. |

---

## Main Risks

| ID | Risk | Probability | Impact | Mitigation |
| --- | --- | --- | --- | --- |
| R-001 | Tight timeline (dev + UAT in ~3 weeks) | High | High | Parallelize Milestone 1 UAT with Milestone 2 start; daily follow-up |
| R-002 | Dependency on a single developer (Sergio Mendoza) | Medium | High | Continuous technical documentation on GitHub; proactive blocker communication |
| R-003 | Late scope changes impacting delivery | Medium | High | Requirements frozen from 02/19/2026; formal use of FOR-009 |
| R-004 | Parallel UAT and Milestone 2 activities (from 02/23) | High | Medium | Clear prioritization with Hugo Pacheco; resolution buffer (Mar 2–6) |

---

## Project Team

| Role | Person | Responsibility |
| --- | --- | --- |
| Sponsor | [[Elena-Torres]] | Project authorization and resources |
| Project Manager | [[Rodney-Ramirez]] | General coordination, follow-up and communication |
| Lead Developer | Sergio Mendoza | Technical design, development of both milestones, observation resolution |
| Business Stakeholder / UAT | Hugo Pacheco | Functional validation and acceptance testing |
| Business Stakeholder | Carlos Ruiz | Business requirements definition |
| Business Stakeholder | Alex Carver | Data model review and business technical decisions |
| Operations | Nicolas Mercado | Operational follow-up and coordination |
| Operations | Elena Torres | Operational follow-up and coordination |
| Implementing Partner (Base Odoo) | Andira Partners (Juan Esteban German, Karina Valdez) | Support on already delivered base accounting modules |

---

## High-Level Timeline

| Milestone | Activity | Responsible | Start | Target Date | Status |
| --- | --- | --- | --- | --- | --- |
| **Milestone 1 — Operational Core** | Development: Configuration, Non-Judicial Mgmt, Judicial Mgmt, Case Mgmt, Activities | Sergio Mendoza | 02/17/2026 | 02/21/2026 | In progress |
| **UAT Milestone 1** | Operational Core acceptance testing | Rodney Ramirez, Hugo Pacheco | 02/23/2026 | 02/27/2026 | To start |
| **Milestone 2 — Integrations and Services** | Development: API integrations, external services, validations | Sergio Mendoza | 02/23/2026 | 02/28/2026 | To start |
| **UAT Milestone 2 + Resolution** | Milestone 2 testing and correction of observations from both UATs | Rodney/Erick (UAT), Sergio (corrections) | 03/02/2026 | 03/06/2026 | To start |
| **Final Delivery** | Production go-live and formal project closure | [[Rodney-Ramirez]] | 03/07/2026 | 03/07/2026 | To start |

**Total duration:** ~3 weeks (February 17 to March 7, 2026)

---

## Resources and Budget

| Field | Information |
| --- | --- |
| **Human Resources** | Sergio Mendoza (development, full-time). Rodney Ramirez (PM, part-time). Hugo Pacheco (UAT, part-time). |
| **Technical Resources** | Odoo 17 Fintrust instance (production + test). Meridian Group GitHub repository. Sergio Mendoza's development environments. |
| **Estimated Budget** | To be defined with Sponsor. Odoo licensing and server costs are covered by the accounting project (Andira Partners). This project's budget mainly corresponds to Sergio Mendoza's development hours. |

---

## Acceptance Criteria

| Field | Information |
| --- | --- |
| **Acceptance Criteria** | (1) All 10 user stories (HU-001 through HU-010) pass UAT without critical observations pending. (2) Navigation of the 4 main menus works correctly in the production environment. (3) Audit trail (chatter) is active on key views. (4) No blocking errors in critical flows: case creation, debtor association, garnishment and legal action registration. (5) Hugo Pacheco and Rodney Ramirez sign the UAT compliance report. |

---

## Communication

| Field | Information |
| --- | --- |
| **Active channels** | Project WhatsApp group (operational); weekly follow-up meetings; log in [[Projects/IE-1-1-3_Odoo-CRM-Fintrust/Logbook]]; minutes in [[Projects/IE-1-1-3_Odoo-CRM-Fintrust/Minutes]]. |
| **Reporting frequency** | Daily follow-up during UAT period; weekly report to Sponsor via FOR-007. |
| **Escalation** | Any critical blocker must be escalated to [[Rodney-Ramirez]] within 24 hours. Scope changes require Sponsor approval via FOR-009. |

---

## Technical Considerations

| Field | Information |
| --- | --- |
| **Platform** | Odoo 17 Community/Enterprise |
| **Architecture** | Respects Odoo's base `res.partner` model for future compatibility with other modules |
| **Repository** | Meridian Group GitHub (data diagrams, entity-relationship, technical documentation) |
| **Audit** | Change logging (Odoo chatter) enabled on key views |
| **Data model** | Generic: one debtor can be associated to N cases without duplicating information; phones with duplicate validation |
| **Future integrations** | DGII (electronic invoice), WhatsApp Business API, NetCollector — out of scope for this phase |

---

## Approvals

| Role | Name | Signature | Date |
| --- | --- | --- | --- |
| Project Sponsor | Elena Torres | ___________________________ | ________________ |
| Project Manager | Rodney Ramirez | ___________________________ | ________________ |
| Lead Developer | Sergio Mendoza | ___________________________ | ________________ |
| Business Stakeholder | Hugo Pacheco | ___________________________ | ________________ |
| Business Stakeholder | Alex Carver | ___________________________ | ________________ |
