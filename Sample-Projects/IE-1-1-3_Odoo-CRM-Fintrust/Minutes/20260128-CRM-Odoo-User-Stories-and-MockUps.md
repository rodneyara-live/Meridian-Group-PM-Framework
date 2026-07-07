---
type: meeting
subtype: mixed
company: meridiangroup
project: "Odoo CRM — Fintrust"
sprint:
date: 2026-01-28
participants: [Rodney-Ramirez, Nicolas-Mercado, Elena Torres, Alex-Carver, Carlos-Ruiz, Sergio-Mendoza, Rodrigo-Villalba]
facilitator: Rodney-Ramirez
tags: [meeting/mixed, company/meridiangroup, project/odoo-crm-fintrust]
---

# 📋 User Stories and MockUps Presentation — CRM Odoo

**Date:** 2026-01-28
**Type:** Mixed (Meridian Group + Ledger-9 + GAF)
**Company:** Meridian Group / Fintrust / Ledger-9
**Duration:** ~25m
**Participants:** [[Rodney-Ramirez]], [[Nicolas-Mercado]], [[Elena-Torres]], [[Alex-Carver]], [[Carlos-Ruiz]], [[Sergio-Mendoza]], [[Rodrigo-Villalba]]
**Facilitator:** [[Rodney-Ramirez]]

[[2026-01-14]] ← | → [[2026-01-29]]

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟣 In Progress (30%)

**Responsible:** [[Rodney-Ramirez]]

**Meeting Context:**
[[Sergio-Mendoza]] presented the CRM Odoo mockups to the expanded team — replicating Odoo's style and UX to validate the proposed structure. The team evaluated the work, identified missing fields at the creditor level, and agreed on next steps to close the review and give "Go" to development.

---

## 🖥️ MockUps Presented — [[Sergio-Mendoza]]

### CRM Module Menu Structure

[[Sergio-Mendoza]] presented mockups replicating Odoo's style with 4 main sections:

| Menu | Description |
|---|---|
| **Non-Judicial Management** | Debtor, phone, address management; collection tracking prior to legal instance |
| **Judicial Management** | Acts, seizures, legal processes, non-seizable debtors (operated from Bonita as orchestrator) |
| **Case Management** | Central entity — file with all actors, activities and statuses |
| **Configuration** | Configurable master tables: phone types, address, email, creditor contact, seizable products |

### Configuration Module

Configurable catalog tables (by administrator):
- **Phone types:** Mobile, Landline, Work, Reference — extensible
- **Address types:** Residential, Work, Alternative, Family — extensible
- **Email types:** Legal, Notification, Billing — extensible
- **Creditor contact types:** configurable by institution type
- **Seizable product types:** configurable

> [[Alex-Carver]] asked how the configuration tables relate to the entities. [[Sergio-Mendoza]] explained: they are master tables that are preconfigured; when registering a phone or address for a debtor, the type is selected from the configured table.

### Debtor Module

- List of debtors with N phones and N addresses (unlimited)
- Debtors can be registered independently of a case, or within a case
- Case assignment is made within the Case entity

### Creditor Module

- List of creditors with their contacts and currencies they handle
- **Related cases** tab for direct visibility from the creditor
- Creditor main contact configuration

### Entities to Seize Module (Ganchi)

- Domain of seizable entities (banks, employers)
- Default currency and additional currencies
- Entity contacts

### Case Supplier Module

- External reference to the case's source system
- Type of system that supplies the cases

### Judicial Management Module

- **Non-seizable debtors:** list of debtors excluded from the seizure process when generating acts
- **Acts / Seizures:** base models created; no business logic yet (pending requirements gathering with Bonita)
- **Legal processes:** base structure; field details will come from Bonita flow requirements gathering

### Case Model (Central Entity)

Contains:
- Case header (main data)
- Related debtors
- Notes
- **Activities** (custom tab): record of who changed what status, when, with what result — case-specific traceability
- **Odoo Chatter** (generic log): changes to model fields, who made them, when — applies to all models that activate it

---

## 💬 Discussion: Chatter and Message Categorization

[[Elena-Torres]] asked whether Odoo's chatter messages can be categorized (like in other CRMs such as Dynamics, where messages are categorized by type: payment, follow-up, etc.) to facilitate traceability and frequency analysis.

**[[Sergio-Mendoza]]'s response:**
- Odoo's generic chatter does not have message categories
- A custom development can be made to add that functionality in a future iteration
- It is not complex — it is a business logic improvement, not structural

**[[Elena-Torres]]'s position:** Could be interesting especially for "stoppers" (follow-up reminders). It is not a blocker for the MVP but it is for future iterations.

---

## 🔐 Security and Access Control

[[Elena-Torres]] asked whether security, role-based access control and log traceability will be handled with Odoo's native structures.

**[[Sergio-Mendoza]]:**
- Role-based access control for screens and buttons is available natively in Odoo
- For custom modules it must be configured — estimated ~1 day of work (8 hours)
- It is not expensive because it reuses Odoo's tools, but it must be done as part of development

**[[Elena-Torres]]:** This must be considered from the start, with good practices and standardized structure. For audit purposes, log traceability is a non-negotiable requirement.

---

## ✅ Evaluation of [[Sergio-Mendoza]]'s Work

The team congratulated the presented work:

- **[[Carlos-Ruiz]]:** "It is very grounded, it has collection topics very well conceptualized. I noticed some missing fields but not many."
- **[[Alex-Carver]]:** "At the structure level of the different tables, it is super good."
- **[[Rodney-Ramirez]]:** "Very clean and well related. These mockups look a lot like what I've seen these days of Odoo."
- **[[Elena-Torres]]:** "We are very happy with your work. You learned fast."

---

## 🚨 Missing Fields Identified

**[[Carlos-Ruiz]]** identified that the Creditors module is missing a **product types tab per creditor**:

- Different creditors handle different product types (card, loan, charged-off loan, etc.)
- Just as there is a contacts tab per creditor, there should be a product types tab for what that creditor handles
- It is not a very complex field but it is mandatory for collection processes

**[[Elena-Torres]]:** We need to identify if there are additional fields that are mandatory for the processes mapped with Bonita — needs review with operational users (Erick).

---

## ✅ Decisions Made

- **Structure approved in principle:** The architecture and table structure proposed by [[Sergio-Mendoza]] is validated. Proceed with detailed field reviews before giving "Go". Decision: [[Elena-Torres]] with [[Alex-Carver]]
- **Product types tab per creditor:** Added to the creditors model. Decision: [[Carlos-Ruiz]] + [[Elena-Torres]]
- **Security and access control:** Included in the development scope from the MVP. Decision: [[Elena-Torres]]
- **Two review meetings for the following day (2026-01-29):
  1. [[Sergio-Mendoza]] + [[Hugo-Pacheco]] (8:00–9:00 AM): detailed operational review of mandatory fields for processes
  2. [[Sergio-Mendoza]] + [[Carlos-Ruiz]] (afternoon): final general review and closing
  3. "Go" decision for development in the afternoon of 2026-01-29. Decision: [[Elena-Torres]] + [[Alex-Carver]]

---

## 📌 Pending Items

- [ ] [[Sergio-Mendoza]] + [[Hugo-Pacheco]]: Detailed operational review — identify mandatory fields for legal processes in Bonita 📅 2026-01-29 AM 🔥
- [ ] [[Sergio-Mendoza]] + [[Carlos-Ruiz]]: Final general review of the complete structure 📅 2026-01-29 PM 🔥
- [ ] [[Rodney-Ramirez]]: Coordinate invitations for the 2 review meetings on 01/29 📅 2026-01-28 🔥
- [ ] [[Carlos-Ruiz]]: Complete field review for collection processes mapped with Bonita 📅 2026-01-29
- [ ] [[Sergio-Mendoza]]: Add product types tab per creditor to the model 📅 pending review

---

## 📌 Next Meetings / Follow-ups

- [ ] Review meeting [[Sergio-Mendoza]] + [[Hugo-Pacheco]]: Mandatory operational fields 📅 2026-01-29 8:00–9:00 AM 🔥
- [ ] Review meeting [[Sergio-Mendoza]] + [[Carlos-Ruiz]]: Final structure review 📅 2026-01-29 afternoon
- [ ] "Go" decision for development 📅 2026-01-29 afternoon 🔥
- [ ] Additional meeting mentioned by [[Rodney-Ramirez]]: around 5:30 PM (same afternoon of 01/28)

---

## 🔗 Triggers — Update after this meeting

- [ ] Odoo module structure approved in principle → [[FOR-003-requirements-matrix]]
- [ ] Product types tab per creditor as mandatory field → [[FOR-003-requirements-matrix]]
- [ ] Security and access control in MVP scope → [[FOR-003-requirements-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
