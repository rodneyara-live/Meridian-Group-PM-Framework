---
type: document
for: FOR-008
project: "IE-1-1-3"
date_creacion: 2026-02-19
ultima_actualizacion: 2026-02-19
tags: [document, risks, issues, project, odoo, crm, fintrust]
---

# FOR-008 — Risk and Issue Matrix

**Project:** Case Management Module — Odoo 17 CRM Fintrust
**Company:** Fintrust / Meridian Group
**PM:** Rodney Ramirez
**Creation Date:** 2026-02-19
**Last Updated:** 2026-02-19

---

## 1. Definitions

| Term | Definition |
|---|---|
| **Risk** | Uncertain event that, if it occurs, may negatively affect the project |
| **Issue** | Problem that has already occurred and requires immediate action |
| **Blocker** | Issue that prevents progress on one or more project tasks |

---

## 2. Probability × Impact Matrix

| | **Low Impact** | **Medium Impact** | **High Impact** |
|---|---|---|---|
| **High Probability** | Monitor | Mitigate | Maximum Priority |
| **Medium Probability** | Accept | Monitor | Mitigate |
| **Low Probability** | Accept | Accept | Monitor |

---

## 3. Risk Register

| ID | Category | Risk Description | Probability | Impact | Level | Strategy | Response Plan | Responsible | Trigger | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| R-001 | Time | Tight timeline — complete dev + UAT + corrections cycle covers barely ~3 weeks (21 Feb – 7 Mar) with two parallel milestones from 02/23 | High | High | Maximum Priority | Mitigate | Parallelize Milestone 1 UAT with start of Milestone 2 development. Prioritize critical corrections. Daily follow-up between PM and developer. | Rodney Ramirez | Sergio delivers Milestone 1 late or Erick reports blocking observations in UAT | Active |
| R-002 | Resources | Dependency on a single developer — Sergio Mendoza is the only technical resource. Any unavailability (illness, connectivity, overload) directly impacts the timeline | Medium | High | Mitigate | Mitigate | Continuous technical documentation on GitHub. Proactive communication of any blocker. Resolution buffer (Mar 2–6) acts as cushion. | Sergio Mendoza | Sergio reports blocker >8 hours without resolution | Active |
| R-003 | Technical | Bidirectional BonitaOdoo integration complexity — case status in Odoo is managed EXCLUSIVELY by Bonita (READ-ONLY in Odoo). Any integration failure affects the complete judicial flow | Medium | High | Mitigate | Mitigate | Validate integration architecture with Rodrigo Villalba before coding Milestone 2. Use API documentation delivered on 02/13. Integration tests as part of UAT Milestone 2. | Sergio Mendoza / Rodrigo Villalba | Bonita API call failure in test environment | Active |
| R-004 | Time | Parallelism of Milestone 1 UAT + Milestone 2 development from 02/23 — if UAT generates many observations, Sergio must handle corrections and development simultaneously | High | Medium | Mitigate | Mitigate | Prioritize critical UAT corrections over Milestone 2 progress. The Mar 2–6 buffer is designed to absorb observations from both UATs. Hugo Pacheco prioritizes highest-risk scenarios first. | Rodney Ramirez / Hugo Pacheco | Milestone 1 UAT generates >5 critical observations in first session | Active |
| R-005 | Business | Post-freeze scope changes — stakeholders may request changes to the data model or functionalities after formal requirements closure (02/04/2026) | Medium | Medium | Monitor | Mitigate | Scope formally frozen as of 02/19/2026. All changes must be processed via FOR-009 Change Request and evaluated as additional work outside current contract. | Rodney Ramirez | Any new functionality request after 02/19 | Active |
| R-006 | Technical | OpenKM integration — the document platform (OpenKM) requires integration from Milestone 2. Technical documentation was delivered, but the integration has not been tested yet | Medium | Medium | Monitor | Mitigate | Validate basic connectivity with OpenKM in the first week of Milestone 2. Escalate to Rodrigo Villalba if technical blockers exist. | Sergio Mendoza | Authentication or access failure to OpenKM repositories in test environment | Active |
| R-007 | External | Access to Bonita for testing — the Bonita environment is externally managed. If not available for Milestone 2 testing, the integration UAT cannot be executed | Low | High | Monitor | Mitigate | Coordinate with Rodrigo Villalba Bonita environment availability for the weeks of 02/23 to 03/06. Verify access before 02/23. | Rodney Ramirez / Rodrigo Villalba | Bonita response failure in test environment during UAT Milestone 2 | Active |

---

## 4. Active Issues Register

| ID | Description | Type | Severity | Opening Date | Impact | Immediate Action | Responsible | Deadline | Status |
|---|---|---|---|---|---|---|---|---|---|
| — | No active issues as of 02/19/2026 | — | — | — | — | — | — | — | — |

> Previous issues already resolved — see section 5.

---

## 5. Resolved Issues History

| ID | Description | Severity | Opening Date | Resolution Date | Applied Solution |
|---|---|---|---|---|---|
| I-001 | Odoo environment access credentials not delivered to Sergio Mendoza | Critical | 2026-02-13 | ~2026-02-17 | Credentials delivered in the week of 02/17. Development could formally start. |
| I-002 | Bonita and OpenKM API documentation (Rodrigo Villalba) pending delivery to developer | High | 2026-02-13 | 2026-02-13 | Francisco delivered the documentation on the same 02/13 as committed. |
| I-003 | Architectural decisions pending on structure by case vs. individual, states and portfolio numbering (Luis/Elena Torres) | Medium | 2026-01-30 | 2026-02-04 | Data model approved by Alex Carver and Hugo Pacheco in requirements closure session on 02/04. |
| I-004 | Ledger-9 API catalog not validated with Rodrigo Villalba | Medium | 2026-01-12 | 2026-01-13 | Validated in meeting on 01/13. Ledger-9 uses batch files instead of direct API for banks. |
| I-005 | Ledger-9 has no case status query interface — Odoo must build this capability from scratch | Critical | 2026-01-09 | 2026-01-30 | Architecture redefined: Bonita is the orchestrator. Case status in Odoo is READ-ONLY, updated exclusively by Bonita via API. |

---

## 6. Escalation

| Time without resolution | Escalate to |
|---|---|
| > 24h without action (Critical) | Elena Torres — General Management |
| > 48h without action (High) | Rodney Ramirez — Project Sponsor |
| > 5 days without action (Medium) | PM documents and decides |

---

## 7. Next Review

- **Review frequency:** Weekly (every Thursday, together with Status Report)
- **Next scheduled review:** 2026-02-26
- **Update responsible:** Rodney Ramirez

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2026-02-19 | Rodney Ramirez | Initial version — 7 risks registered, 5 resolved issues documented |
