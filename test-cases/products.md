# Test Cases – Products (Inventory)

Precondition for all cases: user is logged in and on the Products page.
Result = result with `standard_user` unless another user is named.

| ID | Title | Steps | Test data | Expected result | Priority | Result |
|---|---|---|---|---|---|---|
| TC-PROD-01 | Product list is shown | Open Products page | – | 6 products, each with name, description, price, image and **Add to cart** button | High | ✅ Pass |
| TC-PROD-02 | Each product has the correct image | Compare each image with the product name | all users | Image matches the product | Medium | ❌ Fail (`problem_user`, `visual_user`) → [BUG-001](../bug-reports/BUG-001-wrong-product-images.md) |
| TC-PROD-03 | Prices are correct | Compare prices with the catalogue (standard user) | `visual_user` | Same prices for every user | High | ❌ Fail → [BUG-012](../bug-reports/BUG-012-wrong-prices-visual-user.md) |
| TC-PROD-04 | Sort by name Z → A | Select **Name (Z to A)** | – | First product is "Test.allTheThings() T-Shirt (Red)" | Medium | ✅ Pass · ❌ Fail (`problem_user`, `error_user`) → [BUG-004](../bug-reports/BUG-004-sorting-does-not-work.md) |
| TC-PROD-05 | Sort by price low → high | Select **Price (low to high)** | – | First product $7.99, last $49.99 | Medium | ✅ Pass |
| TC-PROD-06 | Sort by price high → low | Select **Price (high to low)** | – | First product $49.99 | Medium | ✅ Pass |
| TC-PROD-07 | Add every product to cart | Click **Add to cart** on all 6 products | – | Every button changes to **Remove**, cart badge shows 6 | High | ✅ Pass · ❌ Fail (`problem_user`, `error_user`) → [BUG-003](../bug-reports/BUG-003-some-products-cannot-be-added.md) |
| TC-PROD-08 | Remove product from the list | 1. Add a product<br>2. Click **Remove** | – | Button changes to **Add to cart**, badge decreases | High | ✅ Pass · ❌ Fail (`error_user`) → [BUG-008](../bug-reports/BUG-008-remove-button-does-not-work.md) |
| TC-PROD-09 | Open product detail | Click a product name | Sauce Labs Backpack | Detail page shows same name, description and price | Medium | ✅ Pass |
| TC-PROD-10 | Back from product detail | On detail page click **Back to products** | – | Products page opens, cart state is kept | Low | ✅ Pass |
| TC-PROD-11 | Page layout is correct | Check header, cart icon and product cards | `visual_user` | Elements are aligned like for `standard_user` | Low | ❌ Fail → [BUG-012](../bug-reports/BUG-012-wrong-prices-visual-user.md) |
