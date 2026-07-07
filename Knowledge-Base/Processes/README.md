# Processes — Meridian Group SOPs

This folder contains the **Standard Operating Procedures (SOPs)** of the Meridian Group ecosystem — documents written for the human team. They define how work is done: from how a project is initiated to how it is closed, including risk management, changes, communication, and tool usage.

> **Workflows for Claude:** WFs (operational instructions for Claude) live in the sibling folder `[[Knowledge-Base/Workflows/README|Workflows/]]`.

All documents are written to be used as active reference during work, not as archival documentation.

---

## SOP Index

### 🏗️ Project Lifecycle

These SOPs cover project phases in chronological order. Together they form the complete project management framework of Meridian Group.

| Code | Name | When to use |
|---|---|---|
| [[SOP-001-project-administration\|SOP-001]] | Project Administration | General framework — read first |
| [[SOP-002-project-initiation-process\|SOP-002]] | Project Initiation | When starting a new project |
| [[SOP-003-requirements-gathering-and-management\|SOP-003]] | Requirements Gathering and Management | When capturing client needs |
| [[SOP-004-project-control-and-tracking\|SOP-004]] | Project Control and Monitoring | Throughout execution (weekly) |
| [[SOP-009-project-closure\|SOP-009]] | Project Closure | When finishing or canceling a project |

### 🔄 Change, Risk, and Issue Management

| Code | Name | When to use |
|---|---|---|
| [[SOP-005-change-management\|SOP-005]] | Change Management | When a scope or priority change arises |
| [[SOP-006-risk-and-issue-management\|SOP-006]] | Risk and Issue Management | When identifying risks or active issues |

### ✅ Quality and Delivery

| Code | Name | When to use |
|---|---|---|
| [[SOP-007-testing-and-quality-control\|SOP-007]] | Testing and Quality Control | During QA and before production |

### 📣 Communication and Stakeholders

| Code | Name | When to use |
|---|---|---|
| [[SOP-008-communication-and-stakeholder-management\|SOP-008]] | Communication and Stakeholder Management | When planning communications or managing expectations |

### 🛠️ Tools and Operations

| Code | Name | When to use |
|---|---|---|
| [[SOP-010-use-of-management-tools\|SOP-010]] | Management Tools Usage | To configure Planner, Teams, SharePoint on a project |
| [[SOP-011-hour-log-management\|SOP-011]] | Time Tracking Management | To log hours in Clockify and Upwork |

### 📊 Reporting and Management Communication

| Code | Name | When to use |
|---|---|---|
| [[SOP-012-weekly-executive-summary\|SOP-012]] | Weekly Executive Portfolio Summary | Before the Tactical Early Bird or when Management requests a portfolio snapshot |

---

## Interconnection between SOPs

The project lifecycle connects all SOPs as follows:

```
SOP-002 Initiation
    ↓
SOP-003 Requirements
    ↓
SOP-010 Tools (configure from the start)
    ↓
SOP-004 Monitoring ←→ SOP-005 Changes
    ↑                ←→ SOP-006 Risks/Issues
    ↑                ←→ SOP-007 QA/Testing
    ↑                ←→ SOP-008 Communication
    ↑                ←→ SOP-011 Hours
    ↓
SOP-009 Closure
```

[[SOP-001-project-administration|SOP-001]] is the framework that contains and regulates all others.

---

## Related Forms

The SOPs reference forms (FOR) located in [[Templates/project-templates/README|Templates → project-templates]].

| Form | Name | SOP that uses it |
|---|---|---|
| FOR-001 | Project Sheet | SOP-002 |
| FOR-002 | Project Charter | SOP-002, SOP-009 |
| FOR-003 | Requirements Matrix | SOP-003 |
| FOR-004 | Test Plan | SOP-007, SOP-009 |
| FOR-005 | Certification Matrix | SOP-007, SOP-009 |
| FOR-007 | Weekly Status Report | SOP-004, SOP-010 |
| FOR-008 | Risk Matrix | SOP-006 |
| FOR-009 | Change Request | SOP-005 |
| FOR-010 | Issue Log | SOP-006 |
| FOR-011 | Communication Plan | SOP-008 |
| FOR-012 | Final Project Report | SOP-009 |
| FOR-013 | Lessons Learned Record | SOP-009 |
| FOR-014 | RACI Matrix | SOP-001, SOP-010 |

---

## How to Maintain These Documents

- **Owner:** The PM is responsible for keeping SOPs updated.
- **Review:** At least once per quarter, or when a major project reveals a gap.
- **Updates:** Modify the MD file directly and update the version in the document's Version Control.
- **Suggestions:** Any team member can propose changes through Teams channels or directly to the PM.

---

## Related Links

- [[START-HERE]] — Vault entry point
- [[CONTEXT]] — General context of the Meridian Group ecosystem
- [[Organization/README]] — People and companies directory
- [[Projects/README]] — Active projects and their status
