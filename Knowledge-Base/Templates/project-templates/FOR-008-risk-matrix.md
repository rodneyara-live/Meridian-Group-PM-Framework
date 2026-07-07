# FOR-008 — Risk and Issues Matrix

**Project:** [Project Name]
**Company:** [Meridian Group / Fintrust / Meridian Pay]
**PM:** [Name]
**Creation date:** [YYYY-MM-DD]
**Last update:** [YYYY-MM-DD]

---

## 1. Definitions

| Term | Definition |
|---|---|
| **Risk** | Uncertain event that, if it occurs, can affect the project negatively or positively |
| **Issue** | Problem that has already occurred and requires immediate action |
| **Blocker** | Issue that prevents progress on one or more project tasks |

> For the complete management process, see [[SOP-006 Risk and Issues Management]]

---

## 2. Probability × Impact Matrix

|  | **Low Impact** | **Medium Impact** | **High Impact** |
|---|---|---|---|
| **High Probability** | 🟡 Monitor | 🟠 Mitigate | 🔴 Top Priority |
| **Medium Probability** | 🟢 Accept | 🟡 Monitor | 🟠 Mitigate |
| **Low Probability** | 🟢 Accept | 🟢 Accept | 🟡 Monitor |

---

## 3. Risk Register

| ID | Category | Risk Description | Probability | Impact | Level | Strategy | Response Plan | Responsible | Trigger | Status |
|---|---|---|---|---|---|---|---|---|---|---|
| R-001 | Technical | | High / Medium / Low | High / Medium / Low | 🔴 / 🟠 / 🟡 / 🟢 | Mitigate / Accept / Transfer / Avoid | | | | Active / Closed |
| R-002 | Resources | | High / Medium / Low | High / Medium / Low | 🔴 / 🟠 / 🟡 / 🟢 | Mitigate / Accept / Transfer / Avoid | | | | Active / Closed |
| R-003 | External | | High / Medium / Low | High / Medium / Low | 🔴 / 🟠 / 🟡 / 🟢 | Mitigate / Accept / Transfer / Avoid | | | | Active / Closed |
| R-004 | Business | | High / Medium / Low | High / Medium / Low | 🔴 / 🟠 / 🟡 / 🟢 | Mitigate / Accept / Transfer / Avoid | | | | Active / Closed |

**Risk categories:**
- **Technical** — Technology, architecture, technical debt, integrations
- **Resources** — Team availability, turnover, contractors
- **External** — Vendors, regulations, client, market
- **Business** — Priority changes, budget, management decisions

**Response strategies:**
- **Mitigate** — Reduce probability or impact with preventive actions
- **Accept** — Assume the risk without action (with or without contingency reserve)
- **Transfer** — Transfer the risk to a third party (insurance, contract)
- **Avoid** — Eliminate the cause of the risk by changing the approach

---

## 4. Active Issues Register

| ID | Description | Type | Severity | Opening Date | Impact | Immediate Action | Responsible | Resolution Deadline | Status |
|---|---|---|---|---|---|---|---|---|---|
| I-001 | | Issue / Blocker | 🔴 Critical | | | | | | Open / Resolved |
| I-002 | | Issue / Blocker | 🟠 High | | | | | | Open / Resolved |
| I-003 | | Issue / Blocker | 🟡 Medium | | | | | | Open / Resolved |

**Maximum resolution times by severity:**

| Severity | Maximum time |
|---|---|
| 🔴 Critical — System down / data at risk | 24 hours |
| 🟠 High — Main functionality blocked | 48 hours |
| 🟡 Medium — Partial functionality available | 5 business days |
| 🔵 Low — Minimum impact / workaround exists | Next phase |

---

## 5. Resolved Issues History

| ID | Description | Severity | Opening date | Resolution date | Applied solution |
|---|---|---|---|---|---|
| I-000 | | | | | |

---

## 6. Escalation

If a risk or issue is not resolved within the maximum time, escalate according to:

| Time without resolution | Escalate to |
|---|---|
| > 24h without action (Critical) | General Management immediately |
| > 48h without action (High) | Project Sponsor |
| > 5 days without action (Medium) | PM documents and decides |

---

## 7. Next Review

- **Risk review frequency:** Weekly (in follow-up meeting)
- **Next scheduled review:** [Date]
- **Update responsible:** [Name]

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | | | Initial version |
| 1.1 | | | |
