---
type: project
name: "Odoo CRM — Fintrust"
project_name: "Odoo CRM — Fintrust"
internal_code: IE-1-1-3
company: "[[Fintrust]]"
start_date: 2025-12-16
target_date: 2026-03-28
sponsor: "[[Carlos-Ruiz]]"
pm: "[[Rodney-Ramirez]]"
poa_initiatives: ["IE-1-1-3"]
tags: [project]
strategic_pillar: "PE1 — IMPLEMENT FINTRUST"
---

> [!note] Internal code change
> Previous code: `"—"` New code: `PR-1-2-02-1` *(POA system renumbering, 2025-02)*

# Odoo CRM — Fintrust

> 100% custom implementation of the CRM module in Odoo v17 for Fintrust: management of clients, judicial and extrajudicial files, with bidirectional integration to Bonita Soft and OpenKM.

---

## Status and progress

> Operational status, completion and blockers → [[Documents/FOR-015-task-plan|FOR-015]] (source of truth) · Narrative history → [[Logbook]]

---

## Strategic alignment (2026 Matrix)

This project executes the following strategic initiative from the [[Matriz-Estrategica-2026]]:

| Code | Strategic Initiative | Strategic Priority |
|---|---|---|
| PR1.02 | Implement Odoo CRM for Fintrust operations | PE1 — IMPLEMENT FINTRUST |
## Context and objective

**Problem it solves:**
Fintrust operates its judicial and extrajudicial processes on Ledger-9 CRM (Meridian Group system), which was not designed for judicial management. A proprietary CRM in Odoo v17 is required to centralize the master data of debtors, creditors, cases and lawyers, and to serve as the master data source for the Bonita Soft judicial orchestrator.

**Main objective:**
Implement in Odoo v17 a 100% custom CRM module that manages the complete cycle of Fintrust's clients and judicial files, bidirectionally integrated with Bonita Soft (BPMN) and OpenKM (documents), replacing the dependency on Ledger-9 CRM.

**MVP scope:**
- Non-Judicial Management module (master data: Debtors, Creditors, Ganchi, Lawyers)
- Judicial Management module — READ-ONLY (Bonita writes states, Odoo only displays)
- Case Management module (case-centric, bidirectional BonitaOdoo integration)
- Configuration module (catalogs, roles, permissions)
- Bidirectional BonitaOdoo integration (states + timestamps — NON-NEGOTIABLE from MVP)
- OpenKM integration (files and documents linked to case)
- Role-based access control: Administrator (full view) vs. Tracking Operator

**Out of MVP scope:**
- Complete extrajudicial management (later phase)
- Direct API integration with banks (standardized batch is used)
- Debtor bank accounts in the main model

**Fixed architectural decisions:**
- Case-centric model (individuals linked to case with roles: main debtor, co-debtor, guarantor, spouse)
- Case status NEVER manually modified in Odoo — only Bonita updates states
- Mandatory timestamps on every activity and state change (Alex's requirement, Ledger-9's critical gap)
- Additional scope changes go to parking lot and are billed separately
- SIWO classifier for lawyer occupations (international standard)
- Contact history (phones/emails/addresses) NEVER deleted — only deactivated

---

## Team

| Role | Person | Company |
|---|---|---|
| Sponsor | [[Elena-Torres]] | Fintrust / Meridian Group |
| Project Manager | [[Rodney-Ramirez]] | Meridian Group |
| Lead Developer | [[Sergio-Mendoza]] | External (Brazil) |
| Technical Architect / APIs | [[Rodrigo-Villalba]] | External |
| UAT Test Lead | [[Hugo-Pacheco]] | Fintrust (judicial specialist) |
| Director — strategic alignment | [[Alex-Carver]] | Meridian Group |
| Odoo Partner (Andira Partners) | [[Partners/Andira Partners\|Andira Partners]] | External (DO) |
| Data Dictionary | [[Nicolas-Mercado]] | Meridian Group |

---

## Milestones and deliverables

| Milestone | Description | Target date | Status |
|---|---|---|---|
| Discovery & Analysis | Gap analysis, data model, mockups, requirements, plan | 2026-02-13 | Completed |
| **Milestone 1** | Odoo CRM Base Configuration: entities, modules, roles, UAT tests | 2026-02-28 | Completed |
| **Milestone 2** | BonitaOdoo Integration, Judicial Management, OpenKM, comprehensive tests | 2026-03-14 | In progress |
| Closure | Technical documentation, Andira Partners handoff, final report, lessons learned | 2026-03-28 | To start |

> **Total duration:** ~5 weeks from formal start (week of 2026-02-17). Revised end date subject to credential delivery.

---

## Technology stack

| Platform | Role in project |
|---|---|
| Odoo v17 | Target system — custom CRM |
| Bonita Soft (BPMN) | Judicial orchestrator — bidirectional integration |
| OpenKM | Document management — files and annexes |
| Ledger-9 CRM | Source system — reference for catalogs and APIs |
| Figma | Mockup design ([[Sergio-Mendoza]]) |

---

## Active documents

| Document | Type | Description |
|---|---|---|
| [[Documents/FOR-002-project-charter\|FOR-002]] | Project Charter | Project formalization |
| [[Documents/FOR-015-task-plan\|FOR-015]] | Task Plan | Progress source of truth — updated by PM |
| [[Documents/FOR-014-RACI-matrix\|FOR-014]] | RACI Matrix | Team roles and responsibilities |
| [[Documents/FOR-008-risk-matrix\|FOR-008]] | Risk Matrix | Active risks and history |
| [[Documents/FOR-010-issue-log\|FOR-010]] | Issue Log | Registered blockers and issues |
| [[Documents/FOR-004-test-plan-hito1\|FOR-004 Milestone 1]] | Test Plan | Milestone 1 UAT Plan (Hugo Pacheco) |
| [[Documents/FOR-007-weekly-status-report-S1\|FOR-007 S1]] | Weekly Report | First week of execution |

---

## Action item tracking

Action items from each meeting are automatically indexed at:

- [[Actionables]] — open items view for this project (automatic query)
- [[Projects/Dashboard-Actionables-por-Proyecto]] — global view by project
- [[Projects/Dashboard-Actionables-por-Persona]] — global view by responsible person

> For an item to appear here, the minute must be saved in `Minutes/` with the `#PR-1-2-02-1` and `#action` tags on each checkbox.

---

## Follow-up meetings

- Operational Madrugador (Tuesdays and Fridays): technical team follow-up
- Tactical Madrugador (Mondays): portfolio status, blockers and escalations

Transcripts: `Transcripciones/` | Minutes: `Minutes/` | History: [[Logbook]]

---

## Related links

- [[Logbook]] — Narrative project history (last entry = current status)
- [[Actionables]] — Open action items from minutes
- [[Documents/FOR-015-task-plan\|FOR-015]] — Task plan and progress
- [[POA-2026]] — Strategic plan
- [[Projects/Madrugador-Tactico/README]] — Portfolio tracking
- [[Projects/Madrugador-Operativo/README]] — Operational standups
- [[Partners/Andira Partners]] — Implementing Odoo partner
