# TEST PLAN DOCUMENT
## Project: OrangeHRM Web Application — QA Testing Project
### Document Reference: QA-TP-OHRM-001 | Version: 1.0 | Standard Reference: IEEE 829-2008

---

## Document Control

| Field | Detail |
|---|---|
| Project Name | OrangeHRM Human Resource Management System (HRMS) — Functional QA Testing |
| Application URL | https://opensource-demo.orangehrmlive.com/web/index.php/auth/login |
| Document Version | 1.0 |
| Prepared By | QA Architect / Senior QA Engineer |
| Reviewed By | QA Lead |
| Approved By | Project Manager |
| Date | 2026 |
| Status | Baseline |

---

## 1. Introduction

### 1.1 Purpose
This Test Plan defines the scope, approach, resources, and schedule of the testing activities to be performed on the **OrangeHRM** application (Open Source HR Demo instance). It is prepared in accordance with **IEEE 829-2008** Test Plan documentation standards and follows **ISO/IEC/IEEE 29119** software testing principles. The purpose of this document is to:

- Identify items and features to be tested.
- Define the testing tasks to be performed and the individuals responsible for each task.
- Establish a schedule, entry/exit criteria, and risk mitigation approach.
- Serve as a reference artifact for QA audits, client sign-off, and knowledge transfer.

### 1.2 Project Background
OrangeHRM is a widely used open-source Human Resource Management System used to manage employee data, leave, recruitment, time, and performance modules. The publicly hosted demo instance (`opensource-demo.orangehrmlive.com`) is used industry-wide as a **sandbox training/testing application** for QA professionals to practice manual, functional, and automation testing. This project simulates a real-world QA engagement — as would be executed at an IT services organization (Accenture / TCS / Cognizant / Infosys) — to validate the core HR business workflows of the application.

### 1.3 Objective
To ensure that the OrangeHRM application's core modules (**Authentication, PIM, Leave, Dashboard, Admin**) function correctly as per expected business behavior, are free of critical/high severity defects, and provide a stable, secure, and usable experience across the supported test environment.

---

## 2. Scope

### 2.1 In-Scope
| Module | Functionality Covered |
|---|---|
| **Login / Authentication** | Valid/invalid login, forgot password flow, session handling, logout, field validations |
| **Dashboard** | Widget rendering, quick launch panel, employee distribution charts, navigation post-login |
| **PIM (Personal Information Management)** | Add Employee, Search Employee, Edit Employee, Delete Employee, Employee List filters |
| **Leave Module** | Apply Leave, Leave List, My Leave, Leave validations (date range, balance) |
| **Admin Module (Sanity level)** | User Management — Add/Search System User (Sanity only) |
| **Cross-cutting** | UI validations, field-level validations, mandatory field checks, negative/boundary testing, navigation, responsiveness (basic) |

### 2.2 Out-of-Scope
- Recruitment Module (deep functional testing)
- Performance & Time Module (deep functional testing)
- Payroll / Claim module (not available in demo instance)
- Load, Stress, and Performance Testing (non-functional, high-volume)
- Security penetration testing (only basic negative/security validation is covered)
- Native mobile application testing (only responsive web behavior, if applicable)
- Database-level backend validation (no direct DB access to public demo instance)
- Third-party integrations (email server, SSO, LDAP)
- Automation framework execution results (this package documents manual QA artifacts; automation is a separate deliverable)

---

## 3. Test Strategy

### 3.1 Overall Approach
A **risk-based, requirement-driven manual testing approach** will be adopted, supplemented by structured test design techniques:
- **Equivalence Partitioning (EP)** and **Boundary Value Analysis (BVA)** for input field validation (e.g., username length, password length, leave date ranges).
- **Decision Table Testing** for business rule combinations (e.g., leave approval logic based on leave balance and date validity).
- **State Transition Testing** for record lifecycle (e.g., Employee record: Created → Active → Terminated/Deleted; Leave: Applied → Pending Approval → Approved/Rejected/Cancelled).
- **Error Guessing** based on QA experience with similar HRMS applications.

### 3.2 Test Levels
| Level | Description | Responsibility |
|---|---|---|
| **Unit Testing** | Not performed by QA (Developer responsibility) — assumed complete for this OSS build | Dev Team |
| **Integration Testing** | Validating data flow between modules (e.g., Employee added in PIM reflects in Leave module employee dropdown, Admin user list) | QA Team |
| **System Testing** | End-to-end validation of complete business workflows across the full application | QA Team |
| **User Acceptance Testing (UAT)** | Business-scenario validation simulating actual HR Admin/ESS user usage | QA Team + Business Stakeholder (simulated) |

### 3.3 Test Types
| Type | Purpose |
|---|---|
| **Smoke Testing** | Verify build stability — Login, Dashboard load, module navigation works before deeper testing |
| **Sanity Testing** | Quick, focused check after minor fix/change (e.g., after a defect fix on Add Employee) |
| **Functional Testing** | Validate each feature against functional/business requirements |
| **Regression Testing** | Re-verify unaffected areas after defect fixes / new builds |
| **Integration Testing** | Validate cross-module data consistency |
| **End-to-End (E2E) Testing** | Full business flow: Login → Add Employee → Search Employee → Apply Leave → Logout |
| **Negative Testing** | Invalid inputs, boundary violations, unauthorized access attempts |
| **UI/Usability Testing** | Field alignment, mandatory field indicators, error message clarity, tooltips |
| **Cross-Browser Testing** | Validate on Chrome, Firefox, Edge (basic compatibility check) |
| **Boundary Value Testing** | Field length limits (Username, Password, Employee ID, Names) |

### 3.4 Test Design Techniques Used
- Equivalence Partitioning
- Boundary Value Analysis
- Decision Table Testing
- Use Case-Based Testing
- Exploratory Testing (time-boxed sessions post scripted execution)

---

## 4. Entry Criteria
Testing will commence only when the following are satisfied:
1. Test environment (URL, credentials) is accessible and stable.
2. Test Plan is reviewed and approved.
3. Test scenarios and test cases are documented and reviewed.
4. Requirement/User story documentation (or equivalent OrangeHRM functional spec / exploratory understanding) is available.
5. Test data (valid/invalid employee data, leave data) is prepared.
6. Required tools (browser, test management sheet/tool, bug tracker) are installed and accessible.

## 5. Exit Criteria
Testing will be considered complete when:
1. 100% of planned test cases (Critical & High priority) have been executed.
2. No open **Critical** or **Blocker** severity defects remain unresolved.
3. ≥ 95% of test cases have passed; remaining failures are documented with an accepted risk sign-off.
4. All identified defects are logged, triaged, and either fixed & retested, or deferred with stakeholder approval.
5. Test Summary Report is prepared, reviewed, and signed off.
6. RTM shows 100% requirement-to-test-case coverage.

---

## 6. Assumptions
- The publicly hosted OrangeHRM demo instance (`opensource-demo.orangehrmlive.com`) is used as the test environment; data may be reset periodically by the OrangeHRM team, which may affect data persistence between test cycles.
- Default admin credentials (`Admin` / `admin123`) are valid and unchanged for the demo instance at the time of testing.
- The system under test is a **web application** only; no native mobile app is in scope.
- Since this is a public shared demo environment, multiple unrelated testers globally may be modifying data concurrently — this is accepted as an environmental constraint.
- No dedicated staging/UAT environment with isolated data is available; hence some data-dependent regression scenarios are executed with fresh, uniquely-named test data (timestamp-based) to avoid collisions.

## 7. Risks & Mitigation

| Risk ID | Risk Description | Likelihood | Impact | Mitigation Strategy |
|---|---|---|---|---|
| R-01 | Shared public demo environment may have data reset/cleared without notice | High | Medium | Take screenshots/evidence immediately after execution; do not depend on long-term data persistence |
| R-02 | Concurrent testers on the same demo instance may alter/delete shared data (e.g., delete an employee another tester is testing) | Medium | Medium | Use unique, identifiable test data naming conventions (e.g., `QA_Test_<timestamp>`) |
| R-03 | No access to backend/database for deep data validation | High | Low | Rely on UI-level and API-response (network tab) validation where possible |
| R-04 | Limited time for full regression on every release | Medium | High | Prioritize test cases using risk-based approach; maintain a regression suite of high-priority cases |
| R-05 | Application performance degradation due to public/shared hosting | Medium | Low | Note performance observations separately; not treated as functional defects unless blocking |
| R-06 | Browser version drift causing inconsistent UI rendering | Low | Medium | Fix and document browser/version matrix before execution |

---

## 8. Tools Used

| Category | Tool |
|---|---|
| Test Management / Documentation | Excel / Google Sheets, Markdown (GitHub) |
| Defect/Bug Tracking | Jira (simulated format used in this project) |
| Browser DevTools | Chrome DevTools (Network/Console validation) |
| Cross-Browser Testing | Chrome, Mozilla Firefox, Microsoft Edge |
| Automation (future scope) | Selenium WebDriver (Java/Python), Cypress |
| API Testing (future scope) | Postman |
| Version Control | Git & GitHub |
| Screen Capture/Evidence | Snipping Tool / Browser Screenshot |
| Test Case Design Reference | ISTQB Foundation Level Techniques |

---

## 9. Environment Details

| Item | Detail |
|---|---|
| Application Under Test | OrangeHRM OS Demo (Version: latest hosted build) |
| URL | https://opensource-demo.orangehrmlive.com/web/index.php/auth/login |
| Environment Type | Public Cloud-hosted Demo (shared) |
| Browser(s) | Google Chrome (Primary), Mozilla Firefox, Microsoft Edge (Secondary) |
| OS | Windows 10/11 |
| Login Credentials (Standard Demo) | Username: `Admin` / Password: `admin123` |
| Network | Standard broadband internet connection |
| Screen Resolution | 1920×1080 (Desktop primary), basic responsive check on 1366×768 |

---

## 10. Roles & Responsibilities

| Role | Responsibility | Assigned To |
|---|---|---|
| QA Lead / Test Manager | Test strategy approval, resource planning, stakeholder communication, sign-off | QA Lead |
| Senior QA Engineer (Author) | Test plan authoring, test case design, execution, defect reporting, RTM maintenance | Senior QA Engineer |
| QA Engineer(s) | Test case execution, defect logging, regression execution | QA Team |
| Developer / Dev Lead | Defect triage, root cause analysis, fixes | Development Team |
| Business Analyst / Product Owner | Requirement clarification, UAT sign-off | BA/PO |
| DevOps | Environment/build availability | DevOps Engineer |

---

## 11. Test Deliverables
1. Test Plan Document (this document)
2. Test Scenarios Document
3. Detailed Test Cases (Excel/Markdown format)
4. Requirement Traceability Matrix (RTM)
5. Defect/Bug Reports
6. Test Execution Summary Report
7. GitHub-ready QA Project Documentation Package

## 12. Schedule (Sample Timeline)

| Phase | Duration | Activity |
|---|---|---|
| Phase 1 | Day 1–2 | Requirement analysis, Test Plan preparation |
| Phase 2 | Day 3–5 | Test Scenario & Test Case design |
| Phase 3 | Day 6 | Smoke Testing |
| Phase 4 | Day 7–10 | Functional Test Execution (all modules) |
| Phase 5 | Day 11 | Defect Logging, Retesting |
| Phase 6 | Day 12 | Regression Testing |
| Phase 7 | Day 13 | Test Closure & Summary Report |

## 13. Suspension & Resumption Criteria
- **Suspension:** Testing will be suspended if the application/login is completely inaccessible, or a Blocker defect prevents further progress (e.g., Login fails for all valid credentials).
- **Resumption:** Testing resumes once the blocking issue is resolved/environment restored, and a smoke re-check confirms stability.

---
*End of Test Plan Document — QA-TP-OHRM-001*
