# Test Execution Report – SauceDemo

| | |
|---|---|
| **Application** | https://www.saucedemo.com |
| **Test date** | 28 Sep 2026 |
| **Tester** | Deniz Akyol |
| **Browsers** | Chrome (latest), Firefox (latest) on Windows 11 |
| **Test plan** | [test-plan.md](test-plan.md) |

## Summary

All 40 test cases were run with `standard_user` in Chrome, and 34 of them were repeated in Firefox with the same result. The main flows work, but **2 defects affect every user** (empty-cart order, whitespace input).
Then the relevant test cases and exploratory sessions were run with the other test users. **12 defects** were found in total, **2 of them Critical**.

### standard_user

| Module | Test cases | Passed | Failed |
|---|---|---|---|
| Login | 12 | 12 | 0 |
| Products | 11 | 11 | 0 |
| Cart | 5 | 4 | 1 |
| Checkout | 9 | 8 | 1 |
| Session | 3 | 3 | 0 |
| **Total** | **40** | **38 (95%)** | **2** |

### Defects by user

| User | Login | Products | Cart / Checkout | Defects |
|---|---|---|---|---|
| `standard_user` | OK | OK | Empty-cart order, whitespace input | BUG-009, BUG-010 |
| `locked_out_user` | Blocked as expected | – | – | – |
| `problem_user` | OK | Wrong images, 3 products cannot be added, sorting broken | Last name goes into first name, checkout blocked | BUG-001, 002, 003, 004 |
| `error_user` | OK | 3 products cannot be added, remove broken, sort alert | Continues without last name, Finish does nothing | BUG-003, 004, 005, 006, 007, 008 |
| `performance_glitch_user` | ~3.5× slower | OK | OK | BUG-011 |
| `visual_user` | OK | Wrong prices, wrong image, layout problems | – | BUG-012 |

### Defects by severity

| Severity | Count | IDs |
|---|---|---|
| Critical | 2 | BUG-002, BUG-005 |
| High | 4 | BUG-003, BUG-006, BUG-009, BUG-012 |
| Medium | 5 | BUG-001, BUG-004, BUG-008, BUG-010, BUG-011 |
| Low | 1 | BUG-007 |

*BUG-001 has Medium severity but High priority, because the problem is visible on the first page.*

## Risks and recommendations

1. **Checkout is the weakest area.** 5 of 12 defects are in the cart / checkout flow, and both Critical defects block the order. Checkout should get regression tests first.
2. **Input validation is missing on the client side.** Empty cart and whitespace-only values are accepted. Server-side validation should be checked too.
3. **Price data must be the same for all users.** BUG-012 shows prices that change on every login. This should be fixed before any release.
4. **Add automated checks.** Login, add to cart and checkout are already covered in [playwright-bdd-e2e-framework](https://github.com/db-akyol/playwright-bdd-e2e-framework). The new defects above (empty cart, whitespace) are good candidates for new automated tests.

## Exit criteria

| Criterion | Status |
|---|---|
| All test cases run with `standard_user` | ✅ Done |
| All Critical / High defects reported with steps and evidence | ✅ Done |
| Test execution report written | ✅ Done |
