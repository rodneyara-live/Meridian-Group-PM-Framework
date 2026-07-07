---
type: document
for: FOR-008
project: "IE-3-2-3-1"
date_creacion: 2026-02-25
ultima_actualizacion: 2026-03-03
tags: [document, risks, issues, project, file, migration]
---

# FOR-008 — Risk and Issues Matrix

**Project:** File Migration
**Company:** [[Meridian Group]]
**PM:** [[Rodney-Ramirez]]
**Creation date:** 2026-02-25
**Last updated:** 2026-02-25

---

## 1. Definitions

| Term | Definition |
|---|---|
| **Risk** | Uncertain event that, if it occurs, may negatively affect the project |
| **Issue** | Problem that has already occurred and requires immediate action |
| **Blocker** | Issue that prevents progress on one or more project tasks |

---

## 2. Assessment Methodology

### Probability Classification

| Level | Criterion |
|---|---|
| **Low** | < 30% probability of occurrence |
| **Medium** | 30–70% probability of occurrence |
| **High** | > 70% probability of occurrence |

### Impact Classification

| Level | Criterion |
|---|---|
| **Low** | Minor impact on cost/time/quality (< 5% variation) |
| **Medium** | Moderate impact on cost/time/quality (5–15% variation) |
| **High** | Critical impact on cost/time/quality (> 15% variation) or impact on strategic objectives |

### Probability × Impact Matrix

|  | **Low Impact** | **Medium Impact** | **High Impact** |
|---|---|---|---|
| **High Probability** | 🟡 Monitor | 🟠 Mitigate | 🔴 Maximum Priority |
| **Medium Probability** | 🟢 Accept | 🟡 Monitor | 🟠 Mitigate |
| **Low Probability** | 🟢 Accept | 🟢 Accept | 🟡 Monitor |

---

## 3. Risk Register

| ID | Category | Risk Description | Probability | Impact | Level | Strategy | Responsible | Status |
|---|---|---|---|---|---|---|---|---|
| R-001 | Operational | Loss or misplacement of physical documents during inventory, packing, transfer and reception | Medium | High | 🟠 Mitigate | Mitigate | [[Elena-Torres]] | Active |
| R-002 | Operational | Interruption or delay in access to critical documents during and after transition | Medium | High | 🟠 Mitigate | Mitigate | [[Elena-Torres]] | Active |
| R-003 | External | Operational, financial or capacity failure of the external custody provider | Low | High | 🟡 Monitor | Mitigate | [[Tomas-Navarro]] | Active |
| R-004 | People | Active or passive resistance from affected personnel hindering the transition | Medium | Medium | 🟡 Monitor | Mitigate | [[Rodney-Ramirez]] | Active |
| R-005 | Security | Unauthorized access or exposure of confidential client information at provider facilities | Low | High | 🟡 Monitor | Mitigate | [[Carlos-Ruiz]] | Active |
| R-006 | Service Quality | Systematic non-compliance with provider response SLAs post-implementation | Medium | Medium | 🟡 Monitor | Mitigate | [[Rodney-Ramirez]] | Active |
| R-007 | Quality | Documents migrated without meeting HL scanning standard, compromising digital retrieval | High | High | 🔴 Maximum Priority | Mitigate | [[Elena-Torres]] | Active |
| R-008 | Decision | Delay in formal decision on destruction of purified acts generates uncontrolled paper accumulation | Medium | Medium | 🟡 Monitor | Mitigate | [[Rodney-Ramirez]] | Active |

---

## 4. Detailed Risk Analysis

### R-001: Document Loss During Transition

**Level:** 🟠 Mitigate | **Probability:** Medium | **Impact:** High

**Description:** Loss or misplacement of physical documents during the inventory, packing, transfer and reception process at provider facilities.

**Potential Causes:**
- Failures in the inventory and labeling process
- Errors in physical handling of documents
- Problems during transport (accidents, theft)
- Lack of rigorous delivery-receipt controls
- Mixing documents from different batches

**Consequences:**
- Regulatory non-compliance (documents required by the Superintendence of Banks)
- Loss of evidence in ongoing legal proceedings
- Inability to respond to audits
- Legal sanctions and reputational damage

**Mitigation Plan:**

*Preventive:*
- Implement double verification in inventory (two different people)
- Barcode or QR system for box tracking
- Photograph condition of critical documents before packing
- Contract custody and transport insurance
- Perform migration in small, controlled batches
- Pilot test with a non-critical batch before mass migration

*Corrective:*
- Delivery-receipt forms signed by both parties for each batch
- Immediate reconciliation process upon receiving each batch
- Search and recovery protocol for misplacement

*Contingency:*
- Maintain digital backup of high-criticality documents
- Plan for reconstruction of lost documents (request from issuing entities)

**Alert Indicators (Triggers):**
- Inventory count differences > 0.5%
- Delays in signing delivery-receipt forms
- Damage reports during transport

**Monitoring Responsible:** [[Elena-Torres]]
**Review Frequency:** Daily during physical migration

---

### R-002: Interruption of Access to Critical Documents

**Level:** 🟠 Mitigate | **Probability:** Medium | **Impact:** High

**Description:** Delays or temporary inability to access documents needed for daily operations or regulatory compliance during and after transition.

**Potential Causes:**
- Insufficient SLAs for Meridian Group's operational needs
- Provider logistics problems (personnel, transport)
- Inadequate search and indexing systems
- Lack of coordination on urgent requests
- Problems with the established consultation protocol

**Consequences:**
- Paralysis of critical operational processes
- Non-compliance with regulatory deadlines
- Impact on ongoing legal proceedings
- Fines for regulatory non-compliance

**Mitigation Plan:**

*Preventive:*
- Identify frequently consulted documents (last 6 months)
- Keep active documents in-house during transition period (3 months)
- Digitize critical documents before physical migration
- Establish strict SLAs with provider: urgent (2 h), priority (24 h), regular (48 h)
- Early warning system for documents nearing expiration

*Corrective:*
- Contractual penalties for SLA non-compliance
- Direct escalation channel with provider for urgencies

*Contingency:*
- Maintain digital copies of high-turnover documents
- Time buffer in planning processes that require documents

**Alert Indicators (Triggers):**
- SLA non-compliant in > 10% of requests
- Complaints from operational areas about response times
- Documents not located in > 1% of requests

**Monitoring Responsible:** [[Elena-Torres]]
**Review Frequency:** Weekly (first 6 months), monthly (from month 7)

---

### R-003: External Provider Failure

**Level:** 🟡 Monitor | **Probability:** Low | **Impact:** High

**Description:** The custody provider faces operational, financial or capacity problems that compromise service continuity.

**Potential Causes:**
- Provider financial problems
- Loss of facilities (fire, flood, natural disaster)
- Change of ownership or closure of operations
- Systematic non-compliance with contractual obligations

**Consequences:**
- Need to urgently repatriate files
- Prolonged interruption of document access
- Additional costs for migration to a new provider
- Risk of document loss during a provider crisis

**Mitigation Plan:**

*Preventive:*
- Financial and operational due diligence on provider before signing contract
- Verify certifications, insurance and facility audits
- Favorable exit contractual clauses for Meridian Group
- Quarterly review of provider's financial and operational health

*Corrective:*
- Right of unannounced inspection stipulated in contract
- Bank guarantees or performance bonds

*Contingency:*
- File repatriation plan (logistics, costs, timelines)
- Identify pre-qualified alternative providers
- Maintain updated inventory outside the primary provider's custody

**Alert Indicators (Triggers):**
- Changes in provider management or ownership
- SLA non-compliance for more than 2 consecutive months
- Negative news about their financial situation
- Loss of certifications or insurance

**Monitoring Responsible:** [[Tomas-Navarro]]
**Review Frequency:** Quarterly

---

### R-004: Personnel Resistance to Change

**Level:** 🟡 Monitor | **Probability:** Medium | **Impact:** Medium

**Description:** File department personnel generate active or passive resistance that hinders the successful project transition.

**Potential Causes:**
- Fear of job loss
- Lack of transparent communication about changes
- Uncertainty about future employment
- Inadequate handling of the organizational change process

**Consequences:**
- Insufficient cooperation in knowledge transfer
- Errors in documentation or processes during transition
- Negative work climate affecting other areas
- Labor contingencies or lawsuits

**Mitigation Plan:**

*Preventive:*
- Empathetic and transparent communication plan, coordinated with HR
- Strict compliance with applicable labor law
- Offer alternatives within Meridian Group (relocation) when possible
- Communication timing coordinated with project progress

*Corrective:*
- HR support throughout the transition process
- Recognition of the team's historical work
- Involve affected personnel constructively in the transition

*Contingency:*
- Reinforce supervision team during critical migration phase
- Preventive legal support for labor contingencies

**Alert Indicators (Triggers):**
- Increased absenteeism in the department
- Unusual errors in routine processes
- Formal complaints or grievances

**Monitoring Responsible:** [[Rodney-Ramirez]] / Meridian Group HR
**Review Frequency:** Continuous during announcement and transition period

---

### R-005: Information Security Breach

**Level:** 🟡 Monitor | **Probability:** Low | **Impact:** High

**Description:** Unauthorized access, loss or exposure of confidential client or company information contained in documents held by the provider.

**Potential Causes:**
- Insufficient physical security controls at provider facilities
- Inadequate access by provider personnel
- Lack of information segregation by client
- Physical security incident (theft, intrusion) or cyber incident

**Consequences:**
- Non-compliance with Law 172-13 on Personal Data Protection
- Sanctions from the Superintendence of Banks
- Lawsuits from affected clients
- Severe reputational damage and possible regulatory fines

**Mitigation Plan:**

*Preventive:*
- Audit of provider's physical security controls (perimeter, access, cameras, environmental controls)
- Require ISO 27001 certification or equivalent from provider
- Strict confidentiality and liability contractual clauses
- Physical segregation of Meridian Group files from other clients
- Restricted access control and background checks on provider personnel
- Audit log of all accesses to Meridian Group documents

*Corrective:*
- Periodic surprise compliance audits
- Immediate incident notification protocol
- Severe contractual penalties for breaches

*Contingency:*
- Civil liability insurance for security breaches
- Plan for notifying affected clients
- Immediate legal support for any confirmed breach

**Alert Indicators (Triggers):**
- Security incidents reported by the provider
- Negative findings in security audits
- Unauthorized accesses detected in logs

**Monitoring Responsible:** [[Carlos-Ruiz]]
**Review Frequency:** Quarterly + semi-annual surprise audits

---

### R-007: Documents Migrated Without HL Scanning Standard

**Level:** 🔴 Maximum Priority | **Probability:** High | **Impact:** High

**Description:** Physical documents are migrated to offsite archive without having met the high-quality (HL) scanning standard, making digital content retrieval impossible and nullifying the project's purpose.

**Potential Causes:**
- Time pressure to meet the March 30 deadline
- Lack of quality control prior to batch packing
- Previously scanned documents with low resolution or poor quality
- Personnel not verifying digitization status before transfer

**Consequences:**
- Documents physically at offsite archive without recoverable digital copy
- Need to repatriate documents for re-scanning (additional cost and time)
- Non-compliance with the strategic digitization objective
- Legal exposure for inability to present documents in legal proceedings

**Mitigation Plan:**

*Preventive:*
- Establish HL scanning as an **approval gate** before each batch: no verified scan, no batch ships
- Implement scanning quality control checklist per document
- Train the team on HL standard before starting Phase 3
- Random audit of 10% of documents per batch before dispatch

*Corrective:*
- Batch retention protocol if documents without HL scanning are detected
- Immediate re-scanning before continuing dispatch

*Contingency:*
- Priority re-scanning list if detected post-transfer

**Alert Indicators (Triggers):**
- Any document in a batch without confirmed HL scanning record
- Average scan time per document below standard

**Monitoring Responsible:** [[Elena-Torres]]
**Review Frequency:** Per batch (before each offsite archive dispatch)

---

### R-008: Delay in Decision on Destruction of Purified Acts

**Level:** 🟡 Monitor | **Probability:** Medium | **Impact:** Medium

**Description:** The destruction policy for notified and purified acts (e.g., mass garnishments) is not formalized in time, generating uncontrolled paper accumulation in the transitory file and compromising the space liberation objective.

**Potential Causes:**
- Lack of consensus between legal, operations and management areas
- Uncertainty about regulatory requirements for document destruction
- Absence of formal document retention policy

**Consequences:**
- The transitory file is not completely emptied in weekly dispatches
- Sustained growth of physical volume in office, contrary to the project objective
- Additional storage costs with offsite archive for excess volume

**Mitigation Plan:**

*Preventive:*
- Escalate decision to [[David-Carver]] and [[Carlos-Ruiz]] before 2026-04-04 (start of Phase 3)
- Prepare legal analysis of minimum retention requirements (Law 172-13, Superintendence of Banks)
- Define categories of destroyable vs. non-destroyable documents

*Corrective:*
- If the decision is delayed, still proceed with migration applying conservative policy (without destruction)

*Contingency:*
- Additional space at offsite archive to absorb overflow while decision is made

**Alert Indicators (Triggers):**
- As of 2026-04-01 without a formal decision made
- Transitory cabinets not emptied in weekly dispatch

**Monitoring Responsible:** [[Rodney-Ramirez]]
**Review Frequency:** Biweekly until formal decision is made

---

### R-006: Provider SLA Non-Compliance

**Level:** 🟡 Monitor | **Probability:** Medium | **Impact:** Medium

**Description:** The provider does not consistently meet agreed response times for document consultation, loan and return.

**Potential Causes:**
- Insufficient provider operational capacity
- High personnel turnover at the provider
- Inefficient search and indexing system
- Volume of requests higher than anticipated
- Inadequate request prioritization

**Consequences:**
- Impact on Meridian Group's daily operations
- Non-compliance with regulatory deadlines
- Frustration of internal users
- Questioning of the outsourcing decision

**Mitigation Plan:**

*Preventive:*
- Clear and measurable SLA definition by request type:
  - Urgent: 2 hours
  - Priority: 24 hours
  - Regular: 48 hours
- Validate provider's operational capacity before signing contract
- Ticket system with real-time tracking
- Contractual penalties for non-compliance (invoice discounts)
- Monthly performance review with provider

*Corrective:*
- Automatic alerts when an SLA is at risk
- Immediate escalation to provider management
- Mandatory continuous improvement plan if non-compliance exceeds 10%

*Contingency:*
- Termination clause for systematic non-compliance
- Critical file repatriation plan if the problem persists
- Temporarily keep high-turnover documents in-house

**Alert Indicators (Triggers):**
- SLA non-compliance > 10% monthly
- Increasing trend in response times
- Complaints from internal users about delivery times

**Monitoring Responsible:** [[Rodney-Ramirez]]
**Review Frequency:** Weekly (first 3 months), biweekly (from month 4)

---

## 5. Active Issues Register

| ID | Description | Type | Severity | Opening Date | Impact | Immediate Action | Responsible | Deadline | Status |
|---|---|---|---|---|---|---|---|---|---|
| — | No active issues as of 2026-02-25 | — | — | — | — | — | — | — | — |

---

## 6. Resolved Issues History

| ID | Description | Severity | Opening Date | Resolution Date | Solution Applied |
|---|---|---|---|---|---|
| I-001 | Provider commercial proposal outdated | 🟡 Medium | 2026-01-30 | 2026-02-25 | Bruno Torres managed updated commercial proposal with provider |

---

## 7. Escalation

| Time without resolution | Escalate to |
|---|---|
| > 24h without action (Critical) | [[David-Carver]] — Executive Sponsor |
| > 48h without action (High) | [[Tomas-Navarro]] — Sponsor |
| > 5 days without action (Medium) | [[Rodney-Ramirez]] documents and decides |

---

## 8. Next Review

- **Review frequency:** Weekly (during active migration phases), biweekly (planning and stabilization phases)
- **Next scheduled review:** 2026-03-10
- **Update responsible:** [[Rodney-Ramirez]]

---

## 9. Risk Dashboard (Executive Summary)

| Criticality | Quantity | Risks |
|---|---|---|
| 🔴 Maximum Priority | 1 | R-007 |
| 🟠 Mitigate | 2 | R-001, R-002 |
| 🟡 Monitor | 5 | R-003, R-004, R-005, R-006, R-008 |
| 🟢 Accept | 0 | — |

**Immediate Actions Required:**
- **R-007 (NEW — CRITICAL):** Define HL scanning quality control checklist and establish it as a mandatory gate before first offsite archive dispatch — before 2026-03-14
- **R-001 and R-002:** Design detailed gradual migration protocol with batch controls before starting Phase 2
- **R-003:** Complete provider due diligence before signing final contract
- **R-008 (NEW):** Escalate decision on act destruction to management before 2026-04-04
- **All:** Include mitigation clauses in the contract with the provider

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | 2026-01-30 | [[Rodney-Ramirez]] | Initial version — 8 risks (offsite archive project, confidential) |
| 2.0 | 2026-02-25 | [[Rodney-Ramirez]] | Reshaping: project becomes "File Migration", confidentiality and cost overrun risks removed (excluded from charter scope). 6 active risks. |
| 3.0 | 2026-03-03 | [[Rodney-Ramirez]] | Formal kickoff: R-007 added (HL scanning — Maximum Priority) and R-008 (delay in act destruction decision). Total: 8 active risks. |
