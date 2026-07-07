---
type: minuta
tipo-reunion: tecnica
date: 2026-01-10
project: "IE-1-1-3"
cliente: Fintrust (Meridian Group)
attendees: [Rodney Ramirez, Sergio Mendoza]
tags: [meeting, technical, frontend, views, odoo, mockups]
---

# IE-1-1-3 · 2026-01-10 · Technical: Frontend Strategy, Views and Mockups

## Objective

Define the criteria for Odoo module views and mockups before starting production.

## Design Principles

Sergio and Rodney defined:

### 1. Views — Core Criteria

- **All CRUD in tree view (list).** In Odoo 17, list view is the most efficient for bulk operations.
- **Search panel ALWAYS visible.** Must allow filtering by: state, creditor, assigned lawyer, date range, debtor name.
- **Form view: minimalist.** Only the fields that the operator uses daily. Additional fields in a "More" tab or in a section below.
- **Kanban view for cases.** Especially useful for state-based management in the non-judicial module. Optionally also in the judicial module.
- **Pivot / Graph view.** Not required for MVP. Evaluated for version 2.0.

### 2. Debtor View

| Element | View type | Fields |
|---|---|---|
| List | Tree | Code, Name, ID Number, Status, Employer, Last Contact Date |
| Form | Form | Basic info + tabs: Debts, Cases, Contact History, Bank Accounts, Notes |
| Search | Panel | Status, Debtor Type, Employer, ID Number |

### 3. Case View — The Most Complex

**Form View Structure:**

- **Header:** Case Code, State (color), Creditor, Debtor(s)
- **Tab 1: Case Info** — Type, Receipt Date, Lawyer, Total Debt, Current Balance
- **Tab 2: Debtors** — List of roles (Ganchi: main debtor, co-debtor, guarantor) with names and role type
- **Tab 3: Debts** — Product, Original Amount, Updated Amount, Status
- **Tab 4: Activities** — All actions: calls, visits, notifications. Chronological. Filterable by type.
- **Tab 5: Agreements** — Payment agreements: type, amount, status, monitoring
- **Tab 6: Notes** — Internal, client communication, legal notes. Author + date + type.
- **Tab 7: Judicial** (read-only) — Bonita State, Court Case Number, Garnishments, Judgment. Visible only if judicial.
- **Footer:** Created by, Last modification, Audit trail

### 4. Mockups in Figma

- Sergio will produce mockups BEFORE writing any code. This is a non-negotiable practice for Meridian Group.
- The mockups are in Figma (project "Meridian Group — Fintrust").
- **Milestone 1 mockups:** Non-judicial module (Debtors, Creditors, Lawyers, Ganchi, Configuration).
- **Milestone 2 mockups:** Judicial module, integration screens.

### 5. UX Conventions

| Convention | Applied to | Reason |
|---|---|---|
| Color by state | State field in cases | Yellow = In progress, Green = Completed, Red = Blocked, Gray = Inactive |
| Smart buttons in form | Related records (debts, activities, agreements) | Quick navigation without menu |
| Auto-complete in many2one | Creditor, Lawyer, Debtor | Reduce typing errors |
| Confirmation before deletions | All models | Prevent accidental deletions |
| Required field marker | All fields mandatory for state transition | Ensure records always have minimum data before moving state |

## Additional Decisions

- **Mobile:** Odoo 17 already has a responsive interface. A responsive test is done and no adjustments are needed for now.
- **User training:** Hugo Pacheco will receive a 2-hour personalized session before the UAT phase.
- **Figma link:** Will be shared in the [[Actionables]] notes when available.
