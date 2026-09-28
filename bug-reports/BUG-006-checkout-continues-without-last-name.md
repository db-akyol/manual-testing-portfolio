# BUG-006: Last Name field does not accept input, but the form continues anyway

| Field | Value |
|---|---|
| **ID** | BUG-006 |
| **Module** | Checkout |
| **Severity** | High |
| **Priority** | Medium |
| **Affected user** | error_user |
| **Environment** | Chrome (latest) / Windows 11, 1280×800 |
| **URL** | https://www.saucedemo.com |
| **Reported** | 28 Sep 2026 · Deniz Akyol |
| **Status** | Open |

## Preconditions

Logged in as `error_user`, one product in the cart

## Steps to reproduce

1. Cart → **Checkout**
2. Enter First Name, Last Name and Postal Code
3. Look at the Last Name field
4. Click **Continue**

## Expected result

Last Name keeps the typed value. If it is empty, "Error: Last Name is required" is shown.

## Actual result

Last Name stays empty after typing, and **Continue** opens the overview page without a validation error.

## Notes

Two problems: the input does not work, and required field validation is skipped. An order without a last name can be created.
