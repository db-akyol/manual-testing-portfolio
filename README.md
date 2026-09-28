# Manual Testing Portfolio – SauceDemo

![Test cases](https://img.shields.io/badge/test_cases-40-blue)
![Bugs](https://img.shields.io/badge/bugs_reported-12-red)
![Critical](https://img.shields.io/badge/critical-2-darkred)

Manual testing work for the [SauceDemo](https://www.saucedemo.com) e-commerce demo site: a test plan, written test cases, bug reports with evidence and a test execution report.

SauceDemo has several test users, and some of them have defects on purpose. This repo shows how I plan the testing, write test cases, find defects with the same cases for different users, and report them so a developer can reproduce them.

## Contents

| Document | What is inside |
|---|---|
| [Test plan](test-plan.md) | Scope, approach, environments, entry / exit criteria, severity levels, risks |
| [Test cases – Login](test-cases/login.md) | 12 cases: valid / invalid login, required fields, locked user, performance |
| [Test cases – Products](test-cases/products.md) | 11 cases: product list, images, prices, sorting, add / remove, detail page |
| [Test cases – Cart and Checkout](test-cases/cart-and-checkout.md) | 17 cases: cart, form validation, totals, finish order, session |
| [Bug reports](bug-reports/) | 12 bug reports with steps, expected / actual result and screenshots |
| [Test execution report](test-execution-report.md) | Results, defects by user and severity, recommendations |
| [Templates](templates/) | Bug report and test case templates |

## Bugs found

| ID | Title | Module | Severity | User |
|---|---|---|---|---|
| [BUG-001](bug-reports/BUG-001-wrong-product-images.md) | All product images show the same wrong picture | Products | Medium | `problem_user` |
| [BUG-002](bug-reports/BUG-002-last-name-overwrites-first-name.md) | Typing in Last Name changes First Name, checkout is blocked | Checkout | **Critical** | `problem_user` |
| [BUG-003](bug-reports/BUG-003-some-products-cannot-be-added.md) | 3 of 6 products cannot be added to the cart | Products | High | `problem_user`, `error_user` |
| [BUG-004](bug-reports/BUG-004-sorting-does-not-work.md) | Product sorting does not change the order | Products | Medium | `problem_user`, `error_user` |
| [BUG-005](bug-reports/BUG-005-finish-button-does-nothing.md) | Finish button does nothing, order cannot be completed | Checkout | **Critical** | `error_user` |
| [BUG-006](bug-reports/BUG-006-checkout-continues-without-last-name.md) | Last Name field does not accept input, but the form continues anyway | Checkout | High | `error_user` |
| [BUG-007](bug-reports/BUG-007-error-user-sort-alert.md) | Sorting shows a technical error alert to the user | Products | Low | `error_user` |
| [BUG-008](bug-reports/BUG-008-remove-button-does-not-work.md) | Remove button on the Products page does not remove the product | Products | Medium | `error_user` |
| [BUG-009](bug-reports/BUG-009-order-with-empty-cart.md) | Order can be completed with an empty cart | Cart / Checkout | High | `standard_user` |
| [BUG-010](bug-reports/BUG-010-whitespace-accepted-in-checkout.md) | Checkout form accepts values that contain only spaces | Checkout | Medium | `standard_user` |
| [BUG-011](bug-reports/BUG-011-slow-login-performance-user.md) | Login takes about 3.5 times longer for performance_glitch_user | Login | Medium | `performance_glitch_user` |
| [BUG-012](bug-reports/BUG-012-wrong-prices-visual-user.md) | Wrong product prices and broken layout for visual_user | Products | High | `visual_user` |

BUG-009 and BUG-010 were found with `standard_user`, so they affect every user.

## Example

[BUG-002](bug-reports/BUG-002-last-name-overwrites-first-name.md): the user types "Akyol" into Last Name, but the text goes into First Name and the order cannot continue.

![BUG-002](screenshots/bug-problem-user-checkout.png)

## How I worked

1. Read the site and wrote the [test plan](test-plan.md): scope, users, severity levels.
2. Wrote test cases per module with clear steps, test data and expected results.
3. Ran all cases with `standard_user` in Chrome and repeated most of them in Firefox.
4. Ran the same cases and short exploratory sessions with the other test users.
5. Checked that every defect can be reproduced, took screenshots and wrote a bug report.
6. Summarised results and risks in the [execution report](test-execution-report.md).

## Related automation projects

- [playwright-bdd-e2e-framework](https://github.com/db-akyol/playwright-bdd-e2e-framework): the main SauceDemo flows as automated BDD tests
- [api-test-automation](https://github.com/db-akyol/api-test-automation): REST API tests with Playwright and Postman
