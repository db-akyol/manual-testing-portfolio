# BUG-007: Sorting shows a technical error alert to the user

| Field | Value |
|---|---|
| **ID** | BUG-007 |
| **Module** | Products |
| **Severity** | Low |
| **Priority** | Low |
| **Affected user** | error_user |
| **Environment** | Chrome (latest) / Windows 11, 1280×800 |
| **URL** | https://www.saucedemo.com |
| **Reported** | 28 Sep 2026 · Deniz Akyol |
| **Status** | Open |

## Preconditions

Logged in as `error_user`

## Steps to reproduce

1. Select any option in the sort dropdown

## Expected result

Products are sorted. If there is an error, a friendly message is shown in the page.

## Actual result

A native browser alert with a technical text is shown: "Sorting is broken! This error has been reported to Backtrace."

## Notes

Related to BUG-004. Reported separately because the error handling itself is a UX problem.
