# E-Commerce Website – Functional & Manual Testing Project

[![Manual Testing](https://img.shields.io/badge/Testing-Manual%20%26%20Functional-blue.svg)](https://github.com/Jeelanimohammad/ecommerce-functional-testing)
[![Test Cases](https://img.shields.io/badge/Test%20Cases-30%20Designed%20%26%20Executed-green.svg)](test-cases/ecommerce_test_cases.csv)
[![Pass Rate](https://img.shields.io/badge/Pass%20Rate-86.7%25-brightgreen.svg)](test-reports/test_execution_summary.md)
[![Defects Found](https://img.shields.io/badge/Defects%20Identified-4%20Genuine%20Bugs-red.svg)](bug-reports/defects_found.csv)
[![QA Internship Ready](https://img.shields.io/badge/Role-QA%20Tester%20Internship-orange.svg)](README.md)

A comprehensive, end-to-end manual and functional testing project designed to demonstrate core Quality Assurance (QA) competencies for a QA Tester internship. This project covers real-world test scenario design, structured test case creation, hands-on test execution, defect lifecycle reporting, regression testing strategy, and test summary metric analysis on a live e-commerce platform.

---

## 1. Project Overview

In software development, manual testing is the foundation of quality engineering. Before automating test suites, a QA engineer must deeply understand application business logic, user journeys, edge cases, and failure modes.

This project validates the functional integrity of an e-commerce platform from the perspective of an end user and a quality analyst. Testing was conducted on a live, publicly accessible e-commerce application using test accounts and dummy information without financial transactions.

### Key Objectives
- Formulate structured **Test Scenarios** across core e-commerce modules.
- Author **30 detailed Test Cases** covering positive, negative, boundary value, and usability paths.
- Execute test cases against live endpoints and document **Actual Results** vs **Expected Results**.
- Identify, verify, and log **4 genuine defects** with reproduction steps, severity, and priority ratings.
- Formulate a **Regression Testing Strategy** to validate code changes after defect resolution.
- Compile a formal **Test Execution Summary Report** with quantitative pass/fail metrics.

---

## 2. Application Under Test (AUT)

- **Application Name**: Automation Exercise
- **Website URL**: [https://automationexercise.com](https://automationexercise.com)
- **Application Type**: Full-fledged B2C E-Commerce web application built for QA engineers and testing practitioners.
- **Environment**: Desktop Web (Google Chrome 129.0 on Windows 11, Viewport 1920x1080)
- **Credentials Used**: Test dummy account (`alex_test_qa99@mailinator.com` / `Password@123`)

### Core Features Verified on the Application
1. **User Authentication**: User registration with profile metadata, duplicate email validation, login authentication, and secure session termination.
2. **Product Catalog**: Product grid browsing, category accordion filters (Women > Tops), brand filtering, and product specification detail views.
3. **Product Search**: Keyword-based search query execution and case-insensitivity checks.
4. **Shopping Cart Management**: Adding items from catalog or detail pages, custom quantity input, cart persistence across page reloads, multi-item price computation, and single/all item deletion.
5. **Checkout Workflow**: Guest user authentication gateway, address verification (delivery & billing), order item review, dummy payment processing (card number, CVC, expiry), and order confirmation.

---

## 3. Testing Scope & Exclusions

| In-Scope Modules | Description |
| :--- | :--- |
| **User Authentication & Profile** | Registration workflow, mandatory field validation, duplicate email prevention, login with valid/invalid credentials, logout session kill. |
| **Product Discovery & Navigation** | Catalog display, product details view, category filtering, search input queries, case insensitivity. |
| **Shopping Cart Operations** | Add-to-cart modal, quantity multiplication, arithmetic accuracy, item deletion, empty cart state handling. |
| **Checkout & Order Placement** | Address propagation from profile, order review table, payment form validation, dummy card processing, confirmation banner. |
| **Session & Navigation** | Navigation responsiveness, session persistence across browser refreshes, footer email newsletter subscription. |

### Out-of-Scope (Exclusions)
- **Live Monetary Transactions**: No real bank accounts or credit cards were used. All checkout testing utilized dummy credit card tokens.
- **Database Backend Testing**: Direct SQL queries or database modification (black-box functional testing methodology was used).
- **Non-Functional Testing**: Performance/load stress testing under high traffic, and penetration/vulnerability security testing.

---

## 4. Testing Methodologies & Techniques Applied

- **Black-Box Testing**: Testing the system strictly against requirements without inspecting internal source code.
- **Positive Testing**: Verifying that the system behaves as expected under valid inputs (e.g., valid credentials, legitimate product search).
- **Negative Testing**: Intentionally providing invalid, unexpected, or missing inputs to confirm appropriate error handling (e.g., wrong password, blank payment fields, duplicate email).
- **Boundary Value Analysis (BVA)**: Testing extreme ends of input ranges (e.g., entering quantity `0` or `-1` vs. positive integers).
- **Usability & Accessibility Testing**: Verifying keyboard navigation (Enter key submission on search) and user feedback on zero-result states.
- **Regression Testing**: Re-verifying dependent modules and upstream workflows when bug fixes are deployed.

---

## 5. Repository Structure

```text
ecommerce-functional-testing/
│
├── README.md                           # Main project documentation & overview
│
├── test-cases/
│   └── ecommerce_test_cases.csv        # 30 complete test cases with execution status
│
├── bug-reports/
│   ├── defect_report_template.csv      # Standard industry defect logging template
│   └── defects_found.csv               # 4 genuine reproducible defects documented
│
├── test-reports/
│   └── test_execution_summary.md       # Metrics, module breakdown, regression strategy
│
└── screenshots/
    └── README.md                       # Test evidence & screenshot capture guide
```

---

## 6. Test Case Coverage Matrix

A total of **30 test cases** were designed and executed. The table below outlines the distribution across application modules:

| Test ID Range | Module | Scenario Count | Positive Tests | Negative / Boundary | Usability |
| :--- | :--- | :---: | :---: | :---: | :---: |
| `TC_AUTH_01` – `TC_AUTH_04` | Authentication | 4 | 2 | 2 | 0 |
| `TC_PROD_01` – `TC_PROD_03` | Product Catalog | 3 | 3 | 0 | 0 |
| `TC_SRCH_01` – `TC_SRCH_04` | Product Search | 4 | 2 | 1 | 1 |
| `TC_CART_01` – `TC_CART_09` | Shopping Cart | 9 | 7 | 2 | 0 |
| `TC_CHK_01` – `TC_CHK_07` | Checkout & Payment | 7 | 6 | 1 | 0 |
| `TC_NAV_01` – `TC_NAV_03` | Navigation & Session | 3 | 2 | 0 | 1 |
| **Total** | **All Modules** | **30** | **22** | **6** | **2** |

The full spreadsheet is available in [test-cases/ecommerce_test_cases.csv](test-cases/ecommerce_test_cases.csv).

---

## 7. Actual Test Execution Summary

Every designed test case was manually executed on the live demo website.

| Status | Count | Percentage | Formula |
| :--- | :---: | :---: | :--- |
| **Passed** | 26 | 86.7% | `(26 / 30) * 100` |
| **Failed** | 4 | 13.3% | `(4 / 30) * 100` |
| **Blocked** | 0 | 0.0% | `(0 / 30) * 100` |
| **Not Run** | 0 | 0.0% | `(0 / 30) * 100` |
| **Total Executed** | **30** | **100.0%** | `(30 / 30) * 100` |

Detailed module-wise metrics and calculation formulas are documented in [test-reports/test_execution_summary.md](test-reports/test_execution_summary.md).

---

## 8. Defects Identified & Bug Reports

During test execution, **4 genuine, reproducible defects** were uncovered. No simulated or artificial defects were logged.

| Bug ID | Module | Defect Title | Severity | Priority | Status |
| :---: | :--- | :--- | :---: | :---: | :---: |
| **BUG_01** | Product Search | Search bar does not submit on keyboard 'Enter' key press | Medium | Medium | Open |
| **BUG_02** | Product Search | Blank search results screen without feedback message on non-existent query | Low | Medium | Open |
| **BUG_03** | Shopping Cart | Product details accepts '0' and negative quantities into cart session | High | High | Open |
| **BUG_04** | Navigation | Aggressive full-screen overlay ads intercept user navigation clicks | Low | Low | Open |

### Understanding Severity vs. Priority
- **Severity** measures the technical impact of a defect on application functionality or business logic.
  - *Example*: `BUG_03` (High Severity) allows users to put 0 or negative items into the cart, which corrupts financial arithmetic and order totals.
- **Priority** measures the urgency with which a defect must be resolved from a business and release timeline perspective.
  - *Example*: `BUG_03` is also High Priority because cart corruption directly jeopardizes transactions. Conversely, `BUG_02` (blank search state) is Low Severity because the system does not crash, but Medium Priority because it causes user confusion.

The complete defect logs with detailed steps to reproduce are available in [bug-reports/defects_found.csv](bug-reports/defects_found.csv).

---

## 9. Regression Testing Walkthrough

When developers push code fixes, previously passed features must be retested to ensure no unintended side effects were introduced.

### Practical Example: Resolving BUG_03 (Quantity Validation)
1. **Developer Fix**: The developer adds validation on the product details page enforcing `quantity >= 1`.
2. **Defect Retesting (`TC_CART_03`)**: Enter `0` and `-1` into quantity box; verify system now displays validation message and prevents adding to cart. Status moves from `Fail` to `Pass`.
3. **Component Regression (`TC_CART_02`)**: Enter valid quantity `4`; verify legitimate increments still function correctly.
4. **Downstream Workflow Regression (`TC_CART_05`, `TC_CART_06`, `TC_CHK_04`)**: Add valid items to cart and proceed to Checkout; verify cart line items, subtotal calculations, and order summary remain accurate.

---

## 10. How to Export Spreadsheets to CSV & Sync with GitHub

To maintain this project in Excel or Google Sheets and publish updates to GitHub:

### In Google Sheets / Microsoft Excel
1. Create or edit your test cases in Excel / Google Sheets with the standard 10 columns:
   `Test Case ID`, `Module`, `Test Scenario`, `Preconditions`, `Test Steps`, `Test Data`, `Expected Result`, `Actual Result`, `Status`, `Remarks`.
2. Export as CSV:
   - **Google Sheets**: File > Download > Comma Separated Values (`.csv`).
   - **Microsoft Excel**: File > Save As > Choose `CSV UTF-8 (Comma delimited) (*.csv)`.
3. Save the exported file into the local repository folder under `test-cases/ecommerce_test_cases.csv`.

### Syncing to GitHub via Terminal
```bash
# Check modified files
git status

# Stage the updated CSV or markdown files
git add test-cases/ecommerce_test_cases.csv bug-reports/defects_found.csv

# Commit with a clear QA message
git commit -m "qa: update test case execution results and defect logs"

# Push changes to your main branch
git push origin main
```

---

## 11. Key Skills Demonstrated for QA Internship

1. **Test Scenario & Test Case Design**: Translating business requirements into structured, testable verification steps.
2. **Black-Box Testing Techniques**: Implementing Boundary Value Analysis (BVA), Equivalence Partitioning concepts, and Error Guessing.
3. **Defect Lifecycle Management**: Documenting reproducible bug reports with precise environment details, expected vs. actual outcomes, severity, and priority.
4. **Analytical Reporting**: Computing execution metrics, pass/fail percentages, and summarizing release readiness.
5. **Version Control & Collaboration**: Maintaining clean Git repositories, structured documentation, and CSV data formatting.