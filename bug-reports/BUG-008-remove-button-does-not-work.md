# BUG-008: Remove button on the Products page does not remove the product

| Field | Value |
|---|---|
| **ID** | BUG-008 |
| **Module** | Products |
| **Severity** | Medium |
| **Priority** | Medium |
| **Affected user** | error_user |
| **Environment** | Chrome (latest) / Windows 11, 1280×800 |
| **URL** | https://www.saucedemo.com |
| **Reported** | 28 Sep 2026 · Deniz Akyol |
| **Status** | Open |

## Preconditions

Logged in as `error_user`

## Steps to reproduce

1. Click **Add to cart** on Sauce Labs Backpack
2. Click **Remove** on the same product

## Expected result

Button changes back to **Add to cart**, cart badge decreases by 1.

## Actual result

Button still shows **Remove**, the product stays in the cart.

## Notes

Workaround: remove the product on the cart page.
