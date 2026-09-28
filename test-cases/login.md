# Test Cases – Login

Precondition for all cases: the login page `https://www.saucedemo.com` is open. Password for all users: `secret_sauce`.
Result = result with `standard_user` unless another user is named.

| ID | Title | Steps | Test data | Expected result | Priority | Result |
|---|---|---|---|---|---|---|
| TC-LOGIN-01 | Login with valid data | 1. Enter username<br>2. Enter password<br>3. Click **Login** | `standard_user` / `secret_sauce` | Products page opens, title is "Products" | High | ✅ Pass |
| TC-LOGIN-02 | Login with wrong password | 1. Enter username<br>2. Enter wrong password<br>3. Click **Login** | `standard_user` / `wrong` | Error: "Username and password do not match any user in this service". User stays on login page | High | ✅ Pass |
| TC-LOGIN-03 | Login with unknown username | Same as TC-LOGIN-02 | `unknown_user` / `secret_sauce` | Same error as TC-LOGIN-02 | Medium | ✅ Pass |
| TC-LOGIN-04 | Login with empty username | 1. Leave username empty<br>2. Enter password<br>3. Click **Login** | – / `secret_sauce` | Error: "Username is required" | Medium | ✅ Pass |
| TC-LOGIN-05 | Login with empty password | 1. Enter username<br>2. Leave password empty<br>3. Click **Login** | `standard_user` / – | Error: "Password is required" | Medium | ✅ Pass |
| TC-LOGIN-06 | Login with both fields empty | Click **Login** | – | Error: "Username is required" | Low | ✅ Pass |
| TC-LOGIN-07 | Locked user cannot log in | 1. Enter locked username<br>2. Enter password<br>3. Click **Login** | `locked_out_user` | Error: "Sorry, this user has been locked out." | High | ✅ Pass |
| TC-LOGIN-08 | Password field hides the text | Type a password | `secret_sauce` | Characters are masked | Medium | ✅ Pass |
| TC-LOGIN-09 | Error message can be closed | 1. Cause any login error<br>2. Click **X** on the error | – | Error message disappears, red field icons disappear | Low | ✅ Pass |
| TC-LOGIN-10 | Username is case sensitive | Log in with upper case username | `STANDARD_USER` | Login fails with the "do not match" error | Low | ✅ Pass |
| TC-LOGIN-11 | Login with Enter key | 1. Fill both fields<br>2. Press **Enter** | valid data | Products page opens | Low | ✅ Pass |
| TC-LOGIN-12 | Login time is acceptable | Log in and measure time until products are shown | `performance_glitch_user` vs `standard_user` | Login time similar for all users (< 3 s) | Medium | ❌ Fail → [BUG-011](../bug-reports/BUG-011-slow-login-performance-user.md) |
