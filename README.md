🧪 OrangeHRM QA Testing Project — Manual & Functional Testing Portfolio
![Testing](https://img.shields.io/badge/Testing-Manual%20%7C%20Functional-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Standard](https://img.shields.io/badge/Standard-IEEE%20829%20%7C%20ISO%2029119-orange)
![Application](https://img.shields.io/badge/AUT-OrangeHRM-red)
A complete, industry-standard QA documentation package built around the OrangeHRM Open Source Demo application — created to demonstrate real-world Manual Testing, Functional Testing, and Test Management skills at the level expected in IT services organizations (Accenture, TCS, Cognizant, Infosys, and similar).
---
📌 Project Overview
This repository simulates a complete QA engagement lifecycle for an HRMS (Human Resource Management System) web application — from requirement analysis and test planning through test design, execution documentation, defect reporting, and traceability — exactly as a Senior QA Engineer would deliver in a client project.
Application Under Test (AUT): OrangeHRM Demo
Demo Credentials: `Username: Admin` | `Password: admin123`
The project covers the full QA documentation suite required for:
Client audits & QA process compliance (IEEE 829 / ISO 29119 aligned)
Interview portfolio demonstration
Team onboarding / knowledge transfer reference
---
🗂️ Repository Structure
```
OrangeHRM-QA-Project/
│
├── README.md                 → This file
├── Test\\\_Plan.md               → Detailed Test Plan (IEEE 829 format)
├── Test\\\_Scenarios.md          → High-level test scenarios per module
├── Test\\\_Cases.xlsx            → 77 detailed test cases (Positive/Negative/Boundary) across 6 modules
├── Bug\\\_Reports.md             → Sample defect reports with severity/priority \\\& defect lifecycle
├── RTM.md                     → Requirement Traceability Matrix (100% coverage)
└── Resume\\\_Content.md          → Ready-to-use resume/portfolio project description
```
---
🎯 Modules Covered
#	Module	Coverage
1	Login / Authentication	Valid/invalid login, validations, session handling, security (SQLi/XSS), boundary testing
2	Dashboard	Widget validation, navigation, responsiveness, real-time data widgets
3	PIM — Add Employee	Mandatory fields, duplicate ID handling, login-details creation, photo upload validation
4	PIM — Search Employee	Name/ID/filter-based search, pagination, sorting, SQL injection resilience
5	PIM — Delete Employee	Single/bulk delete, confirmation flow, cascading dependency checks, role-based restriction
6	Leave — Apply Leave	Date validations, half-day leave, balance rules, pending/cancel lifecycle, boundary scenarios
Total Test Artifacts: 46 Test Scenarios · 77 Test Cases · 52 Traced Requirements · 5 Sample Defect Reports
---
🛠️ Tools & Techniques Used
Category	Tools / Techniques
Test Documentation	IEEE 829, Markdown, Excel
Test Design Techniques	Equivalence Partitioning, Boundary Value Analysis, Decision Table Testing, State Transition Testing
Test Types Practiced	Smoke, Sanity, Functional, Regression, Integration, E2E, Negative, Security (basic), Cross-Browser
Defect Management	Jira-style defect lifecycle (New → Assigned → Fixed → Retest → Closed)
Browsers Validated	Google Chrome, Mozilla Firefox, Microsoft Edge
Version Control	Git & GitHub
(Future Scope) Automation	Selenium WebDriver, Cypress, Postman (API)
---
▶️ How to Execute This Test Suite
Access the Application
Navigate to: `https://opensource-demo.orangehrmlive.com/web/index.php/auth/login`
Login credentials: `Admin / admin123`
Review Planning Artifacts
Start with `Test\\\_Plan.md` to understand scope, strategy, and environment setup.
Walk Through Scenarios
Refer to `Test\\\_Scenarios.md` for the high-level "what to test" checklist per module.
Execute Detailed Test Cases
Open `Test\\\_Cases.xlsx`. Each module has its own sheet with step-by-step instructions, test data, and expected results. Execute manually against the live application and fill in the Actual Result and Status (Pass/Fail/Blocked/Not Executed) columns.
Log Defects
For any mismatch between Expected and Actual Result, log a defect using the format shown in `Bug\\\_Reports.md`.
Verify Coverage
Cross-check `RTM.md` to confirm every business requirement maps to at least one executed test case.
(Optional) Regression Cycle
After defect fixes, re-execute the High/Critical priority test cases marked in `Test\\\_Cases.xlsx` as a regression pass.
---
🧠 Skills Demonstrated
✅ Test Planning as per IEEE 829 / ISO 29119 standards
✅ Functional, System, Integration, Regression, Smoke & Sanity Testing
✅ End-to-End Business Flow validation across multiple HR modules
✅ Test Case Design using Equivalence Partitioning & Boundary Value Analysis
✅ Positive, Negative & Boundary test case authoring
✅ Defect Lifecycle Management & professional bug reporting (Severity/Priority classification)
✅ Requirement Traceability Matrix (RTM) creation for audit-ready coverage
✅ Agile/Scrum-aligned QA documentation practices
✅ Basic security testing awareness (SQL Injection, XSS on input fields)
✅ Cross-browser & responsive UI validation approach
✅ Professional QA documentation suitable for enterprise client delivery
---
👤 Author
[Dolly Harode]
QA Engineer | Manual & Functional Tester
📧 dollyharode.work@gmail.com | 🔗 www-linkdin-dollyharode
> This project was created as an independent QA portfolio exercise using OrangeHRM's publicly available open-source demo instance for educational and demonstrative purposes. It is not affiliated with or endorsed by OrangeHRM Inc.
---
📄 License
This documentation is shared for educational and portfolio purposes. Feel free to fork and adapt the structure for your own QA practice projects.
⭐ If this repository helped you understand professional QA documentation struc
