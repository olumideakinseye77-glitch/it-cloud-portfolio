# Project 1 — Microsoft 365 Employee Lifecycle

[Portfolio home](../../README.md) · [Support project plan](../../SUPPORT-PROJECTS.md)

Status: core joiner/mover/leaver scenarios and missing-access exercise completed; unperformed checks remain explicit below. [Final handover](HANDOVER.md). See [validation progress](progress.md).
Company: Olu Office Services (fictional).

## Visual walkthrough

[View the employee lifecycle and troubleshooting diagrams](DIAGRAMS.md) — a visual guide to the completed work, three incidents and interview talking points.

## Business request

“We are a small company with Finance and Sales teams. New employees need email and access to their team's documents. Staff changing teams must lose unnecessary access, and leavers must no longer be able to sign in.”

## Access and scope

Use your own dedicated test tenant and fictional employees. Confirm licence availability for email, SharePoint and Teams before building; omit Teams and record the limitation if unavailable. Confirm trial expiry and billing settings. Keep the administrator account separate from ordinary employee accounts.

This is a cloud identity lab. It does not assume connection to the separate Windows domain lab.

## Assignment A — Sarah joins Finance

Agreed fictional requirements: Sarah needs email, MFA, and read/write access to Finance documents. Alex in Sales must have no access to Finance documents. Neither employee needs an administrator role.

- [x] Confirm administrator access and available licences.
- [x] Create Sarah's account.
- [x] Create Alex's test account (operator confirmed).
- [ ] Read back Sarah's and Alex's department fields.
- [x] Assign Sarah an available Business Premium licence.
- [x] Register Microsoft Authenticator for Sarah and test a fresh-session sign-in approval (operator confirmed).
- [ ] Establish and test MFA for Alex.
- [x] Create Finance Lab and change its privacy from Public to Private after an access test.
- [x] Review group membership/privacy; Sarah's access transitioned from Finance to Sales (operator confirmed).
- [x] Create and save the Finance Welcome document.
- [x] Test Sarah's sign-in, password change and internal email in both directions.
- [x] Test Sarah's Finance document read/write access after the privacy fix.
- [x] Test that Alex is denied access in a separate browser session.

Use separate browser sessions for administrator and employee tests. Record the method used for MFA and access management.

## Assignment B — Sarah moves to Sales

The manager confirms Sarah no longer needs Finance access. Update her department and membership, then verify Sales access and loss of Finance access. Check for direct permissions or shared links that could preserve unwanted access.

Department transfer performed and both access tests confirmed by the operator on 27 October 2026. See the validation record for evidence limits.

## Assignment C — Alex leaves

The manager requests immediate access removal. Document a retention and ownership decision before deleting data or removing licences. Block sign-in, revoke sessions, remove relevant memberships and verify the account's access state. Record service/session delays and any test you cannot complete. Blocking an account does not undo previously downloaded files.

## Incident — missing department access

After the healthy baseline is recorded, remove one test membership and investigate the resulting access problem. Capture the symptom, check the permission path, restore the intended membership and retest authorised plus unauthorised access.

## Acceptance evidence

| Test | Expected | Actual | Evidence |
| --- | --- | --- | --- |
| Sarah uses email | Test message sent and received | Passed — operator confirmed internal delivery both ways | [Validation record](progress.md) |
| Sarah completes MFA registration | Successful registration and a recorded challenge test | Passed — operator confirmed registration and Authenticator approval during fresh-session sign-in | [Validation record](progress.md) |
| Sarah edits Finance document | Allowed | Passed — operator confirmed edit/save and post-fix access | [Privacy incident](../../it-support/tickets/HD-002-finance-public-access.md) |
| Alex opens Finance document | Denied | Passed after Public-to-Private correction | [Privacy incident](../../it-support/tickets/HD-002-finance-public-access.md) |
| Sarah moves to Sales | Sales access allowed; Finance denied | Passed — operator confirmed Sales edit/save and Finance denial on 27 October 2026 | [Validation record](progress.md) |
| Alex leaves | Sign-in blocked; session-revocation action recorded | Passed — operator confirmed blocking, session sign-out, membership removal and fresh sign-in rejection on 27 October 2026 | [Validation record](progress.md) |
| Missing Sales access is repaired | Denial after membership removal; edit/save after restoration | Passed — operator confirmed controlled fault and recovery | [Membership incident](../../it-support/tickets/HD-003-sales-membership-recovery.md) |

## Deliverables

Create a joiner/mover/leaver checklist, a configuration summary, test evidence and one incident report using the [ticket template](../../it-support/tickets/TEMPLATE.md). Name evidence descriptively and redact personal details and credentials.

## Interview practice

Explain why access was assigned through groups, how you checked the employee experience, and why removing a licence alone is insufficient as a leaver workflow. Use your actual test results.

## Final review

The core scenarios are complete. Alex's MFA, independent department readback, complete sharing-link audit and evidence screenshots remain unfinished; they are not claimed as completed. See [handover](HANDOVER.md) for the checklist, CV wording, retention decision and evidence limits.
