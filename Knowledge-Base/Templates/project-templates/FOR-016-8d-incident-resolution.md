---
type: template
code: FOR-016
tags: [template, for, 8d, incidents, quality, root-cause]
updated: 2026-07-02
---

# FOR-016 — Incident Resolution (8D Methodology)

> Adaptation of Ford's 8D methodology for structured problem resolution in customer service, financial operations, and operational management environments. Applies to technological incidents (Wolkvox, Ledger-9, Odoo, networks), operational incidents (service outage, campaign blocking), and process incidents (information leak, mass error, SLA breach).

**Incident:** [Descriptive incident name]
**Internal code:** 8D-[YEAR]-[NNN]
**Company:** [[Meridian Group]] / [[Fintrust]] / [[Meridian-Pay]]
**Related project:** [[IE-2-2-1-1_Operational-Incident-Management]]
**Severity:** Critical / High / Medium / Low
**Opening date:** [YYYY-MM-DD]
**Closure date:** [YYYY-MM-DD]
**8D Facilitator:** [[First-Last]]
**Sponsor:** [[First-Last]]

---

## D0 — Plan and Prepare the 8D

*Decision to activate the 8D process. Not every incident deserves a full 8D — only those with significant impact on operations, clients, or compliance.*

**8D activation criteria (check those that apply):**

- [ ] Production-impacting incident (platform outage, Wolkvox down, Ledger-9 inaccessible)
- [ ] Recurrence of the same type of incident (3+ occurrences in 30 days)
- [ ] Impact on external clients (unmanaged accounts, unprocessed payments)
- [ ] Impact on operational SLAs (management time, contact rate, payment promise)
- [ ] Incident with data loss or security breach
- [ ] Incident that required management escalation
- [ ] Process deviation that affected operational results

**Opening justification:**

[Explain why this incident warrants a full 8D instead of a simple resolution]

**Required resources:**
- Estimated team time: [N] hours
- Necessary tools: [logs, Wolkvox reports, recordings, Ledger-9 extracts, etc.]
- Special access: [databases, servers, configurations]

---

## D1 — Form the Team

*Cross-functional team with knowledge of the process, technology, and business.*

| 8D Role | Name | Role at Meridian Group | Area |
|---|---|---|---|
| Sponsor / Champion | | Director / Manager | Management / Operations |
| 8D Facilitator | | Project Manager / Quality | PMO / Quality |
| Technical member | | IT Support / Infrastructure | IT |
| Operations member | | Coordinator / Supervisor | Operations / Call Center |
| Quality member | | Quality Analyst | Quality / Continuous Improvement |
| Business member | | Collections Analyst / Agent | Collections / Portfolio |
| Recorder | | Administrative Assistant | Administration |

**Availability statement:**

- [ ] The full team confirms availability for 8D sessions
- [ ] [N] weekly hours were assigned for team work
- [ ] Sponsor informed and available for escalations

---

## D2 — Describe the Problem

"A well-defined problem is a half-solved problem." — Use data, not opinions.

### 2.1 Problem Definition (IS/IS NOT format)

| Dimension | IS (affects) | IS NOT (does not affect) | Difference / Source |
|---|---|---|---|
| **What?** | | | |
| **Where?** (campaign, queue, server, branch) | | | |
| **When?** (date, time, shift) | | | |
| **Who?** (agents, clients, supervisors) | | | |
| **Magnitude?** (# accounts, # calls, $ amounts) | | | |
| **Trend?** (growing, stable, intermittent) | | | |

### 2.2 Impact on Operations and Business

| Dimension | Detail | Metric | Value |
|---|---|---|---|
| Service hours affected | | Lost HH | |
| Unmanaged accounts | | # accounts | |
| Estimated unrecovered amount | | $ RD | |
| Affected clients | | # clients | |
| Breached SLAs | | SLA | |
| Rework required | | Rework HH | |
| Image / reputation | | Complaints / escalations | |

### 2.3 Available Evidence

- [ ] Screenshots / system logs
- [ ] Wolkvox reports from the affected period
- [ ] Relevant call recordings
- [ ] Ledger-9 / Odoo extract from the period
- [ ] Team communications (WhatsApp, emails)
- [ ] History of similar incidents
- [ ] Documentation of recent changes (deployments, configurations)

### 2.4 Incident Narrative

[Incident timeline: what happened, when, who detected it, how it was initially responded to, who took each action]

---

## D3 — Containment Actions (ICA — Interim Containment Actions)

*Stop the bleeding while investigating the root cause. Temporary actions, not permanent.*

| # | Containment Action | Responsible | Start | End | Verified Effectiveness |
|---|---|---|---|---|---|
| 1 | [e.g., Manual call rerouting to backup call center] | | [YYYY-MM-DD HH:MM] | [YYYY-MM-DD HH:MM] | [ ] Yes / [ ] No |
| 2 | [e.g., Database restoration from backup] | | | | [ ] Yes / [ ] No |
| 3 | [e.g., Agents reassigned to manual campaign] | | | | [ ] Yes / [ ] No |

**Containment verification:**

- [ ] Containment actions were verified to have stopped the impact
- [ ] Client / end user confirmed service restored
- [ ] Monitor reports metrics within normal range

**Risk of containment actions:**

[e.g., Manual restoration may overwrite data generated during the incident window. Rerouting to another call center may saturate capacity.]

---

## D4 — Root Cause Analysis

*Identify the fundamental cause — not the symptoms, not the blame.*

### 4.1 Detailed Timeline

| Time | Event | Observation | Source |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

### 4.2 Cause-Effect Diagram (Ishikawa / Fishbone)

*Relevant categories for customer service/financial operations:*

| Category | Possible Causes |
|---|---|
| **People** (agents, supervisors, quality) | |
| **Processes** (SOPs, management flows, escalations) | |
| **Technology** (Wolkvox, Ledger-9, Odoo, networks, VPN, telephony) | |
| **Vendors** (Altis, Northbridge Bank, Azure, Huawei, Corvant Systems) | |
| **Change Management** (deployments, configurations, permissions) | |
| **Measurement** (metrics, alerts, monitoring) | |

### 4.3 5 Whys (Root Cause Analysis)

| Why # | Question | Answer |
|---|---|---|
| 1 | Why did the incident occur? | |
| 2 | Why [answer 1]? | |
| 3 | Why [answer 2]? | |
| 4 | Why [answer 3]? | |
| 5 | Why [answer 4]? | |

**Identified root cause:**

[Root cause statement validated with data]

### 4.4 Contributing Factors

| Factor | Classification | Evidence |
|---|---|---|
| | Root cause / Contributor / Not relevant | |
| | | |

### 4.5 Root Cause Verification

- [ ] The root cause is reproduced in a controlled environment
- [ ] Statistical data confirms the correlation
- [ ] Eliminating the root cause, the effect disappears (or is not reproduced)
- [ ] The full team agrees on the identified root cause

---

## D5 — Permanent Corrective Actions (PCA)

*Definitive solutions that eliminate the root cause. Not patches.*

| # | Corrective Action | Responsible | Proposed Date | Expected Impact | Success Criterion |
|---|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |

**Best alternative selection:**

| Criterion | Alternative A | Alternative B | Alternative C |
|---|---|---|---|
| Effectiveness against root cause | High / Medium / Low | High / Medium / Low | High / Medium / Low |
| Implementation cost | High / Medium / Low | High / Medium / Low | High / Medium / Low |
| Implementation time | Short / Medium / Long | Short / Medium / Long | Short / Medium / Long |
| Implementation risk | High / Medium / Low | High / Medium / Low | High / Medium / Low |
| Sustainability | High / Medium / Low | High / Medium / Low | High / Medium / Low |

**Selected alternative:**

[Justification]

**Corrective action validation:**

- [ ] Pilot test completed with positive results
- [ ] Actions do not generate adverse side effects
- [ ] Operations team confirms feasibility

---

## D6 — Implement and Validate

*Execute corrective actions and measure their effectiveness in production.*

| # | Action | Responsible | Start Date | End Date | Status | Verification |
|---|---|---|---|---|---|---|
| 1 | | | | | [ ] Pend / [ ] Prog / [ ] Done | |
| 2 | | | | | [ ] Pend / [ ] Prog / [ ] Done | |
| 3 | | | | | [ ] Pend / [ ] Prog / [ ] Done | |

**Implementation plan:**

- Phase 1 (pilot test): [detail]
- Phase 2 (full rollout): [detail]
- Phase 3 (extended monitoring): [detail]

**Post-implementation success criteria (measure for [N] days/weeks):**

| Metric | Baseline (pre-incident) | During Incident | Post-Implementation | Target | Acceptable? |
|---|---|---|---|---|---|
| [Response time] | | | | | Yes / No |
| [Incidence rate] | | | | | Yes / No |
| [Managed accounts/day] | | | | | Yes / No |

**Final validation:**

- [ ] Incident closed without recurrence during observation period ([N] days)
- [ ] Post-implementation indicators within acceptable range
- [ ] Sponsor signs closure approval

---

## D7 — Prevent Recurrence

*Standardize the solution so that the incident does not repeat — neither here nor in other teams.*

### 7.1 Standardization

| # | Required Change | Type | Responsible | Date |
|---|---|---|---|---|
| 1 | [Update SOP / Create checklist / Modify configuration] | SOP / Tool / Process / Training | | |
| 2 | | | | |
| 3 | | | | |

### 7.2 Lessons Learned

| What worked? | What did not work? | What would we do differently? |
|---|---|---|
| | | |

### 7.3 Communication to Other Teams

- [ ] Lessons shared in operations meeting
- [ ] If applicable to other call centers (Meridian Group, Meridian Pay), socialize
- [ ] Update incident knowledge base (FOR-013)
- [ ] Include case in new agent/supervisor onboarding
- [ ] Publish in SharePoint / incident channel

### 7.4 Early Warning Metrics

| Early Warning Signal | Where to monitor | Responsible | Frequency |
|---|---|---|---|
| [e.g., High volume of abandoned calls] | Wolkvox Dashboard | | Daily |
| [e.g., Payment API error rate > 2%] | Ledger-9 Monitoring | | Real time |
| [e.g., Repeated complaints about same account code] | Quality log | | Weekly |

---

## D8 — Close and Recognize the Team

*Celebrate the work, document formal closure, and release the team.*

**8D Executive Summary:**

- **Incident:** [Name]
- **Root cause:** [One line]
- **Corrective actions implemented:** [Summary]
- **Current status:** No recurrence / Monitoring / Partially implemented
- **Projected avoided impact:** [$ RD, HH, recovered accounts]

**Team recognition:**

| Name | Outstanding Contribution |
|---|---|
| [[Name]]| |
| [[Name]]| |

**Formal closure:**

- [ ] Complete 8D document archived in project folder
- [ ] Sponsor signs closure
- [ ] Team released from 8D commitment
- [ ] Incident marked as closed in incident log
- [ ] Lessons learned transferred to project FOR-013

**Closure date:** [YYYY-MM-DD]
**Sponsor signature:** _________________________
**Facilitator signature:** _________________________

---

## Annexes

- [ ] Annex A: Wolkvox / Ledger-9 / Odoo reports from the period
- [ ] Annex B: Screenshots and logs
- [ ] Annex C: Relevant call recordings
- [ ] Annex D: Flowchart of the affected process
- [ ] Annex E: Minutes of 8D sessions
- [ ] Annex F: Updated risk matrix (FOR-008)
- [ ] Annex G: Ticket system — incident history

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2026-07-02 | [[Rodney-Ramirez]] | Initial version — 8D adaptation for customer service/financial operations |
