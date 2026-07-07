# SOP-009 — Project Closure

**Version:** 1.0
**Last updated:** 2025
**Owner:** Project Manager / General Management
**Applies to:** All projects in the Meridian Group ecosystem

---

## 1. Purpose

Standardize the formal project closure process to ensure that:

- All deliverables are accepted and documented.
- Lessons learned are recorded and accessible.
- Resources (people, tools, access) are properly released.
- Generated knowledge is transferred to the operational team.
- Complete traceability exists from initiation to closure.

---

## 2. Scope

Applies to all projects regardless of type (technological, operational, transformation), size, or duration. Includes projects closed by:

- **Successful completion** — objectives were met.
- **Cancellation** — the project was stopped before completion.
- **Indefinite suspension** — the project is paused with no set resumption date.

---

## 3. Key Concepts

| Term | Definition |
|---|---|
| **Formal closure** | Documented process of project conclusion with sponsor approval |
| **Deliverable acceptance** | Client/sponsor validation and sign-off that deliverables meet agreed criteria |
| **Lessons learned** | Structured record of what worked, what failed, and recommendations for future projects |
| **Operational handoff** | Transfer of the system/product to the team that will operate it in production |
| **Final report** | Consolidated project performance document (see [[FOR-012 Final Project Report]]) |

---

## 3.5 Minimum Viable Closure Checklist

> The reality of the Meridian Group portfolio is that projects close under pressure to start the next one. This checklist ensures the essentials are documented, even when there is no time for the full process in sections 4–6.
>
> **For smaller projects:** completing only this checklist is acceptable.
> **For significant projects** (duration >3 months, +5 people, production impact): complete the full process from sections 4–6. This is where FOR-012 and FOR-013 apply in full force.

### Minimum Closure — 5 questions in the Logbook

When closing any project, add a final entry in `Logbook.md` answering these 5 questions:

```
**[YYYY-MM-DD]** Project closure

**Status:** 🟢 Completed · **Completeness:** 100%

Was what was promised delivered?
[What was delivered vs. what was in the project charter]

What went well and should we repeat?
[1-3 concrete practices to keep]

What will we not do again?
[1-3 specific things that did not work]

What was left pending or out of scope?
[Items not delivered, with justification]

Was there any production impact after go-live?
[Bugs, incidents, or tickets in the first 30 days]
```

### Minimum closure actions (all projects)

- [ ] Update `status: 🟢 Completed` and `completeness: 100%` in project README frontmatter
- [ ] Update project status in `Projects/README.md`
- [ ] Add closure entry in `Logbook.md` with the 5 questions
- [ ] Close or archive the project in MS Planner
- [ ] Notify the sponsor formally

---

## 4. Closure Phases

### 4.1 Completeness Verification

Before initiating formal closure, the PM must verify that all deliverables defined in the Project Charter ([[FOR-002 Project Charter]]) are completed or justified.

**Verification checklist:**

- [ ] All deliverables from the original scope are complete or documented as exceptions
- [ ] The test plan ([[FOR-004 Test Plan]]) was executed and approved
- [ ] The certification matrix ([[FOR-005 Certification Matrix]]) is signed
- [ ] No critical or high issues are open without documented resolution
- [ ] Priority requirements (Must Have) are implemented and accepted
- [ ] Technical and user documentation is ready for delivery

---

### 4.2 Formal Client/Sponsor Acceptance

The PM coordinates with the sponsor and/or client to review and formally accept deliverables.

**Process:**

1. Prepare the delivery package with all deliverables and their documentation.
2. Conduct a final demonstration/review session with the sponsor.
3. Obtain the acceptance signature on the [[FOR-012 Final Project Report]].
4. If there are observations, record them as future improvements (outside the current project scope).

**Maximum time to obtain acceptance:** 5 business days from the final demo.

> If the sponsor does not respond within 5 business days, the **acceptance by silence** policy applies: the PM documents contact attempts and the project is marked as closed pending signature.

---

### 4.3 Operational Handoff

For technological projects or those generating a new system/process, a formal transfer to the operational team must be performed.

**Handoff elements:**

| Element | Responsible | Deliverable |
|---|---|---|
| Technical documentation | Tech Lead | Wiki / README in repository |
| User manual | PM / Analyst | Document in SharePoint |
| Access and credentials | Tech Lead | Secure record in password manager |
| Operations runbook | Tech Lead | Document in SharePoint |
| Support contacts | PM | Included in Final Report |
| Operational team training | PM coordinates | Recorded or in-person session |

**Handoff checklist:**

- [ ] Technical documentation delivered and reviewed by the receiving team
- [ ] User manual available in SharePoint
- [ ] Access transferred and verified
- [ ] Training session completed (attach recording or minutes)
- [ ] Operational team confirms they can operate autonomously

---

### 4.4 Lessons Learned Session

**Mandatory** for all projects longer than 4 weeks or with more than 3 people involved. **Recommended** for smaller projects.

**Session format:**

- **Duration:** 60–90 minutes
- **Participants:** Full project team + sponsor (optional)
- **Facilitator:** PM (should not be the one contributing opinions, should facilitate)
- **Tool:** Microsoft Teams + collaborative whiteboard

**Session structure:**

| Section | Time | Guiding questions |
|---|---|---|
| What went well? | 20 min | What practices should we repeat? What gave us an advantage? |
| What went wrong? | 20 min | What problems did we face? What slowed down the project? |
| What would we do differently? | 20 min | If we started over, what would we change? |
| Recommendations | 10 min | What should we standardize or avoid in future projects? |
| Closing | 10 min | Acknowledgments, recognitions, next steps |

**Session rule:** No blame-seeking. Lessons belong to the system, not the people.

The PM completes [[FOR-013 Lessons Learned Record]] with the session inputs and archives it in SharePoint and the Obsidian Vault.

---

### 4.5 Resource Release

**People:**

- Notify each team member of the project end and their release from the team.
- Update People/ files if the role or company changes.
- Formally recognize contributions (recommended: message in the team's Teams channel).

**Tools and access:**

- [ ] Delete or archive the project in Microsoft Planner
- [ ] Revoke temporary access to client systems
- [ ] Archive code repository (read-only mode)
- [ ] Close temporary communication channels (Teams, WhatsApp) or convert them to archives

**Documentation:**

- [ ] Move project folder to `Archive/` in SharePoint
- [ ] Update project status in the central project register
- [ ] Archive in Obsidian Vault if applicable

---

### 4.6 Final Report and Documentary Closure

The PM prepares the [[FOR-012 Final Project Report]] consolidating:

- Executive project summary
- Comparison of planned vs. actual scope, time, and cost
- Final project KPIs
- Issues and risks that materialized
- Deliverable status
- Sponsor acceptance signature
- Link to [[FOR-013 Lessons Learned Record]]

**This is the only document that must be signed. Without it, the project is not considered formally closed.**

---

## 5. Closure by Cancellation or Suspension

When a project is canceled or suspended before completion, the closure process is equally mandatory, adapted:

| Step | Cancellation | Suspension |
|---|---|---|
| Document reason | Yes — with formal justification | Yes — with resumption conditions |
| Operational handoff | Partial — according to progress | Not applicable yet |
| Lessons learned | Yes — especially cancellation causes | Recommended |
| Resource release | Complete | Partial — case by case |
| Final report | Abbreviated version | Abbreviated version with current status |

> **Policy:** No project can be canceled without formal documentation approved by General Management.

---

## 6. Closure Metrics

The Final Report must include the following metrics:

| Metric | Formula |
|---|---|
| Scope variance | (Delivered requirements / Planned requirements) × 100% |
| Time variance | Actual days − Planned days |
| Cost variance | Actual cost − Planned cost |
| Defect rate | Critical/high bugs found in production in the first 30 days |
| Sponsor satisfaction | Scale 1–5, collected in the acceptance session |
| Documented lessons | Number of lessons recorded in FOR-013 |

---

## 7. Roles and Responsibilities

| Role | Closure Responsibilities |
|---|---|
| **Project Manager** | Coordinate the entire process, prepare Final Report, facilitate lessons session |
| **Tech Lead** | Deliver technical documentation, execute system handoff |
| **Sponsor / Director** | Validate and sign deliverable acceptance |
| **Project Team** | Participate in lessons session, complete assigned closure tasks |
| **Receiving Team (Ops)** | Confirm handoff and training |

---

## 8. Related Documents

- [[FOR-012 Final Project Report]] — Formal closure document with signatures
- [[FOR-013 Lessons Learned Record]] — Project knowledge capture
- [[FOR-002 Project Charter]] — Original scope reference
- [[FOR-004 Test Plan]] — Deliverable validation
- [[FOR-005 Certification Matrix]] — Technical acceptance
- [[SOP-001 Project Administration]] — General lifecycle framework
- [[SOP-002 Project Initiation]] — Cycle entry point

---

## 9. Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2025 | Meridian Group PMO | Initial version |
| 1.1 | 2026-02-19 | [[Rodney-Ramirez]] | Adds section 3.5 Minimum Viable Checklist and 5 closure questions in Logbook |
