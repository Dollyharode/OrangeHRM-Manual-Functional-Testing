# REQUIREMENT TRACEABILITY MATRIX (RTM)
## Project: OrangeHRM Web Application | Doc Ref: QA-RTM-OHRM-005 | Version 1.0

The RTM maps each **Business Requirement (BR)** to its corresponding **Test Scenario(s)** and **Test Case(s)**, ensuring 100% test coverage and enabling impact analysis when requirements change.

## Quick-View RTM (Simplified — Module Level)

Use this table for a fast scan. Fill the **Status** column honestly after real execution.

| Module | Requirement | Test Case ID(s) | Status |
|---|---|---|---|
| Login | Valid login succeeds | TC_LOGIN_001 | Not Executed |
| Login | Invalid login rejected | TC_LOGIN_002–004 | Not Executed |
| Login | Mandatory field validation | TC_LOGIN_005–007 | Not Executed |
| Dashboard | Widgets load correctly | TC_DASH_001–002 | Not Executed |
| PIM | Add employee (mandatory fields) | TC_PIM_ADD_001 | Not Executed |
| PIM | Duplicate Employee ID blocked | TC_PIM_ADD_006 | Not Executed |
| PIM | Search employee by name/ID | TC_PIM_SRCH_001–003 | Not Executed |
| PIM | Delete employee with confirmation | TC_PIM_DEL_001–003 | Not Executed |
| Leave | Apply leave (valid range) | TC_LEAVE_001 | Not Executed |
| Leave | From Date > To Date rejected | TC_LEAVE_002 | Not Executed |

> Full detailed 52-requirement mapping is below. Update Status to **Pass / Fail / Blocked** as you execute, and reference the matching screenshot in `/Screenshots`.

| Req ID | Business Requirement Description | Test Scenario ID(s) | Test Case ID(s) | Coverage Status |
|---|---|---|---|---|
| BR-01 | System shall allow a registered user to log in using valid credentials | TS_LOGIN_01 | TC_LOGIN_001 | Covered |
| BR-02 | System shall reject login for invalid username/password combinations without revealing the specific invalid field | TS_LOGIN_02, TS_LOGIN_04 | TC_LOGIN_002, TC_LOGIN_003, TC_LOGIN_004 | Covered |
| BR-03 | System shall enforce mandatory Username and Password fields | TS_LOGIN_03 | TC_LOGIN_005, TC_LOGIN_006, TC_LOGIN_007 | Covered |
| BR-04 | System shall mask password input | TS_LOGIN_07 | TC_LOGIN_008 | Covered |
| BR-05 | System shall provide a "Forgot Password" self-service reset flow | TS_LOGIN_05, TS_LOGIN_06 | TC_LOGIN_009, TC_LOGIN_010, TC_LOGIN_011 | Covered |
| BR-06 | System shall prevent unauthenticated access to internal pages via direct URL | TS_LOGIN_09 | TC_LOGIN_012 | Covered |
| BR-07 | System shall terminate the user session correctly on Logout, with no cached back-navigation access | TS_LOGIN_08, TS_LOGIN_14 | TC_LOGIN_013, TC_LOGIN_014 | Covered |
| BR-08 | Login fields shall enforce defined character length boundaries | TS_LOGIN_11 | TC_LOGIN_015, TC_LOGIN_016 | Covered |
| BR-09 | System shall be resilient against SQL Injection and XSS attacks on login fields | TS_LOGIN_12 | TC_LOGIN_017, TC_LOGIN_018 | Covered |
| BR-10 | System shall handle repeated failed login attempts gracefully (lockout/captcha, if configured) | TS_LOGIN_13 | TC_LOGIN_020 | Covered |
| BR-11 | Login page UI shall render all required elements correctly | TS_LOGIN_10 | TC_LOGIN_019 | Covered |
| BR-12 | System shall display the Dashboard with all default widgets immediately post-login | TS_DASH_01, TS_DASH_02 | TC_DASH_001, TC_DASH_002 | Covered |
| BR-13 | Dashboard Quick Launch icons shall navigate correctly to respective modules | TS_DASH_03 | TC_DASH_003 | Covered |
| BR-14 | Dashboard shall display accurate Employee Distribution analytics (charts) | TS_DASH_04 | TC_DASH_004 | Covered |
| BR-15 | Dashboard shall provide access to all authorized top-level navigation modules | TS_DASH_05 | TC_DASH_005 | Covered |
| BR-16 | User profile dropdown shall display correct user identity and account actions | TS_DASH_06 | TC_DASH_006 | Covered |
| BR-17 | Dashboard shall render responsively across supported screen resolutions | TS_DASH_07 | TC_DASH_007 | Covered |
| BR-18 | "Employees on Leave Today" widget shall reflect accurate, real-time approved leave data | TS_DASH_02 | TC_DASH_008 | Covered |
| BR-19 | System shall allow adding a new employee record with mandatory fields (First/Last Name) | TS_PIM_ADD_01 | TC_PIM_ADD_001 | Covered |
| BR-20 | System shall support optional employee details (middle name, custom ID, photo) during creation | TS_PIM_ADD_02 | TC_PIM_ADD_002 | Covered |
| BR-21 | System shall enforce mandatory field validation on Add Employee form | TS_PIM_ADD_04 | TC_PIM_ADD_003, TC_PIM_ADD_004, TC_PIM_ADD_005 | Covered |
| BR-22 | System shall auto-generate a unique Employee ID and prevent duplicate manual IDs | TS_PIM_ADD_03, TS_PIM_ADD_05 | TC_PIM_ADD_006, TC_PIM_ADD_015 | Covered |
| BR-23 | System shall allow optional creation of ESS login credentials during employee creation, with password-match validation | TS_PIM_ADD_06, TS_PIM_ADD_07 | TC_PIM_ADD_007, TC_PIM_ADD_008 | Covered |
| BR-24 | Newly created employee shall be immediately visible/searchable in Employee List | TS_PIM_ADD_09 | TC_PIM_ADD_009 | Covered |
| BR-25 | System shall validate employee photo upload for format and file size constraints | TS_PIM_ADD_08 | TC_PIM_ADD_010, TC_PIM_ADD_011 | Covered |
| BR-26 | Name fields shall enforce character length and format (alphabetic) restrictions | TS_PIM_ADD_10, TS_PIM_ADD_11 | TC_PIM_ADD_012, TC_PIM_ADD_013 | Covered |
| BR-27 | Unsaved Add Employee form data shall not persist if the user navigates away without saving | TS_PIM_ADD_12 | TC_PIM_ADD_014 | Covered |
| BR-28 | System shall allow searching employees by Name (full/partial), Employee ID, and filter attributes | TS_PIM_SRCH_01–05, TS_PIM_SRCH_09 | TC_PIM_SRCH_001–005, TC_PIM_SRCH_009 | Covered |
| BR-29 | System shall correctly display "No Records Found" for non-matching searches | TS_PIM_SRCH_05 | TC_PIM_SRCH_006 | Covered |
| BR-30 | System shall allow resetting applied search filters | TS_PIM_SRCH_06 | TC_PIM_SRCH_007 | Covered |
| BR-31 | Search functionality shall be resilient to SQL Injection input | TS_PIM_SRCH_08 | TC_PIM_SRCH_008 | Covered |
| BR-32 | Search results table shall support pagination and column sorting | TS_PIM_SRCH_07 | TC_PIM_SRCH_010, TC_PIM_SRCH_011 | Covered |
| BR-33 | Search field shall gracefully handle whitespace-only input | TS_PIM_SRCH_08 | TC_PIM_SRCH_012 | Covered |
| BR-34 | System shall allow deleting a single or multiple employee record(s) with confirmation | TS_PIM_DEL_01, TS_PIM_DEL_02, TS_PIM_DEL_03 | TC_PIM_DEL_001, TC_PIM_DEL_003 | Covered |
| BR-35 | Deleted employee record shall be immediately removed from Employee List/search | TS_PIM_DEL_04 | TC_PIM_DEL_002 | Covered |
| BR-36 | System shall allow cancelling a delete action without data loss | TS_PIM_DEL_05 | TC_PIM_DEL_004 | Covered |
| BR-37 | Delete action with zero selected records shall be safely handled/disabled | TS_PIM_DEL_07 | TC_PIM_DEL_005 | Covered |
| BR-38 | Deleting an employee shall correctly cascade/handle dependent records (login accounts, leave history) | TS_PIM_DEL_06 | TC_PIM_DEL_006, TC_PIM_DEL_007 | Covered |
| BR-39 | Delete functionality shall be restricted based on user role/permission | TS_PIM_DEL_01 | TC_PIM_DEL_008 | Covered |
| BR-40 | System shall allow applying leave with valid Leave Type and date range | TS_LEAVE_01 | TC_LEAVE_001 | Covered |
| BR-41 | System shall validate that 'From Date' cannot be after 'To Date' | TS_LEAVE_02 | TC_LEAVE_002 | Covered |
| BR-42 | System shall enforce mandatory Leave Type selection | TS_LEAVE_03 | TC_LEAVE_003 | Covered |
| BR-43 | System shall handle past-dated leave applications per configured business rule | TS_LEAVE_04 | TC_LEAVE_004 | Covered |
| BR-44 | System shall support Half-Day leave application (Morning/Afternoon) | TS_LEAVE_05 | TC_LEAVE_005 | Covered |
| BR-45 | System shall allow optional comments on leave applications | TS_LEAVE_06 | TC_LEAVE_006 | Covered |
| BR-46 | Submitted leave shall correctly appear in "My Leave" with status "Pending Approval" | TS_LEAVE_07 | TC_LEAVE_007 | Covered |
| BR-47 | System shall handle overlapping leave date-range requests appropriately | TS_LEAVE_08 | TC_LEAVE_008 | Covered |
| BR-48 | Leave balance shall not be deducted until a leave request is approved | TS_LEAVE_09 | TC_LEAVE_009 | Covered |
| BR-49 | System shall allow cancellation of a pending leave request | TS_LEAVE_11 | TC_LEAVE_010 | Covered |
| BR-50 | System shall correctly compute leave days for long date ranges and single-day requests | TS_LEAVE_12 | TC_LEAVE_011, TC_LEAVE_012 | Covered |
| BR-51 | Leave calendar view shall accurately reflect applied leave | TS_LEAVE_10 | TC_LEAVE_013 | Covered |
| BR-52 | System shall validate against insufficient leave balance | TS_LEAVE_09 | TC_LEAVE_014 | Covered |

### RTM Coverage Summary

| Metric | Value |
|---|---|
| Total Business Requirements Identified | 52 |
| Total Requirements Covered by Test Cases | 52 |
| Requirement Coverage % | 100% |
| Total Test Scenarios | 46 |
| Total Test Cases | 77 |
| Modules Covered | Login, Dashboard, PIM (Add/Search/Delete), Leave (Apply) |

---
*End of Requirement Traceability Matrix — QA-RTM-OHRM-005*
