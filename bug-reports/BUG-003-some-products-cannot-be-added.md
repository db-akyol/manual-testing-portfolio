# BUG-003: 3 of 6 products cannot be added to the cart

| Field | Value |
|---|---|
| **ID** | BUG-003 |
| **Module** | Products |
| **Severity** | High |
| **Priority** | High |
| **Affected user** | problem_user, error_user |
| **Environment** | Chrome (latest) / Windows 11, 1280×800 |
| **URL** | https://www.saucedemo.com |
| **Reported** | 28 Sep 2026 · Deniz Akyol |
| **Status** | Open |

## Preconditions

Logged in as `problem_user` or `error_user`

## Steps to reproduce

1. On the Products page click **Add to cart** on every product
2. Look at the buttons and the cart badge

## Expected result

All 6 buttons change to **Remove**, cart badge shows 6.

## Actual result

Only Backpack, Bike Light and Onesie are added. For Bolt T-Shirt, Fleece Jacket and Test.allTheThings() T-Shirt (Red) nothing happens. Badge shows 3.

## Notes

The same 3 products fail for both users.
