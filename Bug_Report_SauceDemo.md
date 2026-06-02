# Defect Report

## BUG-SAUCEDEMO-014 - Product images do not render distinctly on the catalogue

| Field | Value |
|---|---|
| Bug ID | BUG-SAUCEDEMO-014 |
| Title | All product thumbnails render the same image instead of each item's own image |
| Application | Swag Labs - https://www.saucedemo.com |
| Module | Product Catalogue (inventory page) |
| Related Test Case | TC-CAT-07 |
| Severity | Major |
| Priority | High |
| Status | Open |
| Reported by | Zurabi Mardaleishvili (Manual QA) |
| Date reported | Portfolio sample |

## Environment

- **Browser:** Google Chrome (latest) - also reproduced in Firefox and Edge
- **OS:** Windows 11
- **Resolution:** 1920×1080
- **Account used:** `problem_user` / `secret_sauce`

## Description

On the product catalogue (inventory) page, every product thumbnail displays the same image rather than the image that corresponds to each individual product. Product names, descriptions, and prices are correct, but the images are not, which misrepresents the catalogue and would mislead a shopper choosing between items.

## Preconditions

- The application is reachable and the login page loads.
- Valid demo credentials for the affected account are available.

## Steps to Reproduce

1. Navigate to https://www.saucedemo.com.
2. Log in with username `problem_user` and password `secret_sauce`.
3. Observe the product thumbnails on the Products (inventory) page.
4. Compare each thumbnail against its product name and description.

## Expected Result

Each product displays its own distinct, correct image that matches the product name and description.

## Actual Result

All six products display an identical image. The image does not match the product names or descriptions, so the items are visually indistinguishable.

## Evidence

> <img width="2879" height="1283" alt="Screenshot 2026-06-03 000845" src="https://github.com/user-attachments/assets/b46f82b3-d8f2-4770-8114-a544ffdb95fc" />
<img width="2879" height="1279" alt="Screenshot 2026-06-03 010845" src="https://github.com/user-attachments/assets/35bd89ad-377f-4b42-9feb-b281d11acb23" />
<img width="2861" height="1284" alt="Screenshot 2026-06-03 010933" src="https://github.com/user-attachments/assets/ce1e496c-6c45-43d5-8169-982f559add50" />
<img width="2876" height="1287" alt="Screenshot 2026-06-03 011033" src="https://github.com/user-attachments/assets/c0840847-85b8-48f1-ab62-f0ecc62f512e" />





## Impact

Users cannot visually identify or differentiate products, which undermines the core browsing experience, reduces trust, and is likely to lower conversion. Although the functional purchase flow still works, the catalogue is the primary decision surface, so the defect is rated **Major / High** priority.
