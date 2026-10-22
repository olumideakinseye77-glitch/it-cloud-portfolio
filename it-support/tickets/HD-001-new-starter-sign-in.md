# HD-001 — New Starter Cannot Sign In

Date: 22 October 2026
Environment: independent Microsoft 365 lab
User: Sarah Jones (fictional)
Status: resolved — operator-confirmed sign-in and password change
Category: incident

## Reported problem

A newly created and licensed account displayed: “Your account or password is incorrect.”

## Impact

One new starter could not access Microsoft 365. No wider outage or production impact was established.

## Investigation

- Get-MgUser output confirmed that Sarah's account existed.
- Set-MgUserLicense returned a successful response for Business Premium.
- The sign-in instructions used Sarah's full user principal name in a separate browser session.
- The initial credential attempt failed.

## Resolution

The lab administrator reset Sarah's password through the Microsoft 365 Admin Centre. The operator then signed in as Sarah and completed the required password change.

## Verification

The operator confirmed successful sign-in, Outlook inbox access and internal email delivery in both directions with the lab administrator.

## Root cause

Not established. Resetting the credentials resolved access, but does not establish whether the original failure was caused by a typing error, an incorrectly retained password or another condition. Sign-in logs were not collected.

## Communication

“Your account is accessible following the password reset. Sign-in, password change and internal email have been tested.”

This is a simulated user update, not a message sent to another person.

## Escalation criteria

If sign-in continued to fail, collect the exact error and time, confirm account status and username, and inspect available sign-in evidence before escalating. Do not repeatedly reset passwords without checking the evidence.

## Lessons

Creating an account and assigning a licence are separate from testing the employee's sign-in. Keep temporary passwords private and verify the user's task after making a change.

Evidence basis: pasted command output and operator reports from the guided lab session; no production support claim.
