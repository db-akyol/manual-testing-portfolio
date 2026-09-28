# BUG-004: Product sorting does not change the order

| Field | Value |
|---|---|
| **ID** | BUG-004 |
| **Module** | Products |
| **Severity** | Medium |
| **Priority** | Medium |
| **Affected user** | problem_user, error_user |
| **Environment** | Chrome (latest) / Windows 11, 1280×800 |
| **URL** | https://www.saucedemo.com |
| **Reported** | 28 Sep 2026 · Deniz Akyol |
| **Status** | Open |

## Preconditions

Logged in as `problem_user` or `error_user`

## Steps to reproduce

1. Select **Name (Z to A)** in the sort dropdown

## Expected result

First product is "Test.allTheThings() T-Shirt (Red)".

## Actual result

`problem_user`: the list does not change. `error_user`: a browser alert is shown (see BUG-007) and the list does not change.

## Notes

Checked with Price (low to high) too: same result.
