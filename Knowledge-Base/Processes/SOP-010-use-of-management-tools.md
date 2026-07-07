# SOP-010 — Project Management Tools Usage

**Version:** 1.0
**Last updated:** 2025
**Owner:** Project Manager / Technology Director
**Applies to:** Entire Meridian Group ecosystem team

---

## 1. Purpose

Standardize the use of digital project management tools at Meridian Group to:

- Ensure unified visibility of the status of all projects.
- Avoid inconsistent use of tools (everyone with their own system).
- Facilitate collaboration between Meridian Group, Fintrust, and Meridian Pay teams.
- Automate reports and notifications to reduce administrative burden.

---

## 2. Official Tool Stack

| Tool | Main Usage | Who uses it |
|---|---|---|
| **Microsoft Planner Premium** | Task and project management | Entire team |
| **Microsoft Teams** | Communication and meetings | Entire team |
| **SharePoint** | Document storage | Entire team |
| **Clockify** | Time tracking | Contractors + Meridian Group team |
| **Upwork** | Contracts and payments | External contractors |
| **Obsidian** | Internal knowledge base | PM + Management |
| **GitHub / Azure DevOps** | Version control and CI/CD | Technical team |

> **Rule:** If a tool is not on this list, it must be approved by the PM before being adopted in the project.

---

## 3. Microsoft Planner Premium — Standard Configuration

Planner Premium is the main management tool. Each project has its own **Plan** within the Meridian Group Microsoft 365 tenant.

### 3.1 Creating a New Plan

When starting a project, the PM creates the Plan in Planner Premium following this structure:

**Plan Name:** `[COMPANY] — [Project Name]`
Examples: `Fintrust — Sheriff Portal`, `Meridian-Pay — Odoo v17 Migration`

**Creation steps:**

1. Open Microsoft Planner from Teams or planner.microsoft.com
2. Create new Plan → select "Meridian Group Project" template if available, or blank
3. Name the Plan per convention
4. Add the project team as members
5. Link the Plan to the corresponding Teams channel
6. Configure Buckets per section 3.2

---

### 3.2 Bucket Structure (Kanban Columns)

All plans must follow this bucket structure in the same order:

| Bucket | Purpose | WIP Limit |
|---|---|---|
| **📋 Backlog** | Identified but not prioritized tasks | No limit |
| **🔄 In Progress** | Actively developing tasks | Max 3 per person |
| **👀 In Review / QA** | Completed tasks pending review | No limit |
| **✅ Completed** | Approved and closed tasks | — |
| **🚫 Blocked** | Tasks stopped by dependency or impediment | — |

> **Important:** The "Blocked" bucket should never have tasks for more than 48 hours without a documented action comment.

---

### 3.3 Task Configuration

Each task in Planner must have the following fields configured:

| Field | Required | Description |
|---|---|---|
| **Title** | ✅ Mandatory | Verb + object + context (e.g., "Implement RNC validation in form") |
| **Assigned to** | ✅ Mandatory | At least 1 responsible person |
| **Due date** | ✅ Mandatory | Never leave without a date if in current execution |
| **Bucket** | ✅ Mandatory | According to current status |
| **Labels** | ✅ Mandatory | See section 3.4 |
| **Priority** | ✅ Mandatory | Urgent / Important / Medium / Low |
| **Description** | Recommended | Context, acceptance criteria, relevant links |
| **Checklist** | Per task | For tasks with sub-steps |
| **Attachments** | Per task | Links to SharePoint documents or GitHub PRs |

**Task title — Correct format:**
```
✅ "Design login screen for Sheriff Portal"
✅ "Review and approve FOR-003 for CDM project"
✅ "Fix bug #147 in payments module"

❌ "Login" (too vague)
❌ "Pending items to review" (no verb or context)
❌ "Check with Juan" (no object or clear action)
```

---

### 3.4 Label System

Labels allow filtering and reporting by category. Standard configuration:

| Label | Color | Usage |
|---|---|---|
| **Feature** | Blue | New functionality or deliverable |
| **Bug / Fix** | Red | Error correction |
| **QA / Testing** | Yellow | Testing or validation task |
| **Documentation** | Green | Creating or updating docs |
| **Meeting / Coordination** | Purple | Management or coordination tasks |
| **Blocker** | Orange | Task that blocks others |
| **Technical debt** | Gray | Internal improvements without user impact |

> Each task must have at least **1 label**. Up to 3 labels per task can be used.

---

## 4. Kanban Board Management

### 4.1 Daily Routine (Daily Standup)

The Planner board is the reference for the Daily. Each team member:

1. Opens the board before the Daily (15 min before if possible)
2. Updates the status of their tasks
3. Moves tasks between buckets according to progress
4. Marks blocked tasks with **Blocker** label and adds a comment explaining the impediment

### 4.2 Task Movement Rules

```
To Do → In Progress     When the responsible person starts working on the task
In Progress → In Review     When development is complete and ready for QA
In Review → Completed      When QA approves or the PM validates
In Review → In Progress     If QA rejects — add comment with observations
Any bucket → Blocked  When there is an external impediment
Blocked → [previous bucket] When the block is resolved
```

---

## 5. Reports and Monitoring

### 5.1 Weekly Status Report

The PM generates the weekly report ([[FOR-007 Weekly Status Report]]) using Planner Premium's **Charts** view:

1. Go to Plan → **Charts**
2. Export or capture task status by bucket
3. Complete FOR-007 with board data + traffic light 🟢🟡🔴
4. Share in the project's Teams channel on Mondays before 10am

**Standard report metrics:**

- Tasks completed in the week
- Tasks in progress
- Blocked tasks (with blocking time)

### 5.2 Useful Filters in Planner

| Filter | What to use it for |
|---|---|
| **By assignee** | View individual workload |
| **By label** | View only Bugs, only Features, etc. |
| **By due date** | Identify overdue or soon-to-expire tasks |
| **By priority** | Escalate to Urgent what needs immediate attention |
| **By bucket** | Standard Kanban view |

### 5.3 Timeline View (Gantt)

For projects with critical dependencies, use Planner Premium's **Timeline** view:

1. Go to Plan → **Timeline**
2. Assign start and end dates to all project or phase tasks
3. Link dependencies between tasks when applicable
4. Share the view with the sponsor in follow-up meetings

---

## 6. Microsoft Teams — Channel Structure per Project

Each project has its team in Microsoft Teams with the following channel structure:

| Channel | Purpose |
|---|---|
| **General** | General project communication, announcements |
| **📋 Planner** | Tab linked to the project's Planner Plan |
| **🔧 Development** | Technical discussions, PRs, deployments |
| **🧪 QA / Testing** | Bug reports, test results |
| **📄 Documentation** | Links to docs, SharePoint updates |
| **🚨 Incidents** | Alert channel for production issues |

> The **General** channel is for formal communications. For informal coordination, use direct Teams chat or the WhatsApp group (only if the project has one).

---

## 7. SharePoint — Document Organization

### 7.1 Folder Structure per Project

```
📁 [COMPANY] - [Project]
├── 📁 01-Initiation
│   ├── FOR-001 Project Sheet
│   └── FOR-002 Project Charter
├── 📁 02-Planning
│   ├── FOR-003 Requirements Matrix
│   └── FOR-014 RACI Matrix
├── 📁 03-Execution
│   ├── FOR-007 Weekly Reports
│   └── FOR-008 Risk Matrix
├── 📁 04-Control
│   ├── FOR-009 Change Requests
│   └── FOR-010 Issue Log
├── 📁 05-Closure
│   ├── FOR-004 Test Plan
│   ├── FOR-005 Certification Matrix
│   ├── FOR-012 Final Report
│   └── FOR-013 Lessons Learned
└── 📁 06-References
    └── Reference documents, contracts, etc.
```

### 7.2 File Naming Convention

```
[FOR-XXX] [Form Name] - [Project] - v[X.X].xlsx
```

Examples:
- `FOR-002 Project Charter - Sheriff Portal - v1.0.docx`
- `FOR-007 Weekly Report - Odoo Migration - S23 2025.xlsx`

**Rules:**
- Never "final document", "final final document", "v_definitive"
- Always use version number
- Never use dates as a substitute for version

---

## 8. Clockify — Time Tracking

See [[SOP-011 Time Tracking Management]] for the complete procedure.

**Quick summary:**

- Each task in Planner must have its equivalent time entry in Clockify
- The registered time name should match the Planner task title
- Minimum: daily registration, at end of day
- The PM validates entries every Monday before generating the weekly report

---

## 9. Available Automations

Planner Premium and Microsoft Power Automate allow automations that the PM can configure:

| Automation | Trigger | Action |
|---|---|---|
| **Due date notification** | Task due in 2 days | Notifies assignee via Teams |
| **Blocked escalation** | Task in "Blocked" > 48h | Notifies PM |
| **Automatic report** | Every Monday 8am | Sends board summary to General channel |
| **New task assigned** | Task assigned to someone | Notifies assignee |
| **Task completed** | Task moves to Completed | Notifies PM for review |

**How to activate automations:**
1. Open the Plan in Planner Premium
2. Go to **Automation** (lightning icon)
3. Select template or create custom rule
4. Configure trigger and action

> Automations are the PM's responsibility. If an automation fails, the team must inform the PM to reconfigure it.

---

## 10. New Member Onboarding to the Stack

When a new member joins the project:

**Digital onboarding checklist:**

- [ ] Add as a member to the project's Planner Plan
- [ ] Add to the project's Teams team (with member permissions, not owner)
- [ ] Grant access to the project's SharePoint folder
- [ ] Create Clockify account and assign to the project workspace
- [ ] Share this SOP and [[SOP-011 Time Tracking Management]]
- [ ] Conduct a 30-min session to show the board and conventions
- [ ] Assign the first simple task for flow practice

---

## 11. Common Errors and How to Avoid Them

| Error | Impact | Solution |
|---|---|---|
| Not updating the board daily | PM has no real visibility | Establish as part of the Daily; PM reviews before each standup |
| Creating tasks without date or assignee | Orphan tasks, never completed | PM rejects tasks without these fields in weekly review |
| Using Teams chat to agree on decisions without documenting in Planner | Agreements are lost | Every decision agreed in a meeting must have its task in Planner |
| Duplicating tasks across multiple tools | Inconsistencies and confusion | Planner is the single source of truth for tasks |
| Not using labels | Impossible to filter or report by type | PM adds them if the member does not, and provides feedback |

---

## 12. Related Documents

- [[SOP-001 Project Administration]] — General framework with tools and conventions
- [[SOP-004 Project Control and Monitoring]] — KPIs and tracking reports
- [[SOP-008 Communication and Stakeholder Management]] — Communication rules by channel
- [[SOP-011 Time Tracking Management]] — Clockify procedure
- [[FOR-007 Weekly Status Report]] — Report template generated with Planner data
- [[FOR-014 RACI Matrix]] — Defines who does what (reference for task assignment)

---

## 13. Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2025 | Meridian Group PMO | Initial version |
