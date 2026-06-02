# Test Summary Report - Swag Labs (SauceDemo) Web Application

| Field | Value |
|---|---|
| Document ID | TSR-SAUCEDEMO-001 |
| Version | 1.0 |
| Application | https://www.saucedemo.com |
| Test cycle | Functional & End-to-End Manual Testing |
| References | TP-SAUCEDEMO-001 (Test Plan), Test Case Suite, BUG-SAUCEDEMO-014 |
| Prepared by | Zurabi Mardaleishvili - Manual QA Tester |
| Status | Portfolio sample |

---

## 1. Executive Summary

A full cycle of manual functional and end-to-end testing was completed against the Swag Labs (SauceDemo) web application, covering authentication, the product catalogue, the shopping cart, and the checkout flow. Of 24 planned test cases, 23 passed and 1 failed, giving a 95.8% pass rate.

All core revenue-path flows - login, cart management, and checkout - passed in full. One Major defect was found in the product catalogue (BUG-SAUCEDEMO-014): product images do not render distinctly. **The application is recommended for release with this known issue tracked, provided the defect is scheduled for a prompt fix.**

| Total Cases | Passed | Failed | Blocked | Pass Rate |
|---|---|---|---|---|
| 24 | 23 | 1 | 0 | 95.8% |

## 2. Scope of Testing

- **Authentication:** valid login, invalid credentials, locked-out user, mandatory-field validation, and logout.
- **Product Catalogue:** product listing, item detail, image rendering, and all four sort options.
- **Shopping Cart:** add/remove items, cart badge counts, and cart contents.
- **Checkout:** customer information form, mandatory-field validation, order overview, totals, and order completion.

## 3. Results by Module

| Module | Cases | Pass | Fail | Pass Rate |
|---|---|---|---|---|
| Authentication | 6 | 6 | 0 | 100% |
| Product Catalogue | 7 | 6 | 1 | 85.7% |
| Shopping Cart | 5 | 5 | 0 | 100% |
| Checkout | 6 | 6 | 0 | 100% |
| **Total** | **24** | **23** | **1** | **95.8%** |

## 4. Defect Summary

One defect was raised during the cycle. No Critical, High-count, or core-flow defects remain open.

| Severity | Critical | Major | Minor | Notes |
|---|---|---|---|---|
| Open defects | 0 | 1 | 0 | All in non-core (catalogue) module |

### Open defect detail

| Bug ID | Summary | Severity | Status |
|---|---|---|---|
| BUG-SAUCEDEMO-014 | Product thumbnails on the catalogue all render the same image instead of each item's own (linked to TC-CAT-07). | Major | Open |

## 5. Exit Criteria Assessment

| Criterion | Met? | Evidence |
|---|---|---|
| 100% of planned cases executed | Yes | 24 / 24 run |
| At least 95% of cases passed | Yes | 95.8% |
| No open Critical/High defects in core flows (login, cart, checkout) | Yes | Core flows 100% pass |
| All defects logged and triaged | Yes | 1 logged |

## 6. Known Issues & Risks

- **Catalogue image rendering (BUG-SAUCEDEMO-014):** shoppers cannot visually distinguish products. Functional purchase path is unaffected, but the browsing experience is degraded. Recommend a prompt fix and a regression check asserting unique image URLs per product.
- The defect was reproduced on a specific account path; correct rendering on the standard path helps isolate the cause to image-source resolution.

## 7. Release Recommendation

**CONDITIONAL GO.** All core flows and exit criteria are satisfied. The application can be released with BUG-SAUCEDEMO-014 documented as a known issue, on the condition that it is scheduled for a fix in the next iteration and re-verified before closure.

## 8. Sign-off

| Role | Name | Date |
|---|---|---|
| QA Tester | Zurabi Mardaleishvili | |
| Reviewer / Client | | |
