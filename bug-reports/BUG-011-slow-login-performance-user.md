# BUG-011: Login takes about 3.5 times longer for performance_glitch_user

| Field | Value |
|---|---|
| **ID** | BUG-011 |
| **Module** | Login |
| **Severity** | Medium |
| **Priority** | Low |
| **Affected user** | performance_glitch_user |
| **Environment** | Chrome (latest) / Windows 11, 1280×800 |
| **URL** | https://www.saucedemo.com |
| **Reported** | 28 Sep 2026 · Deniz Akyol |
| **Status** | Open |

## Preconditions

Login page is open

## Steps to reproduce

1. Log in as `standard_user` and measure the time until the product list is shown
2. Log out
3. Log in as `performance_glitch_user` and measure again

## Expected result

Login time is similar for both users (under 3 seconds).

## Actual result

`standard_user`: about 2.1 s. `performance_glitch_user`: about 7.1 s (same browser and network).

## Notes

No error, only delay. Users may click the button again or leave the site.
