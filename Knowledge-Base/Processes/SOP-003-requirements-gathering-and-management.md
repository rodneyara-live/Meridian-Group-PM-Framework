# SOP-003 — Requirements Gathering and Management

**Simple and practical methodology for capturing, documenting, and managing requirements for technology projects at Meridian Group**

---

## 1. Purpose and Scope

### 1.1 Purpose

Establish a simple and practical methodology for capturing, documenting, and managing requirements for technology projects at Meridian Group, especially AI, automation, and financial operations systems projects.

### 1.2 Scope

This SOP applies to all strategic portfolio projects requiring technology development, with special emphasis on:

- Artificial intelligence projects (SLM, virtual agents)
- Collections process automation
- System integrations (Ledger-9, Meridian Group Digital, Wolkvox)
- Judicial management modules
- Scoring platforms

### 1.3 References

- FOR-001: Project Sheet
- FOR-002: Project Charter
- FOR-003: Requirements Matrix
- SOP-001: General Project Management Methodology
- SOP-002: Project Initiation Process

---

## 2. User Stories

### 2.1 Basic Structure

- As a [role at Meridian Group]
- I want [what I need]
- So that [what benefit I get]

### 2.2 Essential Acceptance Criteria

Each Story must answer at least these 3 questions:

- **What exactly must it do?** — Specific function it must fulfill
- **How do we know it works well?** — Measurable success criterion
- **When is it done?** — Clear completion condition

### 2.3 User Story Template

```
Story [ID]: [Short title]

As a [role]
I want [functionality]
So that [benefit]

Must do:
- [ ] Condition 1: Clear description
- [ ] Condition 2: Expected behavior
- [ ] Condition 3: Required integration

Done when:
- [ ] Works in test environment
- [ ] End user validates
- [ ] Basic documentation exists

Priority: High / Medium / Low
Effort: XS (hours) / S (1 day) / M (2–3 days) / L (1 week) / XL (split)
Responsible: [Sponsor name]
```

---

## 3. Gathering Techniques by Stakeholder

### 3.1 Area Managers

**Session agenda**:
1. **Current problem**: What does not work today?
2. **Ideal vision**: How should it work?
3. **Priorities**: What is most important?
4. **Success**: How do we measure it worked?

**Expected outputs**:
- 3–5 clear objectives
- List of priority problems
- Definition of success
- Important constraints

### 3.2 Operational Users

**Workshop methodology**:
1. **Quick mapping**: Draw current process
2. **Problems**: Where does everything get complicated?
3. **Ideas**: What would help them most?
4. **Validation**: Review proposals

**Expected outputs**:
- Simple process diagram
- Top 3 operational problems
- Desired functionalities
- Basic use cases

### 3.3 Technical Team

**Feasibility session**:
1. **Review requirements**: Can it be done?
2. **Identify dependencies**: What do we need?
3. **Estimate effort**: How long does it take?

**Expected outputs**:
- Feasibility validation
- Critical dependencies
- Time estimate
- Main technical risks

---

## 4. Prioritization — MoSCoW Model

### Must Have (Critical)

Without this the project is useless. Includes regulatory requirements and blocking integrations.

*Example: "The virtual agent must be able to query history in Ledger-9"*

### Should Have (Important)

Significant improvement, eliminates manual work, or generates measurable savings.

*Example: "The system must generate automatic reports"*

### Could Have (Desirable)

Adds value but is not critical: interface improvements, analytical features.

*Example: "Could include analysis of best contact time"*

### Won't Have (Out of Scope)

For future versions, too complex for this phase, or without significant value.

*Example: "Does not include integration with external systems"*

---

## 5. Special Cases by Project Type

### 5.1 AI Projects (SLM, Virtual Agents)

**Key questions**:
- What data do we have available?
- What personality should the agent have?
- When should it transfer to a human?
- How do we measure if it works well?

**Typical requirements**:
- Access to customer databases
- Definition of conversation flows
- Escalation cases
- Quality metrics

### 5.2 Integration Projects

**Key questions**:
- What systems are being connected?
- What data is shared?
- How do we handle errors?
- Who is responsible for each data point?

**Typical requirements**:
- Field mapping between systems
- Connection error handling
- Data synchronization
- Change traceability

### 5.3 Scoring Projects

**Key questions**:
- What variables influence the score?
- How is the result interpreted?
- How often is it updated?
- Who can view the scores?

**Typical requirements**:
- Definition of input variables
- Score calculation logic
- Update frequency
- Access permissions

---

## 6. Minimum Documentation

### 6.1 Requirements Matrix (FOR-003)

| ID | User Story | Must/Should/Could/Won't | Effort | Sponsor | Status |
| --- | --- | --- | --- | --- | --- |
| REQ-01 | As an agent I want... | Must | M (2–3 days) | [Name] | Defined |
| REQ-02 | As a supervisor... | Should | S (1 day) | [Name] | In analysis |

**Statuses**:
- **Defined**: Clear and accepted requirement
- **In analysis**: Technical team evaluating
- **Approved**: Ready for development
- **Developing**: Under construction
- **Completed**: Finished and validated

### 6.2 Change Management

**For minor changes (<20% of effort)**:
- Email to sponsor with justification
- Matrix update
- Team notification

**For major changes (>20% of effort)**:
- Formal request (FOR-009)
- Impact evaluation
- Strategic Committee approval

---

## 7. Roles and Responsibilities

### 7.1 Project Manager

- Facilitate gathering sessions
- Keep the requirements matrix updated
- Coordinate validations with sponsors
- Escalate important changes

### 7.2 Project Sponsors

- Participate in initial sessions
- Validate developed requirements
- Approve minor changes
- Provide business context

### 7.3 End Users

- Participate in initial workshop (1 hour)
- Test functionalities (30 min weekly)
- Provide feedback on developments
- Validate expectations are met

### 7.4 Technical Team

- Validate technical feasibility
- Estimate development effort
- Identify dependencies
- Propose efficient alternatives

---

## 8. Process Flow

```
1. Initial session
   ├── Key stakeholders present
   ├── Problems and objectives clear
   └── Initial user stories

2. Technical analysis
   ├── Feasibility confirmed
   ├── Effort estimated
   └── Dependencies identified

3. Prioritization
   ├── MoSCoW applied
   ├── Development order defined
   └── Matrix updated

4. Continuous validation
   ├── Functionality demos
   ├── Feedback incorporated
   └── Minor adjustments applied

5. Requirements closure
   ├── All stories completed
   ├── Sponsor validates fulfillment
   └── Final documentation
```

---

## 9. Complete Requirements Verification

Before starting development, verify we have:

- [ ] **Clear problem**: We know what we are solving
- [ ] **User identified**: We know who will use this
- [ ] **Benefit defined**: We understand the value it provides
- [ ] **Acceptance criteria**: We can verify it works
- [ ] **Priority assigned**: We know what to do first
- [ ] **Effort estimated**: We know how long it takes
- [ ] **Dependencies identified**: We know what we need
- [ ] **Responsible assigned**: Someone is in charge
- [ ] **Sponsor validated**: The area responsible approved
- [ ] **Technically feasible**: The team confirmed it can be done

---

## Version Control

| Version | Date | Author | Changes |
| --- | --- | --- | --- |
| 1.0 | 10-AUG-2025 | Rodney Ramirez | Initial version |
|  |  |  |  |
