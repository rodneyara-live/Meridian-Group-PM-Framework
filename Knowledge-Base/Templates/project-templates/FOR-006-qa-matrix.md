# FOR-006 — QA Matrix

**Project:** [Project Name]
**Company:** [Meridian Group / Fintrust / Meridian Pay]
**Build version:** [v0.0.0]
**Execution date:** [YYYY-MM-DD]
**QA Lead:** [Name]
**Reviewed by:** [Name]

---

## 1. Execution Summary

| Metric | Value |
|---|---|
| Total test cases | |
| Executed cases | |
| Approved cases ✅ | |
| Failed cases ❌ | |
| Blocked cases 🚫 | |
| Not executed cases | |
| % Executed coverage | |
| % Success rate | |

**Overall build status:**
- [ ] ✅ Approved — Can go to production
- [ ] 🟡 Approved with observations — See defects section
- [ ] ❌ Rejected — Requires fixes before continuing

---

## 2. Test Cases by Module

### Module: [Module Name 1]

| ID | Test Case | Priority | Type | Result | Defect # | Notes |
|---|---|---|---|---|---|---|
| TC-001 | | High | Functional | ✅ / ❌ / 🚫 | | |
| TC-002 | | High | Functional | ✅ / ❌ / 🚫 | | |
| TC-003 | | Medium | Regression | ✅ / ❌ / 🚫 | | |
| TC-004 | | Medium | Integration | ✅ / ❌ / 🚫 | | |
| TC-005 | | Low | UI/UX | ✅ / ❌ / 🚫 | | |

### Module: [Module Name 2]

| ID | Test Case | Priority | Type | Result | Defect # | Notes |
|---|---|---|---|---|---|---|
| TC-006 | | High | Functional | ✅ / ❌ / 🚫 | | |
| TC-007 | | High | Security | ✅ / ❌ / 🚫 | | |
| TC-008 | | Medium | Performance | ✅ / ❌ / 🚫 | | |

**Test types:**
- **Functional** — Verifies that the functionality does what it should
- **Regression** — Verifies nothing previously built was broken
- **Integration** — Verifies systems connect correctly
- **UI/UX** — Verifies appearance and user interaction
- **Security** — Verifies access control and data protection
- **Performance** — Verifies response times and load

---

## 3. Defect Log

| Defect # | Description | Module | Severity | Status | Assigned to | Report date | Resolution date |
|---|---|---|---|---|---|---|---|
| DEF-001 | | | 🔴 Critical | Open / Resolved | | | |
| DEF-002 | | | 🟠 High | Open / Resolved | | | |
| DEF-003 | | | 🟡 Medium | Open / Resolved | | | |
| DEF-004 | | | 🔵 Low | Open / Resolved | | | |

**Severity criteria:**

| Severity | Criterion | Max. resolution time |
|---|---|---|
| 🔴 Critical | System not working / data loss / security failure | 24 hours |
| 🟠 High | Main functionality unavailable / no workaround | 48 hours |
| 🟡 Medium | Functionality available with workaround | 5 business days |
| 🔵 Low | Cosmetic issues / minor improvements | Next phase|

---

## 4. Regression Tests

Verification that previous functionalities continue to operate correctly after project changes:

| Area | Test | Result |
|---|---|---|
| | | ✅ / ❌ |
| | | ✅ / ❌ |
| | | ✅ / ❌ |

---

## 5. Performance Tests (if applicable)

| Scenario | Metric | Expected Value | Actual Value | Result |
|---|---|---|---|---|
| Main page load | Response time | < 3s | | ✅ / ❌ |
| Query with 1000 records | Response time | < 5s | | ✅ / ❌ |
| 50 simultaneous users | No system crash | — | | ✅ / ❌ |

---

## 6. Pre-Production Quality Checklist

- [ ] All critical and high defects are resolved
- [ ] Regression tests approved
- [ ] User documentation updated
- [ ] Production credentials and access configured
- [ ] Rollback plan documented and tested
- [ ] Support team notified of deployment

---

## 7. General Observations

[Add relevant context: test environment, limitations, assumptions, risks identified during QA]

---

## 8. Approvals

| Role | Name | Signature / Confirmation | Date |
|---|---|---|---|
| QA Lead | | | |
| Tech Lead | | | |
| Project Manager | | | |

---

## Version Control

| Version | Date | Author | Changes |
|---|---|---|---|
| 1.0 | | | Initial version |
