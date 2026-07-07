---
type: document
for: FOR-010
project: "IE-1-1-3"
ultima_actualizacion: 2026-02-19
tags: [document, issues, blockers, project, odoo, crm, fintrust]
---

# FOR-010 — Issue and Blocker Log

**Project:** Case Management Module — Odoo 17 CRM Fintrust
**Company:** Fintrust / Meridian Group
**PM:** Rodney Ramirez
**Last Updated:** 2026-02-19

---

## 1. Issue Summary

| Severity | Active count | Resolved count |
|---|---|---|
| Critical | 0 | 2 |
| High | 0 | 1 |
| Medium | 0 | 2 |
| Low | 0 | 0 |
| **Total** | **0** | **5** |

---

## 2. Active Issues and Blockers

**No active issues as of 02/19/2026.**

---

## 3. Resolved Issues History

| ID | Type | Description | Severity | Reported by | Opening Date | Resolution Date | Days | Applied Solution | Resolved by |
|---|---|---|---|---|---|---|---|---|---|
| I-005 | Blocker | Ledger-9 has no case status query interface. Odoo needed to build that capability, but the technical path was not viable with the original model. | Critical | Sergio Mendoza | 2026-01-09 | 2026-01-30 | 21 | Architecture redefinition: Bonita acts as orchestrator. Case status in Odoo is **READ-ONLY**, updated exclusively by Bonita via API. Judicial management in Odoo is view-only. | Sergio Mendoza / Alex Carver |
| I-001 | Blocker | Odoo environment access credentials (production + test) not delivered to Sergio Mendoza. Without them, formal development could not start. | Critical | Rodney Ramirez | 2026-02-13 | ~2026-02-17 | 4 | Credentials delivered during the week of 02/17. Milestone 1 development resumed. | Rodney Ramirez |
| I-002 | Issue | Bonita and OpenKM API documentation (Rodrigo Villalba) pending delivery to Sergio Mendoza. Needed for Milestone 2 planning. | High | Rodney Ramirez | 2026-02-13 | 2026-02-13 | 0 | Rodrigo Villalba delivered the documentation on the same day 02/13 as committed. | Rodrigo Villalba |
| I-003 | Issue | Architectural decisions pending: data structure by case vs. by individual, state master, portfolio numbering. Without these decisions, the data model could not be closed. | Medium | Sergio Mendoza | 2026-01-30 | 2026-02-04 | 5 | Data model approved by Alex Carver and operationally validated by Hugo Pacheco in session on 02/04. Additional debtor fields: sex, marital status, workplace. Debt block: original + updated. | Alex Carver / Hugo Pacheco |
| I-004 | Issue | Ledger-9 API catalog not validated with Rodrigo Villalba. Impacted the bank integration strategy. | Medium | Sergio Mendoza | 2026-01-12 | 2026-01-13 | 1 | Validated in meeting on 01/13. Decision: banks will deliver standardized **batch** files instead of direct APIs. No bank API integration is developed in this phase. | Rodrigo Villalba / Carlos Ruiz |

---

## 4. Escalated Issues

| ID | Description | Escalated to | Date | Reason | Resolution |
|---|---|---|---|---|---|
| — | No issue escalated in this project | — | — | — | — |

---

## 5. Trend Analysis

**Areas with highest issue concentration:**
1. **Integration architecture** (I-004, I-005) — 2 issues related to external system integration strategy (Ledger-9, Bonita)
2. **Access and resource management** (I-001, I-002) — 2 operational issues for development environment preparation

**Most frequent root cause:**
- [x] Unresolved external dependencies — access, third-party technical documentation
- [x] Ambiguous requirements — architectural decisions requiring additional refinement sessions
- [ ] Technical debt
- [ ] Insufficient resources
- [ ] Other

**Key observation:** The most critical project issues emerged during the analysis/design phase (Dec 2025 – Jan 2026) and were resolved before formal development start. This suggests the discovery process was thorough and reduced risk during the construction phase.

---

## 6. Preventive Actions for Future Phases

| Recurring issue | Preventive action | Responsible | Status |
|---|---|---|---|
| Credentials and access not available at milestone start | Request access 5 business days before each milestone start | Rodney Ramirez | Applied — accesses for Milestone 2 must be confirmed before 02/18 |
| Pending integration technical documentation | Request API documentation at least 1 week before the milestone that requires it | Rodney Ramirez | Applied — Bonita/OpenKM API docs delivered on 02/13 for use in Milestone 2 (start 02/23) |
| Untaken architectural decisions block design | Include decision sessions in the requirements timeline, with defined minimum quorum | Rodney Ramirez | Incorporated — requirements sessions included Alex Carver and Hugo Pacheco |

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2026-02-19 | Rodney Ramirez | Initial version — 5 resolved issues documented, trend analysis included |
