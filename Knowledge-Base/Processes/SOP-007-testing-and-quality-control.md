# SOP-007 — Testing and Quality Control

**Agile testing process to ensure quality without excessive bureaucracy, focused on practical validation of technology deliverables**

---

## 1. Purpose and Scope

### 1.1 Purpose

Establish an agile testing process that ensures quality without creating excessive bureaucracy, focused on practical validation of technology deliverables for AI, automation, and critical integration projects at Meridian Group.

### 1.2 Scope

Applies to all strategic portfolio projects, prioritizing efficiency over extensive documentation and results over process.

### 1.3 References

- SOP-001: General Project Management Methodology
- SOP-003: Requirements Gathering and Management
- FOR-003: Requirements Matrix
- FOR-004: Test Plan

---

## 2. Testing Principles

### 2.1 Practical Approach

**Tests That Add Value**:
- Validate critical business functionality
- Confirm mandatory requirements are met
- Verify integration with existing systems
- Ensure acceptable user experience

**Avoid Unnecessary Tests**:
- Do not perform exhaustive testing of minor functions
- Do not create test cases for obvious scenarios
- Do not excessively document simple processes
- Do not duplicate validations between teams

### 2.2 Risk-Oriented Testing

**High Risk = Mandatory Tests**:
- Integrations with core systems (Ledger-9, MIFOS)
- Financial calculations and scoring
- AI functionality affecting customer experience
- Automated financial operations processes

**Low Risk = Optional Tests**:
- Administrative configuration interfaces
- Non-critical reports
- Cosmetic or minor UX functions
- Documentation and help texts

### 2.3 "Functionally Acceptable" Criteria

- Works for primary use cases
- Acceptable performance under normal conditions
- User can complete flows without blockers
- Minor issues do not prevent operation

---

## 3. Types of Testing by Project

### 3.1 AI Projects (SLM, Agents)

**Critical Tests**:
- Accuracy in defined use cases (target >75%)
- Appropriate responses for financial operations scenarios
- Correct database integration
- Response time <5 seconds

**Sufficient Validation**:
- 10–15 representative test cases per category
- Sample of responses reviewed by business user
- Performance test with 50+ concurrent queries

### 3.2 Automation and Integrations

**Critical Tests**:
- Data transfers correctly between systems
- Business rules applied correctly
- Processes complete end-to-end without errors
- Rollback function works if problems arise

**Sufficient Validation**:
- Main flow works
- 2–3 error scenarios handled correctly
- Logs enable basic problem resolution

### 3.3 Scoring and Analytics

**Critical Tests**:
- Mathematical calculations are correct
- Data source is reliable and up-to-date
- Results are reproducible
- Acceptable performance with real data

---

## 4. Testing Process

### 4.1 Testing During Development

**Daily Testing (Informal)**:
- Developer performs basic functionality test
- Business user validates sample scenarios
- Critical problems reported immediately via WhatsApp/Teams
- Fixes applied within the day if possible

**Weekly Testing (Semi-formal)**:
- Demonstration of new functionality
- Stakeholder confirms acceptability
- Simple list of issues for the following week
- Go/no-go decision if it is a critical milestone

### 4.2 Pre-Production Testing

**Final Testing Week**:
- Execute critical test cases
- Business stakeholder confirms readiness
- Technical lead confirms no critical blockers
- Project manager documents final approvals

**Go-Live Criteria**:
- [ ] Mandatory use cases work
- [ ] Acceptable performance under normal load
- [ ] Primary stakeholder gives approval
- [ ] Rollback plan documented
- [ ] Support team notified of release

### 4.3 Post-Deployment

**First Week**:
- Daily problem monitoring
- Quick resolution of critical problems
- Collection of feedback from real users
- Minor adjustments if necessary

---

## 5. Quality Criteria

### 5.1 Technical Criteria

**Performance**:
- Response time <5 sec for normal queries
- System available during business hours
- Recovery <30 min if there is an outage

**Functionality**:
- Mandatory requirements working
- Core integrations stable
- Critical calculations correct

**Usability**:
- User can complete main flows
- Error messages are understandable
- Process flow is logical

### 5.2 Business Criteria

**Operational Readiness**:
- Users know how to use the new functionality
- Process fits within existing flows
- Business metrics show improvement or no degradation

**Risk Acceptance**:
- Known issues are documented
- Business impact is acceptable
- Mitigation plans exist for high-risk areas

---

## 6. Problem Management

### 6.1 Classification

**Critical**: System down, data corruption, security breach.
- Fix immediately (same day)
- All resources available
- Communication to all stakeholders

**High**: Main functionality broken.
- Fix within 2–3 days
- May require resource reassignment
- Weekly status update

**Medium / Low**: Minor, cosmetic problems.
- Fix in next iteration or version
- Document in simple list
- Address when convenient

### 6.2 Management Flow

- **Report**: Simple message via Teams/WhatsApp with screenshot
- **Tracking**: Excel with Status, Priority, Responsible, Target Date
- **Resolution**: Developer confirms fix, original reporter validates
- **Closure**: Mark as resolved (no extensive documentation needed)

### 6.3 Escalation

**When to escalate**:
- Critical problem not resolved in 4 hours
- Problem pattern indicating fundamental failure
- Resource conflicts preventing resolution
- Business stakeholder requests escalation

**How to escalate**:
- Direct message to Project Manager
- Include brief summary of the problem and attempts made
- Suggest required resources or decision needed

---

## 7. Roles and Responsibilities

### 7.1 Project Manager

- Ensure tests are performed (not necessarily do them)
- Make go/no-go decisions with stakeholder input
- Escalate problems teams cannot resolve
- Document final approval for production

### 7.2 Business Stakeholder

- Define what "working correctly" means
- Test critical business scenarios
- Give final approval for deployment to production
- Be available for quick decisions during testing

### 7.3 Technical Lead

- Ensure the system can handle expected load
- Validate integrations and technical architecture
- Resolve technical problems
- Confirm deployment readiness

### 7.4 Key Users

- Test real-world scenarios
- Provide feedback on usability
- Confirm training and readiness
- Be first-line support post-deployment

---

## 8. Required Documentation

### 8.1 Required Documents

**FOR-004: Test Plan**:
- List of critical scenarios (maximum 10–20 items)
- Who will test what
- Schedule to complete testing
- Go/no-go criteria

**Problem Log (Excel)**:
- Columns: Problem Description, Priority, Responsible, Status
- Updated weekly during active development
- Closed problems archived monthly

**Certification Summary**:
- Key tests completed
- Major problems resolved or accepted
- Stakeholder approvals obtained
- Production readiness confirmed

### 8.2 Documents Not Required

- Detailed test case specifications
- Extensive test execution reports
- Complex traceability matrices
- Formal defect lifecycle documentation
- Multi-page certification documents

### 8.3 Communication Preferences

**Prefer**:
- Quick Teams/WhatsApp updates over formal reports
- Screenshots over written descriptions
- Verbal confirmation over written approvals
- Action items over meeting minutes

**Document only when**:
- The decision affects multiple teams
- There are compliance or audit requirements
- Knowledge needs to be retained long-term
- Technical configuration is complex

---

## 9. Practical Templates

### 9.1 Simple Test Plan

```
PROJECT: [Name]
TEST PERIOD: [Start – End]

CRITICAL TEST SCENARIOS:
1. [Business Scenario 1] – Responsible: [Name]
2. [Business Scenario 2] – Responsible: [Name]
3. [Technical Integration 1] – Responsible: [Name]
[Continue for maximum 10–20 scenarios]

GO-LIVE CRITERIA:
- [ ] All critical scenarios working
- [ ] Acceptable performance
- [ ] [Business Stakeholder] approves
- [ ] [Technical Lead] approves

ACCEPTED KNOWN ISSUES:
- [Issue 1]: [Why it is acceptable]
- [Issue 2]: [Mitigation plan]
```

### 9.2 Simple Problem Log

| ID | Description | Priority | Responsible | Status | Target Date |
| --- | --- | --- | --- | --- | --- |
| 1 | [Problem description] | High | [Name] | In Progress | [Date] |
| 2 | [Problem description] | Low | [Name] | Planned | [Date] |

### 9.3 Go-Live Checklist

```
PROJECT: [Name]
GO-LIVE DATE: [Date]

CHECKLIST:
- [ ] Critical functionality tested and working
- [ ] Acceptable performance under normal load
- [ ] Key users trained and ready
- [ ] Support team informed and prepared
- [ ] Rollback plan documented and tested
- [ ] Business stakeholder approval: [Name / Date]
- [ ] Technical approval: [Name / Date]
- [ ] Project manager approval: [Name / Date]

DECISION: GO / NO-GO
APPROVED BY: [Name]    DATE: [Date]
```

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | 01-SEP-2025 | Rodney Ramirez | Initial version — minimalist approach |
|  |  |  |  |
