# Screenshots Folder — Instructions

This folder must contain **real evidence** captured while executing the test cases in `Manual-Testing/OrangeHRM_Test_Cases.md` against the live application:
https://opensource-demo.orangehrmlive.com/web/index.php/auth/login

> ⚠️ Do not skip this. A QA portfolio without execution evidence looks AI-generated / theoretical to any recruiter or interviewer. This folder is what proves you actually *ran* the tests.

## What to Capture (Minimum Recommended Set — ~15–20 screenshots, not all 77)

Pick a representative mix across modules and result types:

| Category | Suggested Screenshots |
|---|---|
| **Login Module** | 1 valid login success (Dashboard loaded) + 1 invalid login error message + 1 blank-field validation |
| **PIM – Add Employee** | 1 successful add confirmation + 1 mandatory-field validation error |
| **PIM – Search Employee** | 1 successful search result + 1 "No Records Found" |
| **PIM – Delete Employee** | 1 delete confirmation popup + 1 post-delete "No Records Found" |
| **Leave – Apply Leave** | 1 successful leave submission + 1 date validation error (From > To) |
| **Dashboard** | 1 full dashboard view with widgets |
| **At least 1 Bug** | Screenshot of the actual defect being reproduced (matches a Bug ID in Bug-Reports) |

## Naming Convention

Name each file to match the related Test Case ID or Bug ID, so it's traceable:

```
TC_LOGIN_001_Pass.png
TC_LOGIN_002_Fail.png
TC_PIM_ADD_003_Validation.png
OHRM-BUG-003_Evidence.png
```

## How to Capture
- Use browser DevTools/OS screenshot tool (Win+Shift+S / Cmd+Shift+4)
- Crop to show the relevant field/message clearly — no need for full-screen browser chrome
- PNG format preferred over JPG for text clarity

Once captured, update the **Status** and **Actual Result** columns in `OrangeHRM_Test_Cases.md` to reference these screenshots, e.g.:
`Actual Result: Error displayed as expected. See Screenshots/TC_LOGIN_002_Fail.png`
