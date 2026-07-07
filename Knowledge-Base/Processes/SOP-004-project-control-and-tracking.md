# SOP-004 — Project Control and Monitoring

**Monitoring, reporting, and escalation process for projects in the Meridian Group strategic portfolio**

---

## 1. Purpose and Scope

### 1.1 Purpose

Define the process for continuous monitoring, report generation, and escalation of critical situations to keep projects aligned with their objectives, deadlines, and budgets.

### 1.2 Scope

Applies to all active projects in the strategic portfolio of Meridian Group and Meridian Pay during the Execution and Control phases.

### 1.3 References

- FOR-007: Weekly Status Report
- FOR-008: Risk Matrix
- SOP-001: General Project Management Methodology
- SOP-006: Risk and Issue Management

---

## 2. KPIs and Monitoring Metrics

### 2.1 Progress Metrics

| Metric | Definition | Frequency |
| --- | --- | --- |
| % Completion | Completed Stories / Total Stories | Weekly |
| Throughput | Stories closed per week | Weekly |
| Cycle Time | Average days from "In Progress" to "Completed" | Weekly |
| Blocked tasks | Number of items in Blocked status | Bi-weekly |

### 2.2 Project Health Indicators

- 🟢 **Green**: On time, no critical blockers, expected progress
- 🟡 **Yellow**: Delay <1 week, blockers being managed, low risk
- 🔴 **Red**: Delay >1 week, critical blocker, decision required

### 2.3 Alert Thresholds

- Task blocked >48h without resolution → escalation to Level 2
- Project in yellow >2 consecutive weeks → scope review
- Project in red → urgent presentation to Strategic Committee

---

## 3. Reporting Process

### 3.1 Weekly Status Report (FOR-007)

**Responsible**: Project Manager.
**Frequency**: Every Friday before 12:00.
**Distribution**: Project Sponsors + Strategic Committee.

**Minimum content**:
- General status (🟢 / 🟡 / 🔴) with justification
- Weekly progress (concrete achievements)
- Next steps (following week)
- Active blockers and resolution plan
- Newly identified risks

### 3.2 Kanban Board Report (bi-weekly)

**Responsible**: Project Manager.
**Presented at**: Bi-weekly team meeting.
**Format**: Live board review in Microsoft Planner.

**Review points**:
- Items in "Blocked": causes and responsible persons
- Items in "In Review" >3 days: accelerate validation
- Available capacity for the week

### 3.3 Portfolio Dashboard (Strategic Committee)

**Responsible**: Project Manager.
**Frequency**: Weekly Committee meeting.
**Content**: Consolidated view of all active projects with traffic light status, % progress, and critical blockers.

---

## 4. Control Meeting Cadence

| Meeting | Frequency | Duration | Participants | Objective |
| --- | --- | --- | --- | --- |
| Project team | 2x week | 30 min | PM + technical team + sponsors | Kanban, blockers, 3-day plan |
| Strategic Committee | Weekly | 30 min | Management + PM + sponsors | Portfolio, decisions, escalations |
| One-on-one with sponsor | As needed | 15 min | PM + sponsor | Alignment, feedback, quick decisions |

---

## 5. Blocker Management

### 5.1 Identification

A blocker is any impediment that prevents a task from progressing. It is recorded as:
- Item in "Blocked" status in Planner with `Blocker` label
- Description of the impediment and responsible person for resolution
- Identification date

### 5.2 Resolution Process

1. PM identifies blocker in meeting or report
2. Assigns resolution responsible and deadline
3. Daily follow-up until resolution
4. If not resolved within timeframe, escalate according to levels (see section 6)

### 5.3 Maximum Times by Level

| Impact Level | Maximum Time | Responsible |
| --- | --- | --- |
| Low (does not block others) | 5 business days | Technical team |
| Medium (blocks 1 task) | 48 hours | PM + Sponsor |
| High (blocks multiple tasks) | 24 hours | PM + Committee |
| Critical (for the project) | 4 hours | Strategic Committee |

---

## 6. Escalation Levels

| Level | Who | When |
| --- | --- | --- |
| **Level 1 — PM** | Project Manager | Delays <48h, simple operational impediments |
| **Level 2 — Sponsor** | Project Sponsor | Resource conflict, delays >48h, priority changes |
| **Level 3 — Committee** | Strategic Committee | Scope changes, critical risks, strategic decisions |

**Escalation protocol**:
1. PM documents the problem with context and proposed alternatives
2. Direct contact to the corresponding level (do not wait for scheduled meeting)
3. Expected response within the blocker's maximum time
4. Decision documented in Planner and communicated to the team

---

## 7. Change Control (summary)

Any modification to scope, schedule, or resources must follow the SOP-005 process. The Project Manager cannot approve changes unilaterally. Every change must be recorded and traceable.

---

## 8. Roles and Responsibilities

### 8.1 Project Manager

- Keep the Kanban board updated in real time
- Issue the Weekly Status Report (FOR-007)
- Facilitate control meetings
- Escalate blockers according to defined levels
- Monitor KPIs and alert when thresholds are exceeded

### 8.2 Project Sponsors

- Review and respond to the Status Report within 24h
- Participate in bi-weekly meetings
- Make decisions within their level of authority
- Unblock resources from their area when required

### 8.3 Strategic Committee

- Review the portfolio dashboard weekly
- Make Level 3 decisions within the required 4–24h
- Resolve resource conflicts between projects
- Approve significant scope changes

### 8.4 Project Team

- Update task status in Planner daily
- Report blockers immediately to the PM
- Participate in bi-weekly meetings

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | AUG-2025 | Rodney Ramirez | Initial version |
|  |  |  |  |
