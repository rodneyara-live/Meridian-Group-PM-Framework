# SOP-001 — Project Administration

**Hybrid project management methodology for Meridian Group and Meridian Pay**

---

## 1. Purpose and Scope

### 1.1 Purpose

Establish the hybrid project management methodology for Meridian Group and Meridian Pay that combines traditional management phases with Kanban boards for operational monitoring, adapted to cross-functional teams balancing daily operations with strategic projects.

### 1.2 Scope

This SOP applies to all projects in the strategic portfolio of Meridian Group and Meridian Pay, including AI, automation, platform development, and technology modernization initiatives.

### 1.3 References

- FOR-001: Project Sheet
- FOR-002: Project Charter
- FOR-007: Weekly Status Report
- SOP-002: Project Initiation Process
- SOP-004: Project Control and Monitoring

---

## 2. Meridian Group Hybrid Methodology

### 2.1 Model Characteristics

- **Traditional Phases**: Initiation, Planning, Execution, Control, and Closure
- **Kanban Monitoring**: Visual states (To Do, In Progress, Blocked, In Review, Completed)
- **Cross-functional Teams**: Operations personnel dedicating part-time to projects

### 2.2 Differences from Traditional Methodologies

| Aspect | Traditional | Meridian Group Hybrid |
| --- | --- | --- |
| Resources | 100% dedicated | Cross-functional (10–20% dedication) |
| Monitoring | Monthly meetings | Weekly Strategic Committee meetings + twice weekly with the team |
| States | Sequential phases | Kanban with parallel phases |
| Approach | Extensive documentation | Minimum viable documentation |

---

## 3. Phase Structure

### 3.1 Initiation Phase

**Objective**: Formalize the project and obtain authorization.

**Mandatory deliverables**:
- Project Sheet (FOR-001)
- Project Charter (FOR-002)
- Initial RACI Matrix
- Stakeholder identification

**Exit criteria**: Formal sponsor approval.

### 3.2 Planning Phase

**Objective**: Define requirements and execution strategy.

**Mandatory deliverables**:
- Requirements Matrix (FOR-003)
- Test Plan (FOR-004)
- Critical risk identification
- High-level schedule

**Exit criteria**: Plan approved by Strategic Committee.

### 3.3 Execution Phase

**Objective**: Develop and build project deliverables.

**Main activities**:
- Development/implementation according to requirements
- Bi-weekly progress monitoring
- Impediment and risk management
- Regular communication with stakeholders

### 3.4 Control Phase (Parallel to Execution)

**Objective**: Monitor progress and manage changes.

**Main activities**:
- Weekly status reports
- Team meetings twice per week
- Weekly Strategic Committee meetings
- Change and risk management

### 3.5 Closure Phase

**Objective**: Formalize delivery and capture learnings.

**Mandatory deliverables**:
- Quality certification
- Formal sign-offs
- Lessons learned
- Final documentation

---

## 4. Requirements Management with User Stories

### 4.1 User Story Structure

**Standard format**:
- As a [user type]
- I want [functionality/action]
- So that [benefit/objective]

### 4.2 Acceptance Criteria

Each User Story must include:
- **Acceptance Criteria**: Specific conditions that must be met
- **Definition of "Done"**: Technical validation checklist
- **Test Cases**: Specific testing scenarios

### 4.3 Story Categorization

**By Priority (MoSCoW):**
- **Must** — Critical for basic functionality
- **Should** — Important but not critical
- **Could** — Desirable if time/resources allow
- **Won't** — Outside current scope

**By Complexity:**
- **XS** — 1–2 hours (minor configurations)
- **S** — 3–8 hours (simple tasks)
- **M** — 1–2 days (standard development)
- **L** — 3–5 days (complex functionalities)
- **XL** — >1 week (must be split into smaller stories)

---

## 5. Kanban Monitoring System

### 5.1 Board States

1. **To Do** — Tasks defined but not started
2. **In Progress** — Tasks in active development
3. **Blocked** — Tasks with identified impediments
4. **In Review** — Completed tasks pending validation
5. **Completed** — Finished and accepted tasks

### 5.2 WIP Limits (Work in Progress)

- **In Progress**: Maximum 3 tasks per person
- **In Review**: Maximum 5 tasks per project
- **Blocked**: Mandatory resolution within 48 hours

### 5.3 Label System

**Project Labels** — According to strategic initiatives table (e.g. `2.1.1.1 SCORE-PROB-PAGOS`)

**Phase Labels**:
- Initiation Phase
- Planning Phase
- Execution Phase
- Control Phase
- Closure Phase

**Priority Labels**:
- Critical (blocking for other projects)
- High (committed date)
- Medium (target date)
- Low (can be deferred)

---

## 6. Meeting Cadence

### 6.1 Team Meetings (twice per week)

**Frequency**: Twice per week, minimum two days between meetings.
**Duration**: 30 minutes.
**Participants**: PM, active project sponsors, key resources.

**Agenda**:
- Kanban board review (10 min)
- Blocker identification (5 min)
- Planning for next 3 days (5 min)
- AOB / Miscellaneous (5 min)

### 6.2 Weekly Strategic Committee Meetings

**Frequency**: Weekly.
**Duration**: 30 minutes.
**Participants**: Management, PM, sponsors.

**Agenda**:
- Project board (10 min)
- Escalations and decisions (10 min)
- Organizational communication (5 min)

### 6.3 Ad-hoc Meetings

- **Blocker resolution**: Maximum 24 hours to convene
- **Scope changes**: Within 48 hours of identification
- **Crisis / Escalations**: Immediate

---

## 7. Folder Structure and Documentation

### 7.1 Standard Naming

```
[PROJECT_NAME]/
   01_Initiation/
     Project_Sheet_v[X.X].docx
     Project_Charter_v[X.X].docx
     Stakeholder_Matrix_v[X.X].xlsx
   02_Planning/
     Requirements_v[X.X].docx
     RACI_Matrix_v[X.X].xlsx
     Risk_Register_v[X.X].xlsx
     Test_Plan_v[X.X].docx
   03_Execution/
     Weekly_Reports/
     Minutes/
     Change_Requests/
   04_Control/
     Metrics_Dashboard_v[X.X].xlsx
   05_Closure/
     Final_Report_v[X.X].docx
     Lessons_Learned_v[X.X].docx
     Sign_offs.pdf
```

### 7.2 Document Versioning

- **Major Version (X)**: Significant changes requiring re-approval
- **Minor Version (.X)**: Minor updates, corrections, additions

---

## 8. Roles and Responsibilities

### 8.1 Project Manager

- Facilitate bi-weekly and weekly meetings
- Keep the Kanban board updated
- Escalate blockers to the steering committee
- Ensure compliance with methodology and documentation

### 8.2 Project Sponsors

- Provide resources and make project decisions
- Participate in bi-weekly meetings
- Validate project deliverables
- Communicate priority changes

### 8.3 Strategic Committee

- Make strategic decisions about the portfolio
- Resolve resource conflicts between projects
- Approve significant scope changes
- Communicate decisions to the organization

### 8.4 Project Resources (Cross-functional)

- Execute assigned tasks within agreed timelines
- Update task status on the board
- Report impediments immediately
- Participate in meetings as required

---

## 9. Metrics and KPIs

### 9.1 Individual Project Metrics

- **Throughput**: User Stories completed per week
- **Lead Time**: Total time from backlog to completion
- **Cycle Time**: Time from "In Progress" to "Completed"
- **Blocker rate**: Frequency and average resolution time
- **Delivery quality**: % of Stories accepted without rework

### 9.2 Portfolio Metrics

- **Projects on time**: % of projects meeting target date
- **Resource utilization**: % of actual vs. planned dedication
- **Change rate**: Story modifications per project
- **Sponsor satisfaction**: Survey post-delivery of each phase
- **Value delivered**: % of "Must Have" Stories completed

---

## 10. Escalation and Risk Management

### 10.1 Escalation Levels

1. **Level 1 — PM**: Operational impediments, delays <48h
2. **Level 2 — Sponsor**: Resource conflicts, delays >48h
3. **Level 3 — Steering**: Scope changes, critical risks

### 10.2 Response Time

- **Critical Blocker**: 4 hours
- **High Blocker**: 24 hours
- **Medium Blocker**: 48 hours

---

## 11. Tools and Technology

### 11.1 Microsoft Planner

- Kanban board management
- Project and phase labeling
- Automatic reports
- Integration with Teams and Outlook

### 11.2 Microsoft Teams

- Bi-weekly and weekly meetings
- Automatic meeting transcription
- Project channels for communication

### 11.3 SharePoint

- Document repository per project
- Automatic version control
- Form templates

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | 10-AUG-2025 | Rodney Ramirez | Initial version |
|  |  |  |  |
