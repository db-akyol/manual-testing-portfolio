# Test Cases – Cart and Checkout

Precondition for all cases: user is logged in.
Checkout test data (valid): First name `Deniz`, Last name `Akyol`, Postal code `21000`.
Result = result with `standard_user` unless another user is named.

## Cart

| ID | Title | Steps | Expected result | Priority | Result |
|---|---|---|---|---|---|
| TC-CART-01 | Cart shows added products | 1. Add 2 products<br>2. Click cart icon | Both products are listed with quantity 1 and correct price | High | ✅ Pass |
| TC-CART-02 | Remove product in cart | 1. Add a product<br>2. Open cart<br>3. Click **Remove** | Product is removed, badge disappears | High | ✅ Pass |
| TC-CART-03 | Continue shopping | In cart click **Continue Shopping** | Products page opens, cart is not changed | Medium | ✅ Pass |
| TC-CART-04 | Cart is kept after page refresh | 1. Add a product<br>2. Refresh the page | Badge still shows 1 | Medium | ✅ Pass |
| TC-CART-05 | Checkout is not possible with an empty cart | 1. Open cart with no products<br>2. Click **Checkout** | Checkout is blocked or a message says the cart is empty | High | ❌ Fail → [BUG-009](../bug-reports/BUG-009-order-with-empty-cart.md) |

## Checkout – information form

| ID | Title | Steps | Test data | Expected result | Priority | Result |
|---|---|---|---|---|---|---|
| TC-CHK-01 | Continue with valid data | 1. Add a product → cart → **Checkout**<br>2. Fill the form<br>3. Click **Continue** | valid data | Overview page opens | High | ✅ Pass · ❌ Fail (`problem_user`) → [BUG-002](../bug-reports/BUG-002-last-name-overwrites-first-name.md) |
| TC-CHK-02 | First name is required | Leave first name empty, click **Continue** | – | "Error: First Name is required" | High | ✅ Pass |
| TC-CHK-03 | Last name is required | Leave last name empty, click **Continue** | – | "Error: Last Name is required" | High | ✅ Pass · ❌ Fail (`error_user`) → [BUG-006](../bug-reports/BUG-006-checkout-continues-without-last-name.md) |
| TC-CHK-04 | Postal code is required | Leave postal code empty, click **Continue** | – | "Error: Postal Code is required" | High | ✅ Pass |
| TC-CHK-05 | Whitespace-only values are rejected | Enter only spaces in all fields, click **Continue** | `"   "` | Required field errors are shown | Medium | ❌ Fail → [BUG-010](../bug-reports/BUG-010-whitespace-accepted-in-checkout.md) |
| TC-CHK-06 | Cancel on information page | Click **Cancel** | – | Cart page opens | Low | ✅ Pass |

## Checkout – overview and finish

| ID | Title | Steps | Expected result | Priority | Result |
|---|---|---|---|---|---|
| TC-CHK-07 | Totals are correct | 1. Add Backpack ($29.99) and Bike Light ($9.99)<br>2. Go to overview | Item total $39.98, tax $3.20, total $43.18 | High | ✅ Pass |
| TC-CHK-08 | Finish order | On overview click **Finish** | "Thank you for your order!" is shown, cart is empty | High | ✅ Pass · ❌ Fail (`error_user`) → [BUG-005](../bug-reports/BUG-005-finish-button-does-nothing.md) |
| TC-CHK-09 | Back home after order | On complete page click **Back Home** | Products page opens, all buttons show **Add to cart** | Medium | ✅ Pass |

## Session

| ID | Title | Steps | Expected result | Priority | Result |
|---|---|---|---|---|---|
| TC-SES-01 | Logout | Menu → **Logout** | Login page opens | High | ✅ Pass |
| TC-SES-02 | Pages are protected after logout | 1. Logout<br>2. Open `/inventory.html` directly | Error: "You can only access '/inventory.html' when you are logged in." | High | ✅ Pass |
| TC-SES-03 | Reset app state | 1. Add products<br>2. Menu → **Reset App State** | Cart badge disappears | Low | ✅ Pass |
