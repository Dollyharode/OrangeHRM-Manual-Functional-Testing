# DEFECT / BUG REPORTS
## Project: OrangeHRM Web Application | Doc Ref: QA-BUG-OHRM-004 | Version 1.0

These are **sample illustrative defect reports**, formatted in the same style used in Jira/HP ALM at MNC QA teams, based on typical exploratory findings and common edge-case behaviors observed while testing HRMS-type applications. They demonstrate the reporter's ability to write clear, reproducible, well-triaged defects following standard **Defect Life Cycle** practice (New → Assigned → Open → Fixed → Retest → Closed / Reopened).

> Note: Since the demo environment resets periodically and behavior may vary by build/version, these reports should be validated against the live build before being treated as confirmed defects in a real engagement. They are included here to demonstrate defect-writing proficiency.

---

### BUG_ID: OHRM-BUG-001

| Field | Detail |
|---|---|
| **Title** | Login page does not indicate which field (username/password) failed the field-level "Required" validation clearly when both fields are submitted empty simultaneously on first attempt |
| **Module** | Login / Authentication |
| **Severity** | Low |
| **Priority** | Low |
| **Environment** | Chrome v127, Windows 11, https://opensource-demo.orangehrmlive.com |
| **Reported By** | Senior QA Engineer |
| **Status** | New |
| **Steps to Reproduce** | 1. Navigate to the Login page.<br>2. Without entering any value, click the 'Login' button directly. |
| **Expected Result** | Both Username and Password fields should immediately display clear, distinctly visible 'Required' inline validation messages so the user does not need to click again to see both. |
| **Actual Result** | Validation messages appear but may be visually subtle / require the user to notice small red text below both fields; no field is auto-focused to draw attention. |
| **Attachments** | Screenshot_Login_Blank_Submit.png |
| **Suggested Fix** | Auto-focus the first invalid field and consider a summary banner for multiple validation errors to improve usability. |

---

### BUG_ID: OHRM-BUG-002

| Field | Detail |
|---|---|
| **Title** | Employee photo upload allows file selection dialog to accept files above documented size limit before showing the size-validation error only after form submission |
| **Module** | PIM — Add Employee |
| **Severity** | Medium |
| **Priority** | Medium |
| **Environment** | Chrome v127, Windows 11 |
| **Reported By** | Senior QA Engineer |
| **Status** | New |
| **Steps to Reproduce** | 1. Navigate to PIM > Add Employee.<br>2. Click on the photo upload placeholder.<br>3. Select an image file larger than 1MB (e.g., 4MB .jpg).<br>4. Observe behavior immediately after selection, then attempt to Save. |
| **Expected Result** | The oversized file should be rejected immediately upon selection with a clear, immediate inline error, preventing wasted user effort filling the rest of the form. |
| **Actual Result** | The oversized image preview may briefly appear accepted; the size-limit error is only surfaced at Save time, which is a delayed feedback loop for the user. |
| **Attachments** | Screenshot_PhotoUpload_SizeIssue.png |
| **Suggested Fix** | Perform client-side file-size validation immediately on file selection (onChange event) rather than only at submit. |

---

### BUG_ID: OHRM-BUG-003

| Field | Detail |
|---|---|
| **Title** | Applying leave allows selecting a 'To Date' before validating against 'From Date' in real time, resulting in a submit-time-only error instead of inline calendar restriction |
| **Module** | Leave — Apply Leave |
| **Severity** | Medium |
| **Priority** | Medium |
| **Environment** | Chrome v127, Windows 11 |
| **Reported By** | Senior QA Engineer |
| **Status** | New |
| **Steps to Reproduce** | 1. Navigate to Leave > Apply.<br>2. Select Leave Type.<br>3. Set 'From Date' to 25-Sep-2026.<br>4. Set 'To Date' to 20-Sep-2026 (earlier than From Date).<br>5. Click 'Apply'. |
| **Expected Result** | The 'To Date' calendar picker should disable/restrict dates earlier than the selected 'From Date' to prevent an invalid selection at the UI level. |
| **Actual Result** | The system allows selecting an earlier 'To Date' and only throws the validation error after the user clicks 'Apply', requiring rework. |
| **Attachments** | Screenshot_Leave_DateValidation.png |
| **Suggested Fix** | Implement dynamic calendar constraint: disable all dates before the selected 'From Date' in the 'To Date' picker. |

---

### BUG_ID: OHRM-BUG-004

| Field | Detail |
|---|---|
| **Title** | Deleting an employee record with an associated system user login does not clearly inform the admin that the linked login account will also be affected |
| **Module** | PIM — Delete Employee / Admin Integration |
| **Severity** | High |
| **Priority** | High |
| **Environment** | Chrome v127, Windows 11 |
| **Reported By** | Senior QA Engineer |
| **Status** | New |
| **Steps to Reproduce** | 1. Add a new employee and enable 'Create Login Details' with a valid username/password.<br>2. Save the employee.<br>3. Navigate to PIM > Employee List.<br>4. Delete the same employee record.<br>5. Navigate to Admin > User Management > System Users and search for the associated username. |
| **Expected Result** | The delete confirmation dialog should explicitly warn the admin that this employee has an associated system login which will also be impacted/removed, requiring explicit acknowledgment. |
| **Actual Result** | The standard generic delete confirmation ("Are you sure you want to delete the selected record?") is shown with no mention of the linked login account impact, which could lead to unintended access-management side effects. |
| **Attachments** | Screenshot_Delete_LinkedUser.png |
| **Suggested Fix** | Add a contextual warning message in the delete confirmation dialog when the target employee record has an active linked system user account. |

---

### BUG_ID: OHRM-BUG-005

| Field | Detail |
|---|---|
| **Title** | Employee Name search field on PIM > Employee List does not trim leading/trailing whitespace before executing search, causing valid partial matches to sometimes return "No Records Found" |
| **Module** | PIM — Search Employee |
| **Severity** | Low |
| **Priority** | Low |
| **Environment** | Firefox v129, Windows 11 |
| **Reported By** | Senior QA Engineer |
| **Status** | New |
| **Steps to Reproduce** | 1. Navigate to PIM > Employee List.<br>2. In the 'Employee Name' field, enter a valid employee name with a trailing space, e.g., "John Doe " (with trailing space).<br>3. Click 'Search'. |
| **Expected Result** | The system should trim leading/trailing whitespace automatically and return the matching 'John Doe' record. |
| **Actual Result** | Depending on build, the search may fail to match and return 'No Records Found' due to the untrimmed trailing space being included in the query. |
| **Attachments** | Screenshot_Search_Whitespace.png |
| **Suggested Fix** | Apply `.trim()` on the search input value before constructing the search query on both client and server side. |

---

## Defect Severity & Priority Definitions (Reference)

| Severity | Definition |
|---|---|
| **Blocker** | Application crashes, or a core workflow (e.g., Login) is completely unusable; no workaround exists |
| **Critical** | Major functionality broken with significant business impact; workaround may exist but is impractical |
| **High** | Important functionality impaired; workaround exists but is inconvenient |
| **Medium** | Moderate impact; a feature does not behave as expected but does not block core workflows |
| **Low** | Cosmetic/UI issue, or minor inconvenience with negligible business impact |

| Priority | Definition |
|---|---|
| **P1 – Urgent** | Must be fixed immediately before further testing/release |
| **P2 – High** | Should be fixed in the current release cycle |
| **P3 – Medium** | Can be scheduled for a subsequent release |
| **P4 – Low** | Fix as time permits; cosmetic/nice-to-have |

## Defect Life Cycle Followed

```
New → Assigned → Open (In Progress) → Fixed → Retest (by QA)
                                          ├── Pass → Closed
                                          └── Fail → Reopened → Assigned (loop)

Additional states: Deferred (postponed to future release), Duplicate, Not a Bug, Cannot Reproduce
```

---
*End of Bug Reports Document — QA-BUG-OHRM-004*
