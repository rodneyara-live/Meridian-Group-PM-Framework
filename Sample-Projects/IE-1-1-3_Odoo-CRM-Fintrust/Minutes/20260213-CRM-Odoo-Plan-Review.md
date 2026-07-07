---
type: meeting
subtype: internal
company: meridiangroup
project: "Odoo CRM — Fintrust"
sprint:
date: 2026-02-13
participants: [Rodney-Ramirez, Sergio-Mendoza]
facilitator: Rodney-Ramirez
tags: [meeting/internal, company/meridiangroup, project/odoo-crm-fintrust]
---

# 📋 Implementation Plan Review CRM Odoo

**Date:** 2026-02-13
**Type:** Internal (Meridian Group + GAF)
**Company:** Meridian Group / GAF
**Duration:** ~20m
**Participants:** [[Rodney-Ramirez]], [[Sergio-Mendoza]] (connected from Brazil)
**Facilitator:** [[Rodney-Ramirez]]

[[2026-02-04]] ← | → [[2026-02-16]]

---

## 🎯 Projects / Topics

### [[PR-1.02_Odoo-CRM-Fintrust]] — 🟣 In Progress (50%)

**Responsible:** [[Rodney-Ramirez]]

**Meeting Context:**
Technical alignment session between PM and lead developer to review the implementation plan. [[Sergio-Mendoza]] is connected from Brazil (where he is with his family). The 2-milestone structure, approximate 5-week schedule, and testing strategy are defined.

---

## 🏗️ Milestone Structure — Implementation Plan

### Milestone 1: Odoo CRM Base Configuration

**Scope:**
- All data models configured
- CRM views (mockups implemented)
- Configurable catalogs (status types, etc.)
- Complete configuration menu
- Roles and sequences configured
- End-to-end functional system without external integrations

**Estimate:** ~2 weeks of development

### Milestone 2: Service Integration with Bonita

**Scope:**
- API service development to connect Odoo CRM ↔ Bonita
- Integration with OpenKM (document manager)
- Based on the architecture that [[Rodrigo-Villalba]] already has set up for Ledger-9
- Odoo CRM replaces Ledger-9 in the Bonita ecosystem

**Estimate:** ~2 weeks of development (with overlap during Milestone 1 testing)
**Critical dependency:** [[Rodrigo-Villalba]]'s API documentation (delivering today, 2026-02-13)

---

## 📅 Approximate Timeline

```
Week 1-2:  Milestone 1 Development (Odoo CRM Configuration)
Week 3:    Milestone 1 Testing and Certification
           → Parallel start of Milestone 2
Week 4-5:  Milestone 2 Development (Bonita Integration)
           Milestone 2 Testing
           Production deployment
```

**Total estimated:** ~5 weeks from formal start (next week, once access credentials are delivered)

> **Note:** [[Sergio-Mendoza]] is already working ahead; he expects to have the essentials of Milestone 1 functional by the end of this week.

---

## 🧪 Functional Testing Strategy

### Central Principle

[[Rodney-Ramirez]] established the principle: the developer should NOT be the only one designing tests for their own system.

> "It is like Volkswagen doing its own emissions tests."

### Testing Responsibilities

**Test lead:** [[Hugo-Pacheco]] (operational expert in judicial processes)
- Prepares use cases and test scenarios from the business perspective
- Designs the certification matrix with real scenarios
- Proposes edge cases based on operational experience
- Tests focus on **judicial processes** (not extrajudicial call/agreement management)

**Support participant:** [[Carlos-Ruiz]]

**Technical support:** [[Sergio-Mendoza]] (available for clarifications and corrections during testing)

### Scope Discipline

- Test cases must be within the documented requirements scope
- Avoid the pattern observed with Bonita: "Every day something new to add occurs to someone"
- Additional changes go to the **parking lot** and are billed separately (estimated: 4-5 hours per small adjustment)

---

## 🔗 Critical Dependencies

| Dependency | Responsible | Date |
|---|---|---|
| API documentation (Ledger-9 + OpenKM) | [[Rodrigo-Villalba]] | 2026-02-13 (today) |
| Environment access credentials | [[Rodney-Ramirez]] | Next week |
| Detailed roadmap with dates | [[Sergio-Mendoza]] | 2026-02-14 (tomorrow) |
| Alignment with [[Alex-Carver]] | [[Rodney-Ramirez]] | This week |
| Erick ready to start Milestone 1 testing | [[Rodney-Ramirez]] notifies [[Hugo-Pacheco]] | Week 3 |

### About Rodrigo Villalba

- Finishes API documentation today (interactions with Ledger-9 and OpenKM)
- [[Sergio-Mendoza]] and [[Rodrigo-Villalba]] know each other from previous work
- They can communicate directly for technical questions about Milestone 2
- [[Rodrigo-Villalba]] has extended availability this week (negotiated by Meridian Group)

---

## 📦 Scope Context

[[Rodney-Ramirez]] mentioned that the initial scope was expanded significantly at the client's initiative ([[Elena-Torres]]) upon seeing the original price. The expansion was contained and the final negotiated package includes requirements that were originally out of scope. The scope is now **closed** and documented.

---

## ✅ Decisions Made

- **2-milestone structure:** Milestone 1 (Odoo Configuration) → Milestone 2 (Bonita Integration). Decision: [[Rodney-Ramirez]] + [[Sergio-Mendoza]]
- **~5 week timeline:** Formal start next week; total delivery in max 1 month. Decision: [[Sergio-Mendoza]] with [[Rodney-Ramirez]]
- **Testing led by [[Hugo-Pacheco]]:** Not by the developer. Focus on real business use cases (judicial processes). Decision: [[Rodney-Ramirez]]
- **Incremental certification:** Certify Milestone 1 as soon as functional, without waiting for Milestone 2. Decision: [[Rodney-Ramirez]] + [[Sergio-Mendoza]]
- **Future changes in parking lot:** Any new post-approval requirement goes to the parking lot and is billed separately. Decision: [[Rodney-Ramirez]]
- **Direct communication Sergio ↔ Francisco:** For Bonita integration technical questions. Decision: [[Rodney-Ramirez]]

---

## 📌 Pending Items

- [x] [[Sergio-Mendoza]]: Prepare detailed roadmap/timeline with stages for both milestones 📅 2026-02-14 🔥 ✅ 2026-02-22
- [ ] [[Sergio-Mendoza]]: Include in roadmap: code delivery dates + dates available for functional testing 📅 2026-02-14 🔥
- [ ] [[Rodney-Ramirez]]: Deliver environment access credentials to [[Sergio-Mendoza]] 📅 Week of 2026-02-17 🔥
- [ ] [[Rodney-Ramirez]]: Align [[Alex-Carver]] with the plan 📅 This week
- [x] [[Rodney-Ramirez]]: Notify [[Hugo-Pacheco]] about his role as test lead and ask him to start thinking about use cases 📅 This week ✅ 2026-02-22
- [x] [[Rodrigo-Villalba]]: Finish and share API documentation (Ledger-9 + OpenKM) with [[Sergio-Mendoza]] 📅 2026-02-13 (today) 🔥 ✅ 2026-02-22
- [x] [[Sergio-Mendoza]]: Review [[Rodrigo-Villalba]]'s API documentation for Milestone 2 📅 2026-02-14 ✅ 2026-02-22

---

## 📌 Next Meetings / Follow-ups

- [ ] [[Sergio-Mendoza]]'s roadmap review with [[Alex-Carver]] 📅 ~2026-02-16 (next week)
- [ ] Formal development start — Milestone 1 📅 Week of 2026-02-17
- [ ] Functional testing Milestone 1 with [[Hugo-Pacheco]] 📅 ~Week of 2026-03-02

---

## 🔗 Triggers — Update after this meeting

- [ ] 2-milestone plan confirmed (Milestone 1 Configuration + Milestone 2 Bonita Integration) → [[FOR-007-weekly-status-report]]
- [ ] ~5 week timeline from formal start → [[FOR-007-weekly-status-report]]
- [ ] Testing strategy: Hugo Pacheco as certification lead → [[FOR-003-requirements-matrix]]
- [ ] Weekly report → [[FOR-007-weekly-status-report]]
