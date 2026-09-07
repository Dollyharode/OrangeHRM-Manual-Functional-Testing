# TEST SCENARIOS DOCUMENT
## Project: OrangeHRM Web Application | Doc Ref: QA-TS-OHRM-002 | Version 1.0

Test Scenarios represent high-level "what to test" statements derived from business requirements. Each scenario is later broken down into detailed test cases (see `Test_Cases.xlsx`).

---

## Module 1: Login / Authentication

| Scenario ID | Scenario Description |
|---|---|
| TS_LOGIN_01 | Verify user can log in with valid username and password |
| TS_LOGIN_02 | Verify user cannot log in with invalid username/password combinations |
| TS_LOGIN_03 | Verify system behavior when username or password field is left blank |
| TS_LOGIN_04 | Verify appropriate error message on invalid credentials without revealing which field is wrong (security best practice) |
| TS_LOGIN_05 | Verify "Forgot Your Password?" link navigates to password reset page |
| TS_LOGIN_06 | Verify password reset flow with a valid/invalid registered username |
| TS_LOGIN_07 | Verify password field masks entered characters |
| TS_LOGIN_08 | Verify user session terminates properly on Logout |
| TS_LOGIN_09 | Verify direct URL access to internal pages (e.g., dashboard) without login redirects to Login page |
| TS_LOGIN_10 | Verify login page UI elements (logo, fields, labels, footer, version info) render correctly |
| TS_LOGIN_11 | Verify boundary limits of username/password fields (min/max character length) |
| TS_LOGIN_12 | Verify SQL Injection / script injection attempts in login fields are safely handled |
| TS_LOGIN_13 | Verify multiple failed login attempts behavior (lockout/captcha, if implemented) |
| TS_LOGIN_14 | Verify browser back button after logout does not display cached authenticated pages |

---

## Module 2: Dashboard

| Scenario ID | Scenario Description |
|---|---|
| TS_DASH_01 | Verify Dashboard loads successfully immediately after login |
| TS_DASH_02 | Verify all default widgets are displayed (Time at Work, My Actions, Quick Launch, Buzz Latest Posts, Employees on Leave Today, Employee Distribution charts) |
| TS_DASH_03 | Verify Quick Launch panel icons navigate to correct respective modules |
| TS_DASH_04 | Verify Employee Distribution by Sub Unit / Nationality charts render with correct data representation |
| TS_DASH_05 | Verify top navigation bar (Admin, PIM, Leave, Time, Recruitment, etc.) is accessible from Dashboard |
| TS_DASH_06 | Verify user profile dropdown (top right) displays correct logged-in user name and options (About, Support, Change Password, Logout) |
| TS_DASH_07 | Verify Dashboard is responsive and displays correctly on different screen resolutions |

---

## Module 3: PIM — Add Employee

| Scenario ID | Scenario Description |
|---|---|
| TS_PIM_ADD_01 | Verify user can add a new employee with only mandatory fields (First Name, Last Name) |
| TS_PIM_ADD_02 | Verify user can add a new employee with all optional fields filled (middle name, employee ID, photo) |
| TS_PIM_ADD_03 | Verify system auto-generates a unique Employee ID when not manually specified |
| TS_PIM_ADD_04 | Verify validation error when mandatory fields (First Name/Last Name) are left blank |
| TS_PIM_ADD_05 | Verify system prevents duplicate Employee ID entries |
| TS_PIM_ADD_06 | Verify "Create Login Details" toggle correctly reveals username/password/status fields |
| TS_PIM_ADD_07 | Verify validation on Login Details section (password complexity, confirm password match) |
| TS_PIM_ADD_08 | Verify employee photo upload accepts valid formats/sizes and rejects invalid ones |
| TS_PIM_ADD_09 | Verify newly added employee appears correctly in Employee List |
| TS_PIM_ADD_10 | Verify boundary values for Name fields (max character length as per field constraint) |
| TS_PIM_ADD_11 | Verify special characters/numeric values in Name fields are handled per validation rule |
| TS_PIM_ADD_12 | Verify Cancel/navigate-away discards unsaved Add Employee data |

---

## Module 4: PIM — Search Employee

| Scenario ID | Scenario Description |
|---|---|
| TS_PIM_SRCH_01 | Verify user can search an employee by full Employee Name |
| TS_PIM_SRCH_02 | Verify user can search an employee by partial Employee Name |
| TS_PIM_SRCH_03 | Verify user can search an employee using Employee ID |
| TS_PIM_SRCH_04 | Verify search using Employment Status / Sub Unit / Supervisor filters |
| TS_PIM_SRCH_05 | Verify system displays "No Records Found" for a non-existent employee search |
| TS_PIM_SRCH_06 | Verify Reset button clears all applied search filters and reloads the full list |
| TS_PIM_SRCH_07 | Verify search results table pagination and sorting (by name/ID) functions correctly |
| TS_PIM_SRCH_08 | Verify search field behavior with special characters/SQL injection strings |
| TS_PIM_SRCH_09 | Verify case-insensitive search behavior |

---

## Module 5: PIM — Delete Employee

| Scenario ID | Scenario Description |
|---|---|
| TS_PIM_DEL_01 | Verify user can delete a single employee record from Employee List |
| TS_PIM_DEL_02 | Verify user can select and delete multiple employee records at once |
| TS_PIM_DEL_03 | Verify confirmation dialog appears before deletion is finalized |
| TS_PIM_DEL_04 | Verify deleted employee record no longer appears in Employee List/search results |
| TS_PIM_DEL_05 | Verify Cancel on delete confirmation dialog retains the employee record |
| TS_PIM_DEL_06 | Verify deleting an employee removes/updates related references in dependent modules (Leave, Admin User list) |
| TS_PIM_DEL_07 | Verify system behavior when attempting bulk delete with zero records selected (Delete button disabled/no-op) |

---

## Module 6: Leave — Apply Leave

| Scenario ID | Scenario Description |
|---|---|
| TS_LEAVE_01 | Verify user can successfully apply for leave with valid Leave Type and Date Range |
| TS_LEAVE_02 | Verify validation error when "From Date" is later than "To Date" |
| TS_LEAVE_03 | Verify validation error when applying leave without selecting a Leave Type |
| TS_LEAVE_04 | Verify system prevents applying leave for past dates (if business rule enforces this) |
| TS_LEAVE_05 | Verify partial-day leave options (Half Day - Morning/Afternoon) function correctly |
| TS_LEAVE_06 | Verify leave comments/attachment field (if present) accepts input correctly |
| TS_LEAVE_07 | Verify applied leave appears correctly in "My Leave" / Leave List with status "Pending Approval" |
| TS_LEAVE_08 | Verify duplicate leave application for the same overlapping date range is handled per business rule |
| TS_LEAVE_09 | Verify leave balance is not deducted for a "Pending" leave until approved (per business rule) |
| TS_LEAVE_10 | Verify Leave Module calendar view reflects applied leave accurately |
| TS_LEAVE_11 | Verify user can cancel a "Pending Approval" leave request |
| TS_LEAVE_12 | Verify boundary case: applying leave for a single day vs. a long date range (e.g., 30+ days) |

---

## End-to-End (E2E) Business Flow Scenarios

| Scenario ID | Scenario Description |
|---|---|
| TS_E2E_01 | Login → Add New Employee → Search & Verify Employee → Apply Leave for Employee → Verify on Dashboard → Logout |
| TS_E2E_02 | Login → Add Employee with Login Credentials → Logout → Login as New Employee (ESS) → Apply Leave → Logout |
| TS_E2E_03 | Login as Admin → Search Employee → Delete Employee → Verify removal reflected across PIM and Leave modules |
| TS_E2E_04 | Login → Navigate across all main modules from top menu to verify no broken navigation/links |

---
*End of Test Scenarios Document — QA-TS-OHRM-002*
