# Test Case Template

| Field | Description |
|---|---|
| **ID** | TC-<MODULE>-<NUMBER>, e.g. TC-LOGIN-01 |
| **Title** | One short sentence: what is checked |
| **Preconditions** | State before step 1 |
| **Steps** | Numbered actions, one action per step |
| **Test data** | Exact values used |
| **Expected result** | Observable result that decides pass or fail |
| **Priority** | High / Medium / Low |
| **Type** | Positive / Negative / Boundary / UI |
| **Result** | Pass / Fail (+ bug ID) / Blocked / Not run |

## Example

| ID | Title | Steps | Test data | Expected result | Priority | Result |
|---|---|---|---|---|---|---|
| TC-LOGIN-02 | Login with wrong password | 1. Enter username<br>2. Enter wrong password<br>3. Click **Login** | `standard_user` / `wrong` | Error "Username and password do not match any user in this service" | High | Pass |
