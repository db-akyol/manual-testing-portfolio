# Test Plan – SauceDemo (Swag Labs)

| | |
|---|---|
| **Application** | [SauceDemo](https://www.saucedemo.com) – demo e-commerce web app |
| **Version / date** | Live site, tested on 28 Sep 2026 |
| **Author** | Deniz Akyol |

## 1. Goal

Check that a user can log in, find products, manage the cart and complete an order, and find the defects that block or damage these flows.

## 2. Scope

**In scope**

| Module | What is checked |
|---|---|
| Login | Valid / invalid login, locked user, required fields, error messages |
| Products (inventory) | Product list, images, prices, sorting, add / remove buttons, product detail |
| Cart | Cart badge, cart content, remove, continue shopping |
| Checkout | Information form and validation, overview and totals, finish order |
| Session | Logout, access to pages without login, reset app state |

**Out of scope**

- Payment integration (the site has no real payment)
- Security testing beyond access control of pages
- Load testing (only a simple response time comparison between users)

## 3. Test approach

- **Functional testing** with written test cases (positive and negative)
- **Exploratory testing** for each user type, 20–30 minute sessions
- **Boundary and input checks** on form fields (empty, whitespace, long text, special characters)
- **Cross-user comparison**: SauceDemo has several test users. The same test cases are run with each user to find user-specific defects.

| User | Purpose |
|---|---|
| `standard_user` | Normal user, main reference |
| `locked_out_user` | Blocked user |
| `problem_user` | User with UI problems |
| `performance_glitch_user` | User with slow responses |
| `error_user` | User with functional errors |
| `visual_user` | User with visual problems |

## 4. Test environment

| Item | Value |
|---|---|
| OS | Windows 11 |
| Browsers | Chrome (latest), Firefox (latest) |
| Screen | 1280×800 desktop |
| Tools | Browser DevTools, screenshots, Markdown for reports |

## 5. Entry and exit criteria

**Entry**

- The site is reachable
- Test users and password are known
- Test cases are reviewed

**Exit**

- All test cases are run at least once with `standard_user`
- All High / Critical defects are reported with steps and evidence
- A test execution report is written

## 6. Defect severity

| Severity | Meaning |
|---|---|
| Critical | Main flow is blocked, no workaround (e.g. order cannot be completed) |
| High | Main feature does not work correctly or wrong data is shown |
| Medium | Feature works partly or there is a workaround |
| Low | Cosmetic problem, small effect on the user |

## 7. Risks

| Risk | Mitigation |
|---|---|
| Public demo site may change | Date and screenshots are added to every report |
| Some defects appear only for one user | Same test cases are run with each user |

## 8. Deliverables

- [Test cases](test-cases/)
- [Bug reports](bug-reports/)
- [Test execution report](test-execution-report.md)
