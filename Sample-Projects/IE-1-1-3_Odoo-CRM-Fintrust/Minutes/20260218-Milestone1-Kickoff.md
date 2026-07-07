---
type: minuta
tipo-reunion: kickoff
date: 2026-02-18
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Sergio Mendoza]
tags: [meeting, kickoff, milestone1, development, odoo]
---

# IE-1-1-3 · 2026-02-18 · Milestone 1 Kickoff — Development Start

## Context

🎉 **Development officially begins today.** After 2 months of analysis, gap analysis, data model design, mockups and requirement closures, we have the green light to start coding.

### The Credential Issue

- On 02/13, credentials STILL had not been delivered.
- Rodney escalated to Elena Torres on 02/17. Credentials were finally delivered on 02/17.
- **Impact:** Development start slips from 02/10 (planned) to 02/18 (actual). 8 days delay.
- Mitigation: Sergio committed to compressing delivery by 4 days. The adjusted delivery date is **03/03** instead of 02/28.

### Technical Environment

| Environment | Status | URL |
|---|---|---|
| Odoo v17 Test | ✅ Access granted | (internal) |
| Odoo v17 Production | ✅ Access granted | (internal) |
| GitHub Repo | ✅ Active | Meridian Group private repo |
| PostgreSQL (Odoo native) | ✅ Active | Bundled |

## Development Plan — Milestone 1

### User Stories (in order of implementation)

| # | User Story | Estimated days | Owner |
|---|---|---|---|
| HU-001 | Debtor Management (CRUD + contact history) | 2 | Sergio Mendoza |
| HU-002 | Creditor Management (CRUD + contracts) | 1 | Sergio Mendoza |
| HU-003 | Debt Product Management (CRUD) | 1 | Sergio Mendoza |
| HU-004 | Legal Case Management (CRUD + state machine) | 3 | Sergio Mendoza |
| HU-005 | Debtor-to-Case Association (Ganchi roles) | 1 | Sergio Mendoza |
| HU-006 | Debt-to-Case Association | 1 | Sergio Mendoza |
| HU-007 | Garnishment Management | 1 | Sergio Mendoza |
| HU-008 | Activity Management | 1 | Sergio Mendoza |
| HU-009 | Notes Management | 1 | Sergio Mendoza |
| HU-010 | Legal Actions Management | 1 | Sergio Mendoza |
| — | Configuration Module (catalogs, roles, permissions, sequences) | 2 | Sergio Mendoza |
| — | UAT tests with Hugo Pacheco + corrections | 3 | Hugo Pacheco / Sergio Mendoza |
| **Total** | | **18 days** | — |

### Development Rules

1. **Empty states first:** Sergio starts by creating Odoo empty modules with models, views and menus. Then fills with logic.
2. **No frontend (JS) customization for MVP.** All views are native Odoo 17 XML.
3. **Daily commits to GitHub.** Branch: `develop`. No direct push to `main`.
4. **No security yet** (groups and rules) in the first iteration. Added at the end.
5. **Demo at the end of each User Story** to Rodney for review.

## Communication

- Daily sync at 9:00 AM (15 min max) for blocker identification.
- Weekly formal status on Fridays via FOR-007.
- Slack channel `#fintrust-odoo` for quick questions.

## Action Items

| # | Action | Responsible | Due Date |
|---|---|---|---|
| AC-44 | Create Odoo module structure (empty) and push to GitHub | Sergio Mendoza | 2026-02-18 |
| AC-45 | Implement HU-001 (Debtor CRUD) | Sergio Mendoza | 2026-02-20 |
| AC-46 | Implement HU-002 (Creditor CRUD) | Sergio Mendoza | 2026-02-21 |
| AC-47 | Implement HU-003 (Debt Product CRUD) | Sergio Mendoza | 2026-02-22 |
| AC-48 | Begin weekly status reports (FOR-007) | Rodney Ramirez | 2026-02-21 |
