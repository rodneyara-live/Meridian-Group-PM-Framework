---
type: meeting
subtype: client
company: fintrust
project: "Odoo CRM — Fintrust"
sprint:
date: 2025-12-16
participants: [Sergio-Mendoza, Rodney-Ramirez, Osvaldo-Wexler, Carlos-Ruiz, Elena Torres]
facilitator: Rodney-Ramirez
tags: [meeting/client, company/fintrust, project/odoo-crm-fintrust]
---

# 📋 CRM Gaps Exploration — Odoo Fintrust

**Date:** 2025-12-16
**Type:** Client / Requirements Gathering
**Company:** Fintrust
**Participants:** [[Sergio-Mendoza]], [[Rodney-Ramirez]], [[Osvaldo-Wexler]], [[Carlos-Ruiz]], [[Elena-Torres]]
**Facilitator:** [[Rodney-Ramirez]]

[[2025-12-15]] ← | → [[2025-12-17]]

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟡 At Risk (10%)

**Responsible:** [[Rodney-Ramirez]]

**Progress:**
- [[Sergio-Mendoza]] presented an exploration of Odoo v17's Contacts (Partners) module: generic structure, native limitations and what requires customization for Fintrust
- It was identified that native Odoo only supports 1 phone, 1 email and 1 address per contact — insufficient for Fintrust's collections operation
- MVP scope was delimited: exclusive focus on data needed for the **judicial process** and integration with the Bonita orchestrator; extrajudicial management deferred to a later phase

**Gaps identified (initial gap analysis — Contacts/Debtor module):**
- Multiple phones per contact with validity/invalidity marking without deletion (preserved history)
- Multiple validated judicial addresses and multiple emails
- Estimated debtor income (collections context field, not linked to HR module)
- Personal references catalog (relatives, neighbors, colleagues) linked to the debtor
- Specific "Debtor" model extending Odoo's base Partner
- Debt data and relationships: co-debtors, guarantors, spouses
- Bidirectionality with Bonita: Odoo → Bonita (file/case data) and Bonita → Odoo (status updates: generated seizure, notified, lifting act, balance, etc.)

**Pending:**
- [ ] [[Sergio-Mendoza]]: Attend Bonita functional requirements session to understand Odoo–Bonita interactions 📅 2025-12-17 🔥
- [ ] [[Rodney-Ramirez]]: Create specific tasks in Planner for surgical gap analysis post-Bonita 📅 2025-12-18
- [ ] [[Rodney-Ramirez]]: Complete 2 Bonita functional refinement sessions (Tuesday and Wednesday) as precondition for the full Odoo gap analysis 📅 2025-12-18

---

## 🚨 Active Blockers

*No active blockers*

---

## ✅ Decisions Made

- **Odoo MVP scope:** Prioritize only data and integrations required for the judicial process (Bonita). Extrajudicial management (collections pipeline, contact activities, payment promises) remains out of MVP scope. Decision: [[Rodney-Ramirez]] with backing from [[Elena-Torres]] and [[Carlos-Ruiz]]
- **Precondition for surgical gap analysis:** Do not continue the full Odoo gap analysis until the Bonita flow is finalized. Decision: [[Rodney-Ramirez]]
- **Customization required:** Odoo requires custom development (specific module) to support the Fintrust Debtor/File model — not configurable with standard installation. Technical conclusion: [[Sergio-Mendoza]]

---

## 📌 Next Meetings / Follow-ups

- [ ] [[Sergio-Mendoza]]: Join Bonita functional requirements session (from ~3:15pm) 📅 2025-12-17 🔥
- [ ] [[Rodney-Ramirez]]: Schedule surgical Odoo gap analysis session with [[Sergio-Mendoza]] after completing Bonita sessions 📅 2025-12-19

---

## 🔗 Triggers — Update after this meeting

- [ ] Decision that changes requirements → Update [[FOR-003-requirements-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
