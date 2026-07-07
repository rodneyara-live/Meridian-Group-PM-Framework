---
type: meeting
subtype: external
company: meridian-pay
project: "Odoo CRM — Fintrust"
date: 2026-02-17
participants: [Rodney-Ramirez, Sergio-Mendoza, Isabella Torres, Tomas-Navarro]
facilitator: Rodney-Ramirez
tags: [meeting/external, company/meridian-pay, project/odoo-crm-fintrust]
---

# 📋 Presentation of Laura Winslow Flows — CRM Odoo Implementation

**Date:** 2026-02-17
**Type:** External (Meridian Group + Meridian Pay)
**Duration:** ~30m
**Participants:** [[Rodney-Ramirez]], [[Sergio-Mendoza]], [[Isabella Torres]], [[Tomas-Navarro]]
**Facilitator:** [[Rodney-Ramirez]]

> Discovery session: [[Isabella Torres]] presents the current management flow of Laura Winslow (Meridian Pay collection agent) on Ledger-9 CRM, so that [[Sergio-Mendoza]] understands what to replicate and adapt in the new Meridian Pay Odoo instance.

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — Discovery: Current Ledger-9 flow → base for Meridian Pay Odoo CRM

**Responsible:** [[Rodney-Ramirez]]

---

## 🔄 Current Management Flow (Ledger-9 CRM → Laura Winslow)

### General Flow

[[Isabella Torres]] explained the complete extrajudicial collection management flow that [[Laura-Winslow]] executes on Ledger-9:

1. **Debtor information query:** Obtained from the Ledger-9 database (name, ID, debts, phones, etc.)
2. **Contact:** Natalia makes the call or management to the debtor
3. **Result registration:** Post-management, Isabella Torres records in Ledger-9:
   - **Comment/Summary:** narrative text of what happened in the interaction
   - **Activity / Disposition:** specific result code (e.g.: "Payment promise — 10,000 pesos for 02/17")

### Two Debtor Query Mechanisms

| Channel | Method | When used |
|---|---|---|
| **Outbound** (Natalia calls) | Direct query to Ledger-9 DB | Isabella Torres already knows who to call (query with business parameters) |
| **Inbound** (client calls) | API with ID as input | Client calls, provides their ID, and information is queried in real time |

### Portfolio Selection for Management (Outbound)

Debtor selection is defined **by business parameters** (Bruno or Meridian Pay team tells Isabella Torres which segment to work):
- Example: "Only debtors with +3 overdue installments"
- Example: "Do not call those with an active payment promise"
- Isabella Torres translates those criteria into dynamic queries executed every hour (hourly trigger with business hours and holiday verification)
- The result brings multiple cases per debtor → consolidated into **one call** (without overloading the client with duplicate calls for each file)

### Post-Management Registration

Post-call, Isabella Torres does a direct **INSERT** into Ledger-9 tables:
- Comments table (narrative summary)
- Activities table (disposition: what action and what result)

---

## 🏗️ Architectural Decisions — Meridian Pay as Independent Instance

[[Sergio-Mendoza]] asked whether Meridian Pay will remain connected to Ledger-9 or have its own data. [[Rodney-Ramirez]] clarified the target architecture:

> "The idea is to give Meridian Pay **operational independence**. Today Meridian Pay depends on Ledger-9. With Odoo, it will have its own instance."

**Confirmed data model:**
- Clients are **born in Ledger-9** (Meridian Group): first collection management
- When restructuring/refinancing is offered → they **move to Meridian Pay** (new record in Odoo Meridian Pay)
- From that point on, **Meridian Pay interactions are no longer recorded in Ledger-9**
- There will be an overlap period (client in both systems), but the operational flow is separated

**Confirmation from [[Sergio-Mendoza]]:** "I understand now — they will be synchronized for a while, but then Meridian Pay depends solely on its own CRM."

---

## 📌 Relevance to the Odoo CRM

[[Sergio-Mendoza]] confirmed that **Laura Winslow's functionality is essentially the same that Fintrust needs**: notes, activities, dispositions and a debt summary. The three key modules any user needs are:
- **Debtor and case view** (with amounts)
- **Activity recording** (what action was taken)
- **Notes/Comments** (narrative summary of the interaction)

This session validates that the data model already planned in Milestone 1 covers the real operational flow of both companies.

---

## 📋 Actionables from This Meeting

- [x] [[Sergio-Mendoza]]: Consider in the Odoo model the case consolidation mechanism by debtor (single management for multiple files) #PR-1-2-02-1 #resp/Sergio-Mendoza #action 📅 2026-02-24 ✅ 2026-03-20
- [x] [[Rodney-Ramirez]]: Confirm with [[Isabella Torres]] the exact fields of the post-management INSERT (activity and comment fields in Ledger-9) to align the Odoo model #PR-1-2-02-1 #resp/Rodney-Ramirez #action 📅 2026-02-24 ✅ 2026-03-20

---

## 🔗 Triggers — Update after this meeting

- [ ] Data model validation (activities + notes + dispositions) → [[Documents/FOR-015-task-plan]]
- [ ] Meridian Pay architecture as independent instance → [[Documents/FOR-002-project-charter]]
- [ ] Portfolio selection flow (hourly query + business parameters) → context for Milestone 1 configuration module
