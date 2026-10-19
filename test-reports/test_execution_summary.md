# Test Execution Summary Report

**Project**: E-Commerce Website – Functional & Manual Testing  
**Application Under Test (AUT)**: Automation Exercise ([https://automationexercise.com](https://automationexercise.com))  
**QA Tester**: Alex Tester (QA Intern Candidate)  
**Execution Date**: October 2026  
**Test Cycle**: Cycle 1 – Initial Functional & End-to-End Execution  
**Environment**: Google Chrome 129.0 on Windows 11 (Desktop Viewport 1920x1080)  

---

## 1. Executive Summary

This report summarizes the results of the manual functional testing cycle performed on the **Automation Exercise** e-commerce platform. A total of **30 comprehensive test cases** were designed and executed, spanning user authentication, product catalog browsing, search & filtering, shopping cart management, end-to-end checkout, and session navigation.

The application demonstrated robust stability in core business logic including user registration, session login, catalog display, multi-item price computation, and dummy payment completion. However, **4 genuine defects** were uncovered, primarily related to search keyboard usability, unhandled zero-state search queries, input validation on product quantities, and aggressive ad overlay interruptions.

---

## 2. Test Execution Metrics

### Overall Test Execution Status Table

| Metric | Count | Percentage |
| :--- | :--- | :--- |
| **Total Test Cases Executed** | **30** | **100.0%** |
| **Passed Test Cases** | **26** | **86.7%** |
| **Failed Test Cases** | **4** | **13.3%** |
| **Blocked Test Cases** | **0** | **0.0%** |
| **Not Run Test Cases** | **0** | **0.0%** |

### How Metrics are Calculated
- **Pass Rate (%)** = `(Passed Test Cases / Total Executed Test Cases) * 100`  
  *Calculation*: `(26 / 30) * 100 = 86.67%`
- **Fail Rate (%)** = `(Failed Test Cases / Total Executed Test Cases) * 100`  
  *Calculation*: `(4 / 30) * 100 = 13.33%`
- **Execution Rate (%)** = `((Passed + Failed + Blocked) / Total Designed Cases) * 100`  
  *Calculation*: `(30 / 30) * 100 = 100.0%`

---

## 3. Module-Wise Test Execution Breakdown

| Module Name | Total Cases | Passed | Failed | Blocked | Pass Rate (%) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Authentication & Account** | 4 | 4 | 0 | 0 | 100% |
| **Product Catalog & Filters** | 3 | 3 | 0 | 0 | 100% |
| **Product Search** | 4 | 2 | 2 | 0 | 50% |
| **Shopping Cart Management** | 9 | 8 | 1 | 0 | 88.9% |
| **Checkout & Dummy Payment** | 7 | 7 | 0 | 0 | 100% |
| **Navigation & Session** | 3 | 2 | 1 | 0 | 66.7% |
| **Total** | **30** | **26** | **4** | **0** | **86.7%** |

---

## 4. Defect Summary & Distribution

A total of **4 genuine defects** were logged during test execution. All defects have been documented with reproduction steps in [`bug-reports/defects_found.csv`](file:///c:/Users/JEELANI/Downloads/1661/bug-reports/defects_found.csv).

### Severity vs. Priority Matrix

| Severity \ Priority | High | Medium | Low | Total |
| :--- | :---: | :---: | :---: | :---: |
| **Critical** | 0 | 0 | 0 | **0** |
| **High** | 1 (BUG_03) | 0 | 0 | **1** |
| **Medium** | 0 | 1 (BUG_01) | 0 | **1** |
| **Low** | 0 | 1 (BUG_02) | 1 (BUG_04) | **2** |
| **Total** | **1** | **2** | **1** | **4** |

### List of Logged Defects

1. **BUG_01** (`Medium` Severity, `Medium` Priority):  
   *Title*: Product Search Bar Fails to Trigger on Keyboard 'Enter' Key Press.  
   *Impact*: Impacts user experience and keyboard accessibility; requires mouse click.
2. **BUG_02** (`Low` Severity, `Medium` Priority):  
   *Title*: Blank Search Results Screen Without Feedback Message on Non-Existent Product Query.  
   *Impact*: Leaves customers confused about whether the system froze or no products matched.
3. **BUG_03** (`High` Severity, `High` Priority):  
   *Title*: Product Details Page Accepts 0 and Negative Quantities into Cart Session.  
   *Impact*: Business logic integrity risk; allows corrupted zero-item lines in cart and checkout.
4. **BUG_04** (`Low` Severity, `Low` Priority):  
   *Title*: Aggressive Full-Screen Overlay Ads Intercept User Navigation Clicks.  
   *Impact*: Free-tier hosting ad integration disrupts navigation flow.

---

## 5. Scope of Testing & Exclusions

### In-Scope
- User signup and login authentication workflows (positive, negative, and duplicate validation).
- Product listing, category accordion navigation, and product detail views.
- Keyword product search (positive, case-insensitivity, keyboard events, zero-result handling).
- Shopping cart operations (adding single/multiple items, quantity updates, unit price multiplication, single-item deletion, empty cart boundary).
- Checkout workflow (guest checkout prompt, logged-in user address propagation, order review, dummy credit card payment validation, and order confirmation).
- Session logout and subscription form verification.

### Out-of-Scope / Exclusions
- **Real Financial Transactions**: Real credit cards, bank accounts, and live payment gateways (only dummy test data was utilized).
- **Backend Database Direct Manipulation**: Direct SQL queries or database table modification (black-box manual testing only).
- **Automated Performance / Load Testing**: Stress testing concurrent users or API response latency under load.
- **Security Penetration Testing**: SQL injection, XSS exploitation, or network packet sniffing.

---

## 6. Regression Testing Strategy & Demonstration

### What is Regression Testing?
Regression testing is the process of re-running functional and non-functional tests to ensure that previously tested code still functions correctly after a software change (such as a bug fix, new feature addition, or configuration update).

### How to Select Regression Test Cases
When a developer fixes a defect, a QA tester selects test cases based on:
1. **Defect Verification Test**: The exact test case that originally failed.
2. **Directly Impacted Feature Tests**: Test cases testing the same module or component.
3. **Downstream Workflow Tests**: Test cases that rely on the modified component (e.g., changes to cart quantity impact cart total and checkout calculations).
4. **Core Smoke Tests**: High-priority happy path test cases that verify critical business flows (login, catalog browse, checkout).

### Regression Testing Example: Fixing BUG_03 (Product Quantity Validation)
Suppose the development team deploys a fix for **BUG_03** by adding client-side and server-side validation that enforces `quantity >= 1`:

| Step | Action | Test Case ID | Expected Outcome |
| :--- | :--- | :--- | :--- |
| **1. Defect Verification** | Retest quantity input with `0` and `-1` on product details page | `TC_CART_03` | System prevents submission and displays error: "Please enter a quantity of 1 or greater". Status moves from **Fail -> Pass**. |
| **2. Module Regression** | Verify valid quantity update (e.g., entering `4`) | `TC_CART_02` | Ensure the fix did not break legitimate quantity increases. Item adds with quantity 4. |
| **3. Downstream Regression** | Verify cart table display and total price calculation | `TC_CART_05`, `TC_CART_06` | Total price correctly calculates `Unit Price * 4` without arithmetic errors. |
| **4. End-to-End Regression** | Proceed through Checkout and Place Order | `TC_CHK_02`, `TC_CHK_04`, `TC_CHK_07` | Ensure that the order review table and checkout summary process the validated item smoothly. |

---

## 7. Limitations & Challenges Encountered

1. **Third-Party Banner Advertisements**:  
   Because Automation Exercise is a publicly hosted free testing site, third-party Google vignette overlays occasionally popped up between page navigations. Testers had to manually close these interstitials to resume testing.
2. **Stateless Demo Reset**:  
   Public demo sites periodically refresh or purge dummy user accounts, requiring fresh registration data generation during extended test runs.
3. **Simulated Payment Gateway**:  
   The payment page accepts arbitrary dummy card numbers without connecting to real merchant banking networks, meaning banking-level 3D-Secure / OTP flows could not be tested.

---

## 8. Final Conclusion & Recommendation

The application successfully passed **86.7%** of its test scenarios. The critical user journey—browsing catalog items, adding them to the cart, reviewing address information, and completing checkout—is functional and stable.

**Release Recommendation**:  
- The core functionality is **Conditionally Acceptable**.
- Before promoting the application to a production environment, the **High Severity defect BUG_03** (quantity boundary validation) and **BUG_01** (keyboard accessibility for search) must be resolved and verified through a dedicated regression test cycle.
