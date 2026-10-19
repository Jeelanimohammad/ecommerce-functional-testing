# Test Evidence & Screenshot Guidelines

This directory houses visual evidence captured during manual test execution and defect reporting for the **Automation Exercise** e-commerce platform.

---

## 1. Purpose of Test Evidence in Manual QA

In professional software testing, visual evidence serves as indisputable proof of:
- **Defect Reproducibility**: Demonstrating the exact visual state of the application when a defect occurs so developers can understand and resolve it immediately.
- **Audit & Compliance**: Verifying that critical test cases (such as checkout, payment processing, and user registration) were successfully validated against real environments.
- **Cross-Browser Verification**: Showing visual layout rendering across different viewports and browser engines.

---

## 2. Screenshot Naming Convention

To keep the project clean, professional, and well-organized, adhere strictly to the standardized naming structure:

### For Defect Evidence
```text
BUG_<BugID>_<short_description>.png
```
*Examples:*
- `BUG_01_search_enter_key_failure.png`
- `BUG_02_empty_search_zero_feedback.png`
- `BUG_03_zero_negative_quantity_accepted.png`
- `BUG_04_ad_overlay_interception.png`

### For Successful Execution Evidence (Milestones)
```text
TC_<TestCaseID>_pass_<feature_milestone>.png
```
*Examples:*
- `TC_AUTH_01_pass_account_created.png`
- `TC_CHK_07_pass_order_confirmed.png`

---

## 3. Recommended Screenshot Capture Tools

| Tool | Shortcut / Access | Best Use Case | Cost |
| :--- | :--- | :--- | :--- |
| **Windows Snipping Tool** | `Win + Shift + S` | Quick rectangular capture with built-in highlighter & pen | Free (Built-in) |
| **Google Chrome DevTools** | `Ctrl + Shift + P` -> "Capture full size screenshot" | Full-page vertical scrolling captures | Free (Built-in) |
| **ShareX / Lightshot** | Custom Hotkey | Instant crop, text callouts, numbered step circles, arrows | Free / Open-Source |

---

## 4. Best Practices for Professional QA Evidence

1. **Highlight the Anomaly**: Use red boxes or arrows to draw attention to the specific defect area (e.g., the blank search container, 0 quantity in cart).
2. **Include Context**: Always capture the URL bar and navigation breadcrumbs to confirm page location and environment.
3. **Protect Sensitive Data**: Never include real credit card numbers, passwords, or personal PII. Use dummy data only (`alex_test_qa99@mailinator.com`, dummy card `4111 1111 1111 1111`).
4. **Optimal File Formats**: Save screenshots as `.png` or `.jpg` with compression to keep repository sizes light.

---

## 5. Mapping of Documented Defects to Evidence

| Bug ID | Module | Defect Description | Evidence File Reference |
| :--- | :--- | :--- | :--- |
| **BUG_01** | Product Search | Search bar does not submit on keyboard Enter key | `screenshots/BUG_01_search_enter_key_failure.png` |
| **BUG_02** | Product Search | Non-existent search query yields blank screen with zero feedback | `screenshots/BUG_02_empty_search_zero_feedback.png` |
| **BUG_03** | Shopping Cart | Product details accepts '0' or negative quantity into cart | `screenshots/BUG_03_zero_negative_quantity_accepted.png` |
| **BUG_04** | Navigation | Full-screen Google vignette ad overlays intercept menu clicks | `screenshots/BUG_04_ad_overlay_interception.png` |

---

*Note: In accordance with clean repository standards, only necessary evidence and genuine defect documentation is stored here to prevent repository bloat.*
