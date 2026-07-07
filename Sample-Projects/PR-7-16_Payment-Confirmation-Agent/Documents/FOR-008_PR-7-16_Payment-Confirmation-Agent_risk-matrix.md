# FOR-008 — Risk and Issues Matrix

**Project:** Payment Confirmation Agent
**Code:** PR-7-16
**PM:** [[Rodney-Ramirez]]
**Creation date:** 2025-10-17
**Last update:** 2026-02-21

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
| **High Probability** | 🟡 Monitor | 🟠 Mitigate | 🔴 Maximum Priority |
| **Medium Probability** | 🟢 Accept | 🟡 Monitor | 🟠 Mitigate |
| **Low Probability** | 🟢 Accept | 🟢 Accept | 🟡 Monitor |

---

## 3. Risk Register

| ID | Category | Risk Description | Probability | Impact | Level | Strategy | Response Plan | Responsible | Status |
|---|---|---|---|---|---|---|---|---|---|
| R-001 | Resources | **Test data availability:** Delay in delivering validated DPI cases | Low | High | 🟢 Closed | Mitigate | [[Sofia-Vargas\|Sofia]] delivered the data in Oct 2025 as committed. | [[Rodney-Ramirez]] | ✅ Closed — Oct 2025 |
| R-002 | Resources | **External developer availability:** [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] as sole external resource | Low | High | 🟢 Closed | Mitigate | Blue Scarf Solutions delivered v3.0 technical documentation on 2026-02-12. The risk did not materialize. | [[Rodney-Ramirez]] | ✅ Closed — Feb 2026 |
| R-003 | Technical | **Input data quality:** Name variations, amounts or incomplete information affecting matching | Medium | Medium | 🟡 Monitor | Mitigate | Algorithm (v3.0) implements 2 tiers with configurable tolerances. Feb 3 demo showed scores 91.67%–100%. Monitored in daily operation. | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] | Active — in monitoring |
| R-004 | Technical | **Algorithm scalability:** Performance degradation with larger volumes | Low | High | 🟢 Closed | Mitigate | Incremental testing completed. Demo with 26 Ledger-9 / 55 DPI operational without issues. System runs 2×/day without problems. | [[Partners/Contacts/Jose-Ricardo-Cuadra\|Jose Ricardo Cuadra]] | ✅ Closed — Feb 2026 |
| R-005 | Technical | **OAuth2 credential expiration (Microsoft Outlook):** Outlook OAuth2 token may expire and block email notifications | Medium | Medium | 🟡 Monitor | Mitigate | [[Isabella Torres]] configured the token. Per v3.0 technical guide, if the token expires, credentials must be renewed in n8n (Credentials → Meridian Group Outlook OAuth2). Monitor with error alerts. | [[Isabella Torres]] | Active — pending production monitoring |

---

## 4. Active Issues Register

| ID | Description | Type | Severity | Opening Date | Impact | Immediate Action | Responsible | Deadline | Status |
|---|---|---|---|---|---|---|---|---|---|
| — | No active issues as of 2026-02-21 | — | — | — | — | — | — | — | — |

---

## 5. Resolved Issues History

| ID | Description | Severity | Opening Date | Resolution Date | Applied Solution |
|---|---|---|---|---|---|
| I-001 | Filter blocked executions when there were no pending payments | 🟡 Medium | 2026-02-03 | 2026-02-14 | Replaced with decision node as per Feb 3 meeting decision |

---

## 6. Escalation

| Time without resolution | Escalate to |
|---|---|
| > 24h without action (Critical) | [[Tomas-Navarro]] — Management |
| > 48h without action (High) | [[Tomas-Navarro]] — Sponsor |
| > 5 days without action (Medium) | [[Rodney-Ramirez]] — PM documents and decides |

---

## 7. Next Review

- **Risk review frequency:** Upon going to production and first operational month
- **Next scheduled review:** At go-live time
- **Update responsible:** [[Rodney-Ramirez]]

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2025-10-17 | [[Rodney-Ramirez]] | Initial version with 4 risks identified in Charter |
| 2.0 | 2026-02-21 | [[Rodney-Ramirez]] | Update to real status: R-001, R-002 and R-004 successfully closed. R-003 in active monitoring. New R-005 (Outlook OAuth2). Issue I-001 resolved (filter → decision node). |
