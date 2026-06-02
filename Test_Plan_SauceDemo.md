# Test Plan - Swag Labs (SauceDemo) Web Application

**Functional & End-to-End Manual Testing**

| Field | Value |
|---|---|
| Document ID | TP-SAUCEDEMO-001 |
| Version | 1.0 |
| Application Under Test | Swag Labs storefront - https://www.saucedemo.com |
| Prepared by | Zurabi Mardaleishvili - Manual QA Tester |
| Standard alignment | ISTQB CTFL v4.0 - IEEE 829 test plan structure |
| Status | Portfolio sample |

---

## 1. Introduction

This test plan defines the scope, approach, resources, and schedule for manually testing the Swag Labs (SauceDemo) e-commerce web application. SauceDemo simulates a simple online store with authentication, a product catalogue, a shopping cart, and a multi-step checkout flow. The goal of this effort is to verify that a user can reliably authenticate, browse and sort products, manage the cart, and complete a purchase end to end, while surfacing any functional, usability, or data-integrity defects.

The plan is organised around ISTQB CTFL v4.0 principles and follows the IEEE 829 test plan layout so that any stakeholder - developer, product owner, or fellow tester - can quickly understand what will be tested, how, and to what acceptance bar.

## 2. Test Objectives

- Confirm that valid users can log in and that invalid, locked-out, and empty credentials are handled with correct error messaging.
- Verify the product catalogue displays correctly and that sorting (name and price, ascending and descending) behaves as specified.
- Validate add-to-cart, remove-from-cart, and cart badge counts across the catalogue, item detail, and cart pages.
- Exercise the full checkout flow - customer information, order overview, payment/shipping summary, totals, and order completion.
- Validate field-level input handling, mandatory-field enforcement, and price/tax/total calculations.
- Identify, document, and prioritise defects with clear, reproducible reports.

## 3. Scope

### 3.1 In Scope

| Module | Coverage |
|---|---|
| Authentication | Valid login, invalid credentials, locked-out user, empty fields, logout, session behaviour |
| Product Catalogue | Product listing, item details, images, sort dropdown (A-Z, Z-A, price low-high, high-low) |
| Shopping Cart | Add/remove items, cart badge count, cart contents, navigation to and from cart |
| Checkout | Customer information form, mandatory-field validation, order overview, item total, tax, total, order completion |
| Navigation & UI | Hamburger menu (All Items, About, Logout, Reset App State), header/footer links, cross-browser rendering |

### 3.2 Out of Scope

- Performance, load, and stress testing (beyond noting obvious slow-loading behaviour).
- Security/penetration testing and back-end API contract testing.
- Native mobile applications (responsive web rendering is in scope; native apps are not).
- Automated regression suites (this engagement is manual; automation can be quoted separately).

## 4. Test Approach & Techniques

Testing combines requirements-based functional testing with experience-based exploratory sessions. Black-box test-design techniques are applied to keep coverage efficient and traceable:

| Technique | Applied to |
|---|---|
| Equivalence Partitioning (EP) | Login credentials, postal-code and name fields - valid vs invalid partitions |
| Boundary Value Analysis (BVA) | Field length limits, empty/minimum inputs on the checkout form |
| Decision Tables | Login outcomes across user type × password combinations |
| State Transition | Cart and checkout flow: empty cart -> items added -> information -> overview -> complete |
| Exploratory Testing | Time-boxed charters on catalogue and checkout to find issues structured cases miss |

## 5. Test Environment

| Item | Detail |
|---|---|
| Application URL | https://www.saucedemo.com |
| Browsers | Google Chrome (latest), Mozilla Firefox (latest), Microsoft Edge (latest) |
| Operating systems | Windows 11, macOS |
| Resolutions | 1920×1080 (desktop), 1366×768 (laptop), responsive widths down to 375 px |
| Test data - password | `secret_sauce` (shared across all demo accounts) |
| Test data - accounts | `standard_user`, `locked_out_user`, `problem_user`, `performance_glitch_user` |
| Tools | Browser DevTools (inspection), JIRA (defect tracking), TestRail (test management) |

## 6. Entry & Exit Criteria

### 6.1 Entry Criteria

- Application is reachable and the login page loads in all target browsers.
- Test data (demo accounts and password) is confirmed working.
- Test cases are reviewed and the environment is configured.

### 6.2 Exit Criteria

- 100% of planned test cases executed; at least 95% passed.
- No open Critical or High-severity defects remain in core flows (login, cart, checkout).
- All defects are logged, triaged, and either fixed-and-retested or formally accepted by the stakeholder.
- Test summary report delivered.

## 7. Test Deliverables

- This test plan.
- Test case suite (functional cases with steps, test data, and expected results).
- Defect reports with severity, priority, reproduction steps, and evidence.
- Test summary report (executed vs passed/failed, defect breakdown, and release recommendation).

## 8. Risks & Mitigations

| Risk | Mitigation |
|---|---|
| Demo environment data resets mid-session | Use 'Reset App State' deliberately; capture evidence immediately on failure |
| Intentional demo defects masking real findings | Maintain a known-issues list per account; distinguish seeded behaviour from genuine defects |
| Browser-specific rendering differences | Run core flows across all target browsers; log rendering issues with screenshots |

## 9. Indicative Schedule

| Phase | Activity | Effort |
|---|---|---|
| Planning | Review requirements, write test plan and cases | 0.5 day |
| Execution | Run functional cases + exploratory charters | 1.5 days |
| Reporting | Log defects, retest fixes, write summary report | 0.5 day |
