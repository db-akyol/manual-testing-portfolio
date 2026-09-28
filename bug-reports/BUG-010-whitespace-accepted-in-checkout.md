# BUG-010: Checkout form accepts values that contain only spaces

| Field | Value |
|---|---|
| **ID** | BUG-010 |
| **Module** | Checkout |
| **Severity** | Medium |
| **Priority** | Medium |
| **Affected user** | standard_user |
| **Environment** | Chrome (latest) / Windows 11, 1280×800 |
| **URL** | https://www.saucedemo.com |
| **Reported** | 28 Sep 2026 · Deniz Akyol |
| **Status** | Open |

## Preconditions

Logged in as `standard_user`, one product in the cart

## Steps to reproduce

1. Cart → **Checkout**
2. Enter 3 spaces in First Name, Last Name and Postal Code
3. Click **Continue**

## Expected result

Values are trimmed and the required field errors are shown.

## Actual result

The overview page opens. The order can be finished with empty-looking customer data.

## Notes

Validation checks only for an empty string, not for whitespace.
