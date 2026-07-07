# SOP-006 — Risk and Issue Management

**Proactive identification, evaluation, and mitigation of risks in Meridian Group portfolio projects**

---

## 1. Purpose and Scope

### 1.1 Purpose

Establish the process for identifying, evaluating, prioritizing, and mitigating risks and issues (active problems) in projects, minimizing their impact on objectives, schedule, and deliverable quality.

### 1.2 Scope

Applies to all strategic portfolio projects. Risk management is continuous from the Initiation phase through Closure.

### 1.3 References

- FOR-008: Risk Matrix
- FOR-010: Issue Log
- SOP-004: Project Control and Monitoring

---

## 2. Definitions

- **Risk**: Future and uncertain event that, if it occurs, negatively impacts the project. Managed *proactively*.
- **Issue**: Problem that has already occurred and is actively affecting the project. Requires *immediate* action.
- **Blocker**: Issue that prevents the progress of one or more tasks. Managed on the Kanban board.

---

## 3. Risk Management Process

### 3.1 Identification

**When**: At project start and continuously at each follow-up meeting.

**Techniques**:
- Review of lessons learned from previous projects
- Brainstorming session with the team and sponsors
- Analysis of technical and resource dependencies
- Review of the regulatory and technology environment

**Frequent risk categories at Meridian Group**:
- Availability of cross-functional resources
- Dependencies on legacy systems (Ledger-9, MIFOS)
- Regulatory or compliance changes
- Technology maturity of the solution (AI, integrations)
- Turnover or absence of key people

### 3.2 Evaluation — Impact / Probability Matrix

| | Low Probability | Medium Probability | High Probability |
| --- | --- | --- | --- |
| **High Impact** | 🟡 Medium | 🔴 High | 🔴 Critical |
| **Medium Impact** | 🟢 Low | 🟡 Medium | 🔴 High |
| **Low Impact** | 🟢 Low | 🟢 Low | 🟡 Medium |

**Impact Scale**:
- **High**: Compromises project objectives, delay >2 weeks, loss of key deliverables
- **Medium**: Delay 1–2 weeks, requires resource reassignment
- **Low**: Delay <1 week, mitigable without affecting milestones

**Probability Scale**:
- **High**: >60% occurrence in the current context
- **Medium**: 30–60% occurrence
- **Low**: <30% occurrence

### 3.3 Response Strategies

| Strategy | When to Use | Example |
| --- | --- | --- |
| **Avoid** | Critical or high risk | Redesign the solution to eliminate the risky dependency |
| **Mitigate** | Medium/high risk with options | Train a backup for a critical role |
| **Transfer** | Technical risk with third parties | Include SLA in vendor contract |
| **Accept** | Low risk or no alternative | Document and monitor without proactive action |

### 3.4 Registration and Monitoring (FOR-008)

Each risk is recorded in the Risk Matrix (FOR-008) with:
- Unique ID
- Clear description
- Category
- Probability / Impact / Level
- Responsible person for mitigation plan
- Mitigation actions
- Status (Active / Mitigated / Closed)
- Last review date

**Review frequency**: Weekly for High/Critical risks; bi-weekly for Medium; monthly for Low.

---

## 4. Issue Management Process

### 4.1 Identification and Registration (FOR-010)

When a risk materializes or a new problem arises, it becomes an **Issue**. It is recorded in the Issue Log (FOR-010) with:
- Unique ID
- Problem description
- Current impact on the project
- Responsible person for resolution
- Actions taken
- Resolution deadline
- Status (Open / In Progress / Closed)

### 4.2 Issue Classification

| Severity | Description | Maximum Resolution Time |
| --- | --- | --- |
| **Critical** | For the project, data corruption, security breach | 4 hours |
| **High** | Main functionality broken, blocks multiple tasks | 24 hours |
| **Medium** | Blocks one task, workaround available | 48 hours |
| **Low** | Minor problem, does not block progress | Next iteration |

### 4.3 Issue Escalation

- **Critical / High without resolution in time**: Escalate immediately to Strategic Committee
- **Medium without resolution**: PM convenes ad-hoc meeting with sponsor
- **Recurring issue pattern**: Review root causes in retrospective

---

## 5. Integration with Follow-up Meetings

| Meeting | Risk Review | Issue Review |
| --- | --- | --- |
| Bi-weekly team | New risks identified | Active blockers |
| Weekly Committee | High/Critical risks | Critical/high issues |
| Weekly report (FOR-007) | Top 3 active risks | Open issues with closing date |

---

## 6. Roles and Responsibilities

### 6.1 Project Manager

- Keep FOR-008 and FOR-010 updated
- Facilitate risk identification in meetings
- Escalate issues according to defined classification
- Report risks and issues in weekly FOR-007

### 6.2 Project Sponsor

- Approve mitigation plans for High/Critical risks
- Resolve issues requiring business decisions
- Identify risks from the area's perspective

### 6.3 Project Team

- Report risks and issues to the PM as soon as identified
- Execute assigned mitigation plans
- Update issue status in Planner

### 6.4 Strategic Committee

- Approve response strategies for critical risks
- Resolve high organizational impact issues
- Review the top portfolio risks weekly

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | AUG-2025 | Rodney Ramirez | Initial version |
|  |  |  |  |
