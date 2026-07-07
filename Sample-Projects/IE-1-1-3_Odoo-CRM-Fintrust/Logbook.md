---
type: log
project: "IE-1-1-3"
project_name: "Odoo CRM — Fintrust"
company: "[[Fintrust]]"
priority: P1
completion: 100%
baseline_date: 2026-02-13
planned_end_date: 2026-03-28
revised_end_date: 2026-06-30
close_date: 2026-06-30
pm: "[[Rodney-Ramirez]]"
status: " In showcase"
last_event: "2026-06-30 — Project closed. CRM delivered, configured and in production. Final cosmetics approved. CRM evolution passes to Fintrust's organization."
confidentiality: "C1"
tags: [logbook]
---
# Log — Odoo CRM — Fintrust

> Reverse chronological record (newest first). Each entry captures the status at a given point in time.

## Current Status
*(updated: 2026-06-30)*

**Project closed.** Odoo CRM delivered, configured and in production. Milestones 1 and 2 completed; final cosmetic adjustments approved (23-jun-2026). CRM evolution and Milestone 3 (transactional module) become the responsibility of Fintrust's organization. See [[Documents/closing-record_2026-06-30|Closure Report]].

---

## 2026-06-30 — Project closed; CRM passes to Fintrust administration

**Status:**  In showcase · **Completion:** 100%

**Executive summary:** [[Rodney-Ramirez]] declares formal closure. CRM delivered and in production. Future developments on Odoo CRM at Fintrust will be managed directly by Fintrust's organization, outside Meridian Group' portfolio.

**Documents:** [[Documents/closing-record_2026-06-30|Closure Report 2026-06-30]]

---

## 2026-06-08 — Cosmetics delivered; project closing; milestone model decision

**Status:** In progress · **Completion:** 98%

**Executive summary:** [[Gustavo-Novak]] completed the CRM cosmetic modifications. [[Rodney-Ramirez]] reviews and approves closure this week. Future Odoo projects will be milestone-based.

**What happened:**
- [[Gustavo-Novak]] left notes on the cosmetic modifications requested by [[Hugo-Pacheco]]; delivery ready for review.
- Once approved, the project closes and payment proceeds.
- [[Elena-Torres]] and [[Rodney-Ramirez]] agreed that future projects with [[Sergio-Mendoza]] / [[Gustavo-Novak]] will be quoted by milestones, not by hours — lesson learned from the accounting project where a large hour load was generated.
- Next work identified: [[Gustavo-Novak]] must do significant work for [[Fintrust]] to use Odoo as CRM and daily operational database (decoupling from Ledger-9).

**Action items:**
- [x] [[Rodney-Ramirez]]: Review [[Gustavo-Novak]]' cosmetic modifications delivery and approve closure and payment of CRM Fintrust project 📅 2026-06-09 #IE-1-1-3 #resp/Rodney-Ramirez #action ✅ 2026-06-23
- [x] [[Rodney-Ramirez]]: Define with [[Sergio-Mendoza]] and [[Gustavo-Novak]] the Ledger-9 Odoo decoupling work so [[Fintrust]] operates Odoo as CRM and daily database #IE-1-1-3 #resp/Rodney-Ramirez #action 📅 2026-06-11 ✅ 2026-06-23

**Related minutes:** [[Cadences/Madrugador-Tactico/Minutes/20260608-Madrugador-Tactico]]

---

## 2026-05-29 — UAT Milestone 1 closure; Milestone 2 — Bonita endpoints pending to Sofia

**Status:** In progress · **Completion:** 96%

**Executive summary:** Final review of UAT observations with [[Hugo-Pacheco]] and [[Sergio-Mendoza]]. Most observations were discarded or already corrected. 3 minor corrections remain for Sergio. Milestone 2 progresses: Sergio delivers Bonita endpoint documentation to [[Sofia-Vargas]] this week.

**What happened:**
- [[Hugo-Pacheco]] reviewed his UAT list marked in red. Resolved: locations, negative phone as primary, multiple prefixes per country.
- Pending correction (Sergio): (1) state change history with timestamp and user; (2) "Add" option in product/case navigation tab — it is for viewing only, not adding; (3) automatic case numbering upon creation.
- Milestone 1 structurally complete; data can be added to Odoo.
- Milestone 2: [[Sergio-Mendoza]] developed endpoints for Bonita integration (received from [[Rodrigo-Villalba]]). Documentation to be delivered to [[Sofia-Vargas]] this week (or before Sergio's trip the following week).
- Milestone 3 (transactional part) — scope to be defined by [[Alex-Carver]], not started.
- [[Alex-Carver]] participated briefly.

**Action items:**
- [x] [[Sergio-Mendoza]]: Fix pending UAT observations: state history with timestamp/user, navigation tab UI, automatic case numbering #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-06-06 ✅ 2026-06-01
- [x] [[Sergio-Mendoza]]: Pass Bonita endpoints documentation to [[Sofia-Vargas]] (Milestone 2) — before his trip #IE-1-1-3 #resp/Sergio-Mendoza #action 📅 2026-06-06 ✅ 2026-06-01
- [x] [[Rodney-Ramirez]]: Coordinate with [[Sofia-Vargas]] check of Bonita Odoo CRM endpoints #IE-1-1-3 #resp/Rodney-Ramirez #action 📅 2026-06-06 ✅ 2026-06-01

**Related minutes:** [[Minutes/20260529-CRM-Odoo-Fintrust-UAT-Milestone1-2-Closure]]

---

## 2026-05-19 — Madrugador: model in production; Erick's interface improvements pending for next week

**Status:** In progress · **Completion:** 93%

**Executive summary:** The Fintrust CRM model went into production on 05/18. Pending: Hugo-Pacheco' interface improvement list, to be tackled next week post-accounting.

**What happened:**
- Production deployment completed on the night of 05/18.
- [[Hugo-Pacheco]] has a list of interface improvements raised — [[Rodney-Ramirez]] will address them next week when the team clears the accounting workload.

**Related minutes:** [[Cadences/Madrugador-Operativo/Minutes/2026-05-19-martes]]

---

## 2026-05-07 — Orchestrator State Architecture resolved (Milestone 2); go-live blocker: Erick has not responded to corrections set

**Status:** In progress · **Completion:** 92%

**Executive summary:** Technical architecture session with [[Carlos-Ruiz]], [[Alex-Carver]], [[Sergio-Mendoza]] and [[Nicolas-Mercado]]. "Orchestrator State" architecture defined and classified as Milestone 2. **Active go-live blocker:** [[Hugo-Pacheco]] has not confirmed whether his corrections set contains critical findings. This point is relevant for the weekly report.

**What happened:**
- **Orchestrator State architecture defined:** Case (parent) list of Processes by intervenor (main debtor, co-debtor, guarantor, spouses) Bonita State per process. New table in Ledger-9 with `individuo` key linked to the case + substate per process. [[Sergio-Mendoza]] adjusts Odoo to receive this structure. Does not modify existing structure — it is additive.
- **Integration:** Bonita updates individual processes (not the parent case). Ledger-9 stores substates. Odoo CRM displays by case and by debtor.
- **Orchestrator State = Milestone 2, outside the MVP.** Euris+Sergio modeling session after 15-may (Sergio committed to accounting migration until that date). Alex can already use the CRM as is.
- **FE Fintrust (tangential IE-1-1-4):** [[Sergio-Mendoza]] identified and resolved Andira Partners's technical debt issue (code coupled to the previous vendor). Needs separate staging requests approval from [[Alex-Carver]].

**Active blockers:**
-  **[[Hugo-Pacheco]]: no response on critical findings in corrections set** blocker for formal MVP closure. Urgent escalation.

**Next steps:**
- [ ] [[Rodney-Ramirez]]: Escalate to [[Hugo-Pacheco]] to obtain confirmation of critical findings 📅 2026-05-08 
- [ ] [[Hugo-Pacheco]]: Confirm whether there are critical findings in the corrections set 📅 2026-05-08 
- [ ] [[Sergio-Mendoza]]: Resolve critical findings if any 📅 2026-05-09
- [ ] [[Alex-Carver]]: Approve separate staging instance for FE testing with GTI 📅 2026-05-08

**Related minutes:** [[Minutes/20260507-CRM-Fintrust-Orchestrator-Architecture-Status]]

---

## 2026-05-05 — Madrugador: survey almost ready; orchestrator-state field blocking; meeting today afternoon

**Status:** In progress · **Completion:** 90%

**Executive summary:** [[Rodney-Ramirez]] confirmed the survey is practically ready. The only blocker is the missing orchestrator-state field in the DB model; technical session this afternoon to resolve it. Go Live week of 11-may.

**What happened:**
- CRM survey practically completed.
- Technical session for the orchestrator-state field called for this afternoon with [[Sergio-Mendoza]] and [[Elena-Torres]].

**Active blockers:**
-  "Orchestrator state" field missing in DB model session this afternoon

**Next steps:**
- [ ] [[Rodney-Ramirez]] / [[Sergio-Mendoza]]: Resolve orchestrator-state field in Odoo CRM DB model 📅 2026-05-05 

**Related minutes:** [[Cadences/Madrugador-Operativo/Minutes/20260505-Madrugador-Operativo-Tactico]]

---

## 2026-05-01 — Madrugador: final adjustments; pending Horizon meeting for architecture early next week

**Status:** In progress · **Completion:** 90%

**Executive summary:** [[Rodney-Ramirez]] confirmed the project is in its final adjustments. Remains to schedule a Horizon meeting with [[Elena-Torres]] to incorporate the architecture point discussed in the last session — to be scheduled early next week.

---

## 2026-04-29 — UAT Milestone 1 complete; finding: missing orchestrator-state field; technical session week of 5-may

**Status:** In progress · **Completion:** 90%

**Executive summary:** [[Hugo-Pacheco]] completed and presented the UAT for Milestone 1. System viable for the MVP with minor observations. New structural finding: [[Sergio-Mendoza]]'s model does not include an "orchestrator state" field for the BonitaCRM integration. [[Rodney-Ramirez]] calls a technical session the week of May 5 to resolve before Go Live.

**What happened:**
- [[Hugo-Pacheco]] presented a full walkthrough of the UAT file with screen sharing. Conclusion: the system can launch at the MVP level.
- [[Rodney-Ramirez]] clarified the architecture: the CRM is a data repository; Bonita orchestrates judicial processes. Several of Erick's observations about the garnishment and judicial processes module were dismissed as blockers because they are designed to be operated by Bonita, not by humans.
- [[Elena-Torres]] identified that the current model lacks an "orchestrator state" field with relational correspondence BonitaCRM. Without this field, Bonita has nowhere to write in Odoo. Agreed design: master equivalence table, coupled initially and decouplable in the future.
- Erick's minor observations still valid: default country (DR), technical error in duplicate phone message, prefix 809/829/849, auto-generation of case number, visibility of co-debtor/guarantor links.

**Active blockers:**
- "Orchestrator state" field missing in Odoo model requires urgent technical session

**Next steps:**
- [ ] [[Hugo-Pacheco]]: Review and prioritize UAT findings marking those that apply with the Bonita-orchestrator model 📅 2026-04-30
- [ ] [[Rodney-Ramirez]]: Call technical session with [[Sergio-Mendoza]], [[Elena-Torres]] and [[Carlos-Ruiz]] for orchestrator state field 📅 2026-05-05

**Related minutes:** [[Minutes/20260429-CRM-Fintrust-UAT-Milestone1-Review]]

---
## 2026-04-28 — Madrugador: Erick active testing; review tomorrow; Go Live Friday if OK

**Status:** In progress · **Completion:** 85%

**Executive summary:** Hugo Pacheco in active UAT; if the Apr-29 review is positive, Go Live proceeds on Friday May 1.

**What happened:**
[[Hugo-Pacheco]] in active testing state. Results review tomorrow April 29. If the latest modifications are approved **Go Live on Friday May 1**. [[Rodney-Ramirez]] will follow up today.

**Active blockers:**
- None.

**Next steps:**
- [ ] [[Rodney-Ramirez]]: Confirm with Erick test results 📅 2026-04-28
- [ ] Final review and Go Live decision 📅 2026-04-29

**Related minutes:** [[Cadences/Madrugador-Operativo/Minutes/20260428-Madrugador-Operativo]]

---
## 2026-04-27 — Madrugador: 50% UAT, no technical dependencies towards Corvant Systems; final review Wednesday

**Status:** In progress · **Completion:** 85%

**Executive summary:** In the Tactical Madrugador, [[Rodney-Ramirez]] confirmed that [[Hugo-Pacheco]] is at 50% UAT and finishes today-tomorrow. There are no open technical dependencies from Meridian Group' side towards Corvant Systems.

**What happened:**
- [[Hugo-Pacheco]] at 50% UAT with his team; finishes 100% today and tomorrow
- No pending technical dependencies from Meridian Group towards [[Partners/Corvant Systems]]
- Final review scheduled: Wednesday April 29

**Next steps:**
- [ ] [[Hugo-Pacheco]]: Complete CRM Fintrust UAT at 100% 📅 2026-04-28
- [ ] [[Rodney-Ramirez]]: Final CRM Fintrust review with [[Hugo-Pacheco]] 📅 2026-04-29

**Related minutes:** [[Cadences/Madrugador-Tactico/Minutes/20260427-Madrugador-Tactico]]

---


## 2026-04-21 — Corrections uploaded by Sergio; checkpoint tomorrow 22-apr

**Status:** In progress · **Completion:** 80%

**Executive summary:** [[Rodney-Ramirez]] reported in the Operational Madrugador that [[Sergio-Mendoza]] uploaded the latest modifications requested by [[Hugo-Pacheco]] and [[Carlos-Ruiz]]. Checkpoint tomorrow to review those corrections.

**What happened:**
- [[Rodney-Ramirez]] covered the project status given the absence of Sergio and Erick from the meeting (invitation sent last night).
- [[Sergio-Mendoza]] uploaded the latest corrections to the observations from [[Hugo-Pacheco]] and [[Carlos-Ruiz]].
- Review checkpoint scheduled for tomorrow 22-apr.

**Active blockers:**
- None reported.

**Next steps:**
- [ ] [[Hugo-Pacheco]] + [[Carlos-Ruiz]]: Review corrections uploaded by Sergio at the Apr-22 checkpoint 📅 2026-04-22
- [ ] [[Rodney-Ramirez]]: Confirm Sergio and Erick attendance at the checkpoint 📅 2026-04-21

**Related minutes:** [[Cadences/Madrugador-Operativo/Minutes/2026-04-21-martes]]

---

## 2026-04-15 — Follow-up: activities doc corrected; Sergio maps sub-states and roles

**Status:** In progress · **Completion:** 80%

**Executive summary:** Follow-up meeting with [[Sergio-Mendoza]], [[Hugo-Pacheco]] and [[Carlos-Ruiz]]. It was identified that the activities/dispositions document sent by [[Carlos-Ruiz]] only included state-changing activities — agreed to update it with ALL activities (access, messages, procedural acts) plus a separate tab. [[Carlos-Ruiz]] clarified the complete payment commitment flow logic. [[Sergio-Mendoza]] will map sub-states and create the 2 missing roles; [[Hugo-Pacheco]] needs active access to validate in parallel.

**What happened:**
- [[Sergio-Mendoza]] already has the new activity/notes button active in the CRM; date and user auto-fill.
- Finding: the activities document that [[Carlos-Ruiz]] sent contained only state-changing ones. [[Sergio-Mendoza]] and [[Hugo-Pacheco]] need ALL activities (file access, messages, procedural acts from Ledger-9 Judicial, plus state-changing dispositions). Agreement: [[Carlos-Ruiz]] updates the document with a separate tab.
- [[Carlos-Ruiz]] explained the payment commitment flow: `commits` = date + amount; if fulfilled state changes; if breached state changes + reassigns manager + creates follow-up event. Automated triggers (JSONs) validated by [[Carlos-Ruiz]] and Sofia via Postman.
- Milestone 1 roles: only 3 roles (Supervisor + 2). [[Sergio-Mendoza]] has 1 ready; will create the other 2 and pass user list to [[Hugo-Pacheco]].
- Sub-states: [[Sergio-Mendoza]] will map state/substate transition visual layer for [[Hugo-Pacheco]], JSONs Postman for [[Carlos-Ruiz]] and Ana. [[Rodney-Ramirez]] confirmed this is a Milestone 1 finding.

**Active blockers:**
- None.

**Next steps:**
- [ ] [[Carlos-Ruiz]]: Update activities document including ALL activities with separate tab for non-state-changing ones 📅 2026-04-18
- [ ] [[Sergio-Mendoza]]: Map sub-states and upload version for validation (visual: Erick; JSONs Postman: Carlos Ruiz + Ana) 📅 2026-04-18
- [ ] [[Sergio-Mendoza]]: Create the 2 missing roles and pass user list to [[Hugo-Pacheco]] 📅 2026-04-18

**Related minutes:** [[Minutes/20260415_Odoo-CRM-Fintrust-Follow-up]]

---

## 2026-03-30 — UAT Milestone 2 follow-up: BonitaOdoo state architecture defined; corrections by 03/31

**Status:** In progress · **Completion:** 80%

**Executive summary:** [[Hugo-Pacheco]] presented findings from his UAT review of Milestone 2. The critical finding — absence of state/sub-state logic in the CRM — was resolved with a clear architectural decision: Bonita does not modify the CRM state; a separate "Fintrust state" field is created that Bonita updates. [[Sergio-Mendoza]] confirms he finishes corrections on 03/31 and uploads the corrected version; [[Hugo-Pacheco]] and [[Carlos-Ruiz]] will do final review on 04/03.

**What happened:**
In the March 30 follow-up meeting, [[Hugo-Pacheco]] presented the findings from his Milestone 2 review. Critical finding: the CRM has no business logic behind states — it does not know what to do when a case is active or inactive (does not deactivate turbo collection, messaging or management). Sub-states are also not implemented with the state↔substate connection logic.

[[Carlos-Ruiz]] and [[Rodney-Ramirez]] clarified the definitive architecture: three layers are needed: (1) Ledger-9 state, (2) Ledger-9 substate, and (3) legal process state in Bonita. Integration works like this: the CRM informs Bonita of the state/substate change, and Bonita stops or reactivates processes and returns its own legal process state. A new field is created in Odoo ("Fintrust state") for Bonita to update, without touching the collection state. This architecture is already prepared for future integrations (banks, Peru CRM).

[[Nicolas-Mercado]] had already passed the Ledger-9 states/substates to [[Sergio-Mendoza]] on Saturday. [[Rodney-Ramirez]] committed to passing the current Bonita states (from user stories). [[Sergio-Mendoza]] has most corrections done, finishes them tomorrow (03/31) and uploads them. [[Carlos-Ruiz]] asked that [[Hugo-Pacheco]] do a comprehensive final review once uploaded, and anything additional be communicated promptly.

Other non-critical findings identified: duplicate debtors without control, editable log/dispositions (should be immutable log with auto-captured date/time), access control for guarantor/co-debtor linking by hierarchy. All cases are loaded by batch; no individual manual registration process exists.

**Active blockers:**
- State/substate logic pending implementation — architecture defined, development by [[Sergio-Mendoza]] 📅 2026-03-31

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Finish corrections from [[Hugo-Pacheco]]' observations and upload corrected version 📅 2026-03-31 
- [ ] [[Rodney-Ramirez]]: Pass current Bonita states to [[Sergio-Mendoza]] (from user stories) 📅 2026-03-30 
- [ ] [[Hugo-Pacheco]] + [[Carlos-Ruiz]]: Comprehensive final review of CRM post-corrections 📅 2026-04-03
- [ ] [[Rodney-Ramirez]]: Schedule Milestone 2 follow-up meeting post-corrections 📅 2026-04-02

**Related minutes:** [[Minutes/20260330-CRM-Odoo-Fintrust-UAT-Milestone2-Follow-up]]

---

## 2026-03-30 — Madrugador: decision not to hire sub-developer; regrouping today

**Status:** In progress · **Completion:** 75%

**Executive summary:** [[Elena-Torres]] made the definitive decision not to hire a sub-developer under [[Sergio-Mendoza]]: at the current project stage, bringing someone new would delay more than it would help. [[Sergio-Mendoza]] reports Milestone 2 ready from his side; still pending applying [[Hugo-Pacheco]]' observations from Milestone 1 UAT. Today the team regroups to re-establish tasks, define the milestone billing scheme and set dates for the April accounting migration phase.

**What happened:**
In the March 30 Madrugador, [[Carlos-Ruiz]] raised the possibility of bringing someone under Sergio to accelerate Odoo projects in parallel (CRM + accounting). [[Elena-Torres]] responded that at the current state he did not consider it viable: they are already at a very advanced point and adding someone new would generate more noise than speed. He confirmed he asked Sergio to prioritize CRM Milestone 2, upload improvements based on Erick's observations, and then resume accounting. [[Carlos-Ruiz]] requested that all Odoo project plans be updated with clear commitment dates. [[Rodney-Ramirez]] cited two critical dates: QuickBooks license renewal (data available for consultation, manageable) and **May 15** for active electronic invoicing in all companies.

**Next steps:**
- [ ] [[Rodney-Ramirez]]: Regroup with Sergio — re-establish Milestone 2 tasks, define milestone billing scheme and set dates 📅 2026-03-30
- [ ] [[Rodney-Ramirez]] + [[Elena-Torres]] + [[Carlos-Ruiz]]: Update plans for all Odoo projects with commitment dates 📅 2026-04-01

**Related minutes:** [[Projects/Madrugador-Tactico/Minutes/20260330-Madrugador-Tactico]]

---

---
## 2026-03-17 — Erick begins formal Milestone 1 certification; module 1 summary by end of day

**Status:** In progress · **Completion:** 75%

> **Executive summary:** [[Hugo-Pacheco]] confirmed in the March 17 Operational Madrugador that today he formally begins the certification of Milestone 1 areas, backed by the good work delivered by [[Sergio-Mendoza]]. By end of day he will send a summary of the first certified module to continue with necessary configurations.

**What happened:**
In the March 17 Operational Madrugador, [[Hugo-Pacheco]] reported that yesterday (03/16) they started testing superficially due to existing commitments, but early today he began formally certifying certain areas. He highlighted that [[Sergio-Mendoza]] did a good job. By end of day he will have the summary of the first module to continue with the necessary configurations. The test environment set up by [[Sergio-Mendoza]] on 03/16 is operational and Milestone 1 UAT is in full execution.

**Active blockers:**
- *(None)*

**Next steps:**
- [ ] [[Hugo-Pacheco]]: Send certification summary of module 1 (UAT Milestone 1) to [[Rodney-Ramirez]] 📅 2026-03-17 
- [ ] [[Hugo-Pacheco]]: Complete full UAT of Milestone 1 📅 2026-03-20
- [ ] [[Sofia-Vargas]]: Complete Milestone 1 quality verifications 📅 2026-03-20
- [ ] [[Sergio-Mendoza]]: Provide technical support during Milestone 1 testing 📅 2026-03-20

**Related minutes:** [[Minutes/20260317-Madrugador-Operativo]]

---

## 2026-03-16 — Test environment ready; Milestone 1 coordination starts today with Erick, Sergio and Ana

**Status:** In progress · **Completion:** 75%

> **Executive summary:** [[Sergio-Mendoza]] managed to set up the test instance with all Milestone 1 modules; today [[Hugo-Pacheco]], [[Sofia-Vargas]] and [[Sergio-Mendoza]] meet in the afternoon to coordinate test execution and quality verifications.

**What happened:**
In the March 16 Tactical Madrugador, [[Rodney-Ramirez]] confirmed that [[Sergio-Mendoza]] was finally able to set up the test instance and upload all Milestone 1 modules. With this, the test coordination meeting between [[Sergio-Mendoza]], [[Hugo-Pacheco]] and [[Sofia-Vargas]] is scheduled for this afternoon to formally begin UAT testing and Milestone 1 quality verifications. Additionally, it was mentioned that [[IE-1-1-3-2_Odoo-CRM-Meridian-Pay]] could be temporarily frozen to focus available resources on multi-company accounting, which is urgent in the coming weeks.

**Active blockers:**
- *(None)*

**Next steps:**
- [ ] [[Hugo-Pacheco]]: Execute Milestone 1 UAT tests in test instance 📅 2026-03-20
- [ ] [[Sofia-Vargas]]: Execute Milestone 1 quality verifications 📅 2026-03-20
- [ ] [[Sergio-Mendoza]]: Provide technical support during Milestone 1 testing 📅 2026-03-20

**Related minutes:** [[Minutes/20260316-Madrugador-Tactico]]

---

## 2026-03-04 — Resumption checkpoint: instance ready tonight; Milestone 1 UAT starts tomorrow

**Status:** In progress · **Completion:** 75%

> **Executive summary:** Checkpoint with the full team confirms that [[Sergio-Mendoza]] delivers the test instance tonight and [[Hugo-Pacheco]] starts Milestone 1 UAT tomorrow (05/03); [[Sofia-Vargas]] and [[Nicolas-Mercado]] will audit the code via GitHub.

**What happened:**
In a short checkpoint with the full team ([[Hugo-Pacheco]], [[Sergio-Mendoza]], [[Sofia-Vargas]], [[Nicolas-Mercado]], [[Elena-Torres]], [[David-Carver]], [[Carlos-Ruiz]]), [[Sergio-Mendoza]] confirmed he is on step 3 of the setup and will have the instance configured with Milestone 1 modules tonight. [[Elena-Torres]] confirmed that the use cases for UAT are already ready with [[Hugo-Pacheco]]. In parallel, [[Sofia-Vargas]] and [[Nicolas-Mercado]] will conduct a best-practices audit of the Milestone 1 code by accessing the GitHub repository once [[Sergio-Mendoza]] uploads it. The result will be reported tomorrow asynchronously through the project group.

**Active blockers:**
- *(None — Erick's access to the instance is resolved tonight)*

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Finish instance configuration and upload Milestone 1 modules 📅 2026-03-04 
- [ ] [[Sergio-Mendoza]]: Grant GitHub access to [[Sofia-Vargas]] and [[Nicolas-Mercado]] 📅 2026-03-05 
- [ ] [[Hugo-Pacheco]]: Start Milestone 1 UAT in test instance 📅 2026-03-05
- [ ] [[Sofia-Vargas]]: Audit Milestone 1 code and report findings in the group 📅 2026-03-05
- [ ] [[Nicolas-Mercado]]: Audit Milestone 1 code and report findings in the group 📅 2026-03-05
- [ ] [[Elena-Torres]]: Add [[Sofia-Vargas]] to the communication group 📅 2026-03-04 

**Related minutes:** [[Minutes/20260304-CRM-Odoo-Fintrust-UAT-Milestone1-Checkpoint]]

---

## 2026-03-02 — Involuntary hiatus last week; resumption this week; end-of-month goal still on track

**Status:** In progress · **Completion:** 75%

**Executive summary:** The week of 02/24 the project had a hiatus due to priority shift towards accounting and confusion with the Andira Partners instance — no Milestone 1 tests or Milestone 2 development were done. Resumes this week and the end-of-March goal remains.

**What happened:**
In the March 02 Tactical Madrugador, [[Rodney-Ramirez]] explained that last week the project had an involuntary pause: the priority shift towards accounting topics (Odoo Meridian Pay implementation) and the confusion experienced with the instance delivery by [[Partners/Andira Partners]] prevented [[Hugo-Pacheco]] from doing Milestone 1 tests and [[Sergio-Mendoza]] from advancing on Milestone 2 development. This consumed the optimistic time buffer, but the end-of-month planning remains valid. Resumes this week.

**Active blockers:**
- None active

**Next steps:**
- [ ] [[Hugo-Pacheco]]: Resume and complete Milestone 1 tests this week 📅 2026-03-06
- [ ] [[Sergio-Mendoza]]: Resume Milestone 2 development this week 📅 2026-03-06

---

## 2026-03-01 — Milestone 1 completed; Milestone 2 in progress (BonitaOdoo integration started)

**Status:** In progress · **Completion:** 75%

**Executive summary:** Milestone 1 closed on 02/28 with UAT approved by [[Hugo-Pacheco]]; Milestone 2 starts with BonitaOdoo integration and Judicial Management module in progress. Target closing date: 2026-03-14.

**What happened:**
During the week of 02/17 to 02/28, Milestone 1 was completed in its entirety: credentials delivered, Non-Judicial module (Debtors, Creditors, Ganchi, Lawyers) implemented, Configuration module (SIWO catalogs, roles, permissions) configured and UAT tests approved by [[Hugo-Pacheco]]. Sprint 8 closed on 02/26 with 100% of Milestone 1 tasks completed. On 02/17 a discovery session was held with [[Isabella Torres]] and [[Tomas-Navarro]] where current Laura Winslow management flows in Ledger-9 were presented, confirming that the designed data model (activities, notes, dispositions) covers the real operational flow. It was also defined that Meridian Pay will have an independent Odoo instance from Ledger-9. [[Sergio-Mendoza]] started Milestone 2 this week.

**Active blockers:**
- None

**Next steps:**
- [ ] [[Rodrigo-Villalba]]: Complete BonitaOdoo integration (state and timestamp synchronization) 📅 2026-03-07
- [ ] [[Sergio-Mendoza]]: Complete READ-ONLY Judicial Management Module 📅 2026-03-07
- [ ] [[Sergio-Mendoza]]: Case Management module (case-centric with roles) 📅 2026-03-10
- [ ] [[Rodrigo-Villalba]]: OpenKM integration + end-to-end integration tests 📅 2026-03-14

**Related minutes:** [[Minutes/20260217-Laura-Winslow-Flows-CRM-Odoo-Implementation]] · [[Minutes/20260213-CRM-Payers-Scope-Definition]]

---

## 2026-02-24 — Sprint 8 at 80%; closing Thursday; Rafa starts communication testing for written-off portfolio

**Status:** In progress · **Completion:** 75%

**Executive summary:** Sprint 8 progressing well — 80% of 19 tasks completed, with closing expected Thursday 02/26; [[Alex-Carver]] began orchestrating the written-off portfolio communication sequence, with tests expected this week.

**What happened:**
In the February 24 Operational Madrugador, [[Isabella Torres]] reported that Sprint 8, started last week, has 80% of its 19 tasks completed and is expected to close by end of week (Thursday 02/26). The next sprint would start afterwards. [[Alex-Carver]] joined the report indicating he is working on tasks outside the sprint, specifically on orchestrating the sequence of the written-off portfolio communication strategy, and expects to start testing that same week.

**Active blockers:**
- None active

**Next steps:**
- [ ] [[Isabella Torres]]: Close Sprint 8 (19 tasks) and coordinate start of next sprint 📅 2026-02-27

---

## [2026-02-13] — Implementation plan defined: 2 milestones, ~5 weeks, testing led by Hugo Pacheco

**Status:** In progress · **Completion:** 50%

> **Executive summary:** [[Rodney-Ramirez]] and [[Sergio-Mendoza]] align the implementation plan. 2 milestones defined: Milestone 1 (Odoo CRM Base Configuration, ~2 weeks) and Milestone 2 (Bonita Integration, ~2 additional weeks). Formal start next week pending credential delivery. [[Hugo-Pacheco]] will lead functional testing. [[Rodrigo-Villalba]] delivers API documentation today. Total timeline: ~5 weeks.

**What happened:**
Technical alignment session between PM and developer (Sergio connected from Brazil). The plan is structured in 2 milestones with incremental certification. It is agreed that functional testing will be led by [[Hugo-Pacheco]] (not the developer) focusing on real judicial processes. Scope discipline established: additional changes go to parking lot and are billed separately. [[Rodrigo-Villalba]] finishes Ledger-9 and OpenKM API documentation today, essential for Milestone 2. Sergio anticipates having Milestone 1 functional this week.

**Active blockers:**
- Environment access credentials pending delivery — needed for formal start 📅 Week 2026-02-17
- Bonita API documentation (Francisco) — delivery today 📅 2026-02-13

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Deliver detailed roadmap (stages for both milestones + code dates + test dates) 📅 2026-02-14 
- [ ] [[Rodney-Ramirez]]: Deliver environment access credentials 📅 Week 2026-02-17 
- [ ] [[Rodney-Ramirez]]: Align [[Alex-Carver]] with the plan 📅 This week
- [ ] [[Rodney-Ramirez]]: Notify [[Hugo-Pacheco]] about his role as test lead 📅 This week
- [ ] [[Rodrigo-Villalba]]: Share API documentation (Ledger-9 + OpenKM) with [[Sergio-Mendoza]] 📅 2026-02-13 

**Related minutes:** [[Minutes/20260213-CRM-Odoo-Plan-Review]]

---

<!-- ═══════════════════════════════════════════════════════
     PREVIOUS ENTRIES (newest → oldest)
     ═══════════════════════════════════════════════════════ -->

## [2026-02-04] — Requirements closed: team approves model and gives "Go" to development

**Status:** In progress · **Completion:** 45%

> **Executive summary:** Formal closure session of the requirements phase. [[Alex-Carver]]: "We are ready to start now." [[Hugo-Pacheco]] operationally validated the system as "complete and functional, a light but stable and concise version." [[Sergio-Mendoza]] confirms applied changes to the model and delivers hours/milestones proposal.

**What happened:**
[[Sergio-Mendoza]] confirmed changes to the model: debtor demographic data (sex, marital status, workplace), debt block (original + updated), balanced total. [[Alex-Carver]] approved the full scheme. [[Hugo-Pacheco]] validated with no pending observations. [[Sergio-Mendoza]] proposed granular roles: administrator (full view) vs. tracking operator (activities only, no amounts). The entire team positively validated the work.

**Active blockers:**
- None — requirements phase closed

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Contract/milestones proposal to [[Alex-Carver]] 📅 2026-02-04 
- [ ] Formal development start 📅 TBD

**Related minutes:** [[Minutes/20260204-CRM-Odoo-Requirements-Follow-up]]

---

## [2026-01-30] — Requirements workshop (~90 min): judicial architecture clarified, new Lawyers entity, debt breakdown defined

**Status:** In progress · **Completion:** 38%

> **Executive summary:** Operational workshop with [[Hugo-Pacheco]] as judicial expert. New Lawyers entity identified (internal/external, SIWO classifier). Odoo's role clarified (master data + query) vs. Bonita (judicial orchestrator). Judicial Management in Odoo is READ-ONLY. New tabs: Obligations (formerly "Assigned Debts") and capital/interest/fees/ITB breakdown. OpenKM integration confirmed.

**What happened:**
~90-minute workshop where [[Sergio-Mendoza]] presents mockups to [[Hugo-Pacheco]] and [[Elena-Torres]] (first 21 min), then Sergio and Erick continue alone. Key topics: new Lawyers entity (with international SIWO classifier for occupations), adjustments to garnishable entities (mandatory address, RNC, legal representative), non-garnishable debtors without dates (free-text reason, ID by national ID number), case model (Obligations, debt breakdown, actor roles), acts/garnishments as READ-ONLY in Odoo (generated by Bonita), mass batch sending to Bonita. [[Rodney-Ramirez]] shared Euris' template dictionary.

**Active blockers:**
- Architectural decisions pending with Luis/Elena Torres: structure by case vs. by individual, states, portfolio numbering

**Next steps:**
- [ ] [[Elena-Torres]]: Identify applicable SIWO classifiers + pass master lawyer table to Sergio 📅 2026-02-02
- [ ] [[Sergio-Mendoza]]: Update mockups with all adjustments + add Lawyers module 📅 2026-02-02
- [ ] Data dictionary meeting: Sergio + Euris + Francisco 📅 2026-02-02

**Related minutes:** [[Minutes/20260130-CRM-Odoo-Requirements-Workshop]]

---

## [2026-01-30] — AM follow-up: case status only updated by Bonita, debt breakdown confirmed, CRM roles clarified

**Status:** In progress · **Completion:** 35%

> **Executive summary:** Mockup review between [[Carlos-Ruiz]], [[Sergio-Mendoza]] and [[Hugo-Pacheco]]. Key corrections: case status ONLY updatable by Bonita (not manual), new "Debt Breakdown" tab (capital/interest/fees via API), debtor demographic data, removal of "Financial Company" field, bidirectional DebtorCase navigation.

**What happened:**
~19-minute detailed review session. [[Rodney-Ramirez]] clarified the CRM's role: master data maintenance, queries and reports; Bonita orchestrates and updates states. It was agreed that the case status in Odoo is NEVER modified manually (avoids inconsistencies with Bonita). [[Sergio-Mendoza]] already incorporated product-by-creditor tab, address, LNC and creditor lawyers. The Figma mockups look so good there is a risk stakeholders believe it is already in production.

**Active blockers:**
- None

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Add demographic data to Debtor, debt breakdown tab, rename fields 📅 before 2026-02-02
- [ ] Data dictionary meeting with Euris + Francisco 📅 2026-02-02

**Related minutes:** [[Minutes/20260130-CRM-Odoo-MockUp-Review-Follow-up]]

---

## [2026-01-28] — MockUps presented and validated: 4-module structure approved, product-by-creditor tab mandatory

**Status:** In progress · **Completion:** 30%

> **Executive summary:** [[Sergio-Mendoza]] presented Odoo CRM mockups to the extended team, replicating Odoo's style with 4 sections. The structure was approved in principle. Missing field identified: product types by creditor tab. Security and access control included in MVP scope. "Go" to development decision scheduled for 01/29 afternoon.

**What happened:**
[[Sergio-Mendoza]] presented the mockups (in Figma, faithful to Odoo style): Non-Judicial Management, Judicial Management, Case Management, Configuration. [[Carlos-Ruiz]] identified a critical missing field: product types by creditor tab (card, loan, written-off loan, etc.). [[Elena-Torres]] requested that security and role-based access be in the MVP. The team warmly congratulated [[Sergio-Mendoza]]'s work. Two detailed review meetings were scheduled for 01/29: AM with Hugo Pacheco and PM with Carlos Ruiz.

**Active blockers:**
- Review of operational fields with [[Hugo-Pacheco]] pending 📅 2026-01-29 AM

**Next steps:**
- [ ] [[Sergio-Mendoza]] + [[Hugo-Pacheco]]: Review mandatory operational fields 📅 2026-01-29 AM 
- [ ] [[Sergio-Mendoza]] + [[Carlos-Ruiz]]: Final structure review 📅 2026-01-29 PM 
- [ ] "Go" to development decision 📅 2026-01-29 afternoon 

**Related minutes:** [[Minutes/20260128-CRM-Odoo-User-Stories-and-MockUps]]

---

## [2026-01-14] — Gap Analysis with client: bidirectional BonitaOdoo integration NON-NEGOTIABLE, data model validated

**Status:** In progress · **Completion:** 22%

> **Executive summary:** [[Sergio-Mendoza]] presented the formal gap analysis to the extended team including [[Elena-Torres]] and [[Hugo-Pacheco]]. Critical debate: bidirectional BonitaOdoo state integration is NON-NEGOTIABLE from MVP. Debtor bank accounts remain outside the model. Bonita judicial process fields must be mapped to Odoo.

**What happened:**
Presentation of Fintrust's macro process in Odoo (Non-Judicial + Judicial Management with Bonita). Data model (Debtor, Creditor, Ganchi, Supplier, Case) with detailed fields. [[Elena-Torres]] rejected the proposal to only record Bonita activities without updating case status: "Everything Bonita does must leave a trace in Odoo from the MVP." The sub-process gap was identified (one case can have N active judicial processes in Bonita). Next deliverable: User Stories.

**Active blockers:**
- Bonita judicial process fields pending mapping to Odoo

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Deliver User Stories with mapped fields 📅 2026-01-19 
- [ ] [[Rodrigo-Villalba]] + [[Sergio-Mendoza]]: Align on BonitaOdoo fields 📅 2026-01-16

**Related minutes:** [[Minutes/20260114-CRM-Odoo-Gap-Analysis-Review]]

---

## [2026-01-12] — Gap analysis checkpoint: incremental GAF strategy defined, base model entities confirmed

**Status:** In progress · **Completion:** 20%

> **Executive summary:** [[Sergio-Mendoza]] presented the gap analysis diagram (standard Odoo vs. custom development vs. integrations). The team agreed on an incremental delivery strategy to GAF with user stories prioritized by dependencies. Key decision: no direct API integration with banks — standardized batch load. [[Alex-Carver]] formalized the requirement for timestamps on every activity/state. Meeting with [[Rodrigo-Villalba]] and presentation to "the doctor" scheduled for January 13.

**What happened:**
Technical checkpoint where [[Sergio-Mendoza]] presented the ecosystem diagram (standard Odoo + custom development + Bonita/OpenKM integrations). The team debated creditor CRM integration and agreed that banks will deliver batch files instead of APIs. [[Alex-Carver]] reinforced the traceability requirement with timestamps — Ledger-9's critical gap. The base model entities were identified: Case, Debtor, Creditor, Supplier, Guaranty. The delivery process to GAF was defined: user stories + mockups + DB structure, module by module in priority order.

**Active blockers:**
- Formal documentation for GAF in preparation — [[Sergio-Mendoza]] needs to formalize prioritized user stories
- Ledger-9 API catalog pending validation with [[Rodrigo-Villalba]] 📅 2026-01-13

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Meeting with [[Rodrigo-Villalba]] AM — review BonitaOdoo integration document and Ledger-9 API catalog 📅 2026-01-13 
- [ ] [[Sergio-Mendoza]]: Formalize user stories + prioritized field mapping for GAF 📅 2026-01-13
- [ ] [[Rodney-Ramirez]]: Present gap analysis + estimates + roadmap to "the doctor" 📅 2026-01-13 3:00 PM 
- [ ] [[Rodney-Ramirez]]: Share complete data model link (Francisco) and Ledger-9 API catalog in the group 📅 2026-01-12

**Related minutes:** [[Minutes/20260112-CRM-Odoo-Analysis-Checkpoint]]

---

## [2026-01-09] — Deep functional analysis Ledger-9: case-centric model defined, 100% custom development confirmed

**Status:** In progress · **Completion:** 15%

> **Executive summary:** [[Carlos-Ruiz]] presented a complete walkthrough of Ledger-9 (judicial and extrajudicial processes). [[Sergio-Mendoza]] defined the case-centric data model for Odoo, confirmed that ~100% of the judicial module requires custom development, and the team agreed on MVP scope for the meeting with senior management on Tuesday January 13.

**What happened:**
Technical session with [[Carlos-Ruiz]] for [[Sergio-Mendoza]] to understand Ledger-9 in depth. Case-centric architecture was defined (individuals linked to case with roles: main debtor, co-debtor, guarantor, spouse). The contact history rule was established (phones/emails/addresses are never deleted). [[Nicolas-Mercado]] assumed the task of normalizing the data dictionary. It was clarified that Fintrust does not receive direct payments — it charges a service fee to the creditor. Critical gap identified: Ledger-9 has no case status query interface.

**Active blockers:**
- Ledger-9 has no case status query interface — Odoo must build this capability from scratch
- 100% custom development required — only Odoo's `res.partner` is reusable

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Meet with [[Rodrigo-Villalba]] to validate MVP vs. BonitaLedger-9 integration map 📅 2026-01-11 
- [ ] [[Nicolas-Mercado]]: Normalize unified master data dictionary 📅 2026-01-13
- [ ] [[Rodney-Ramirez]]: Present gap analysis + estimates + roadmap to "the doctor" 📅 2026-01-13 

**Related minutes:** [[Minutes/20260109-Odoo-CRM-Ledger-9-Gap-Review]]

---

## [2025-12-19] — Strategy defined: BonitaLedger-9 bypass plan while Odoo CRM prepares in parallel

**Status:** In progress · **Completion:** 10%

> **Executive summary:** Strategic meeting confirmed that Odoo CRM will not be ready for Bonita's launch (January 5 2026). A bypass plan was adopted: Bonita integrates temporarily with Ledger-9 for the MVP judicial process, while Odoo CRM prepares in parallel. The Ledger-9 API is the critical path.

**What happened:**
Session with [[Rodrigo-Villalba]] (external architect), [[Alex-Carver]], [[Nicolas-Mercado]], [[Sergio-Mendoza]] and [[Carlos-Ruiz]]. Two parallel tracks defined: (1) [[Sergio-Mendoza]] inventories Ledger-9 with Hugo Pacheco (super-user) to map what to replace, and (2) [[Rodrigo-Villalba]] delivers BonitaLedger-9 integration architecture meeting with [[Ana-Teresa-Peguero]] and [[Jesus]]. [[Elena-Torres]] shared the master judicial file states for validation with the legal team.

**Active blockers:**
- Ledger-9 API is not ready or exposed for external integration with Bonita — critical before January 5 2026

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Meet with Hugo Pacheco to inventory active judicial functions in Ledger-9 📅 2025-12-22
- [ ] [[Rodrigo-Villalba]]: Meet with [[Ana-Teresa-Peguero]] and [[Jesus]] to map BonitaLedger-9 integration 📅 2025-12-22
- [ ] [[Rodney-Ramirez]]: Share Bonita user stories with [[Rodrigo-Villalba]] 📅 2025-12-23
- [ ] [[Carlos-Ruiz]]: Prepare and expose Ledger-9 API for Bonita (ports, IPs, Huawei Cloud monitoring) before January 5 2026

**Related minutes:** [[Minutes/20251219-Functional-Analysis-Odoo-Ledger-9-CRM]]

---

## [2025-12-16] — Initial gap analysis: Odoo does not natively support Fintrust's Debtor model

**Status:** In progress · **Completion:** 5%

> **Executive summary:** First Odoo exploration session with consultant Sergio Mendoza confirmed that custom development is required; MVP scope was delimited to the judicial process for Bonita integration.

**What happened:**
[[Sergio-Mendoza]] presented Odoo v17's Contacts (Partners) module and its native limitations. Key gaps were identified: Odoo only supports 1 phone/email/address per contact, has no "Debtor" model, no personal references catalog, no estimated income fields. The team decided to delimit the MVP to the judicial process and bidirectional Bonita integration, leaving extrajudicial management for a later phase. Defined precondition: complete the Bonita flow before resuming the full gap analysis.

**Active blockers:**
- None

**Next steps:**
- [ ] [[Sergio-Mendoza]]: Attend Bonita session to understand OdooBonita interactions 📅 2025-12-17
- [ ] [[Rodney-Ramirez]]: Complete 2 Bonita functional refinement sessions 📅 2025-12-18
- [ ] [[Rodney-Ramirez]]: Schedule surgical Odoo gap analysis with [[Sergio-Mendoza]] post-Bonita 📅 2025-12-19

**Related minutes:** [[Minutes/20251216-CRM-Gap-Exploration-Odoo]]

---

## [YYYY-MM-DD] — Project start

**Status:** To start · **Completion:** 0%

> **Executive summary:** Project created. Pending team definition and first sprint.

**What happened:**
Creation of the project file in the vault. Identified alignment with [[POA-2026]] (initiative PR-X.X-NN). Initial team to be confirmed.

**Next steps:**
- [ ] Complete README.md with context, team and milestones
- [ ] Schedule kickoff with sponsor
- [ ] Link initial FORs in `Documents/`

---
