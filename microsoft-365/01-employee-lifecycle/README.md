# Project 1 — Microsoft 365 Employee Lifecycle

[Portfolio home](../../README.md) · [Support project plan](../../SUPPORT-PROJECTS.md)

Status: in progress — Sarah's account, sign-in, password change and internal email tested. See [validation progress](progress.md).
Company: Olu Office Services (fictional).

## Business request

“We are a small company with Finance and Sales teams. New employees need email and access to their team's documents. Staff changing teams must lose unnecessary access, and leavers must no longer be able to sign in.”

## Access and scope

Use your own dedicated test tenant and fictional employees. Confirm licence availability for email, SharePoint and Teams before building; omit Teams and record the limitation if unavailable. Confirm trial expiry and billing settings. Keep the administrator account separate from ordinary employee accounts.

This is a cloud identity lab. It does not assume connection to the separate Windows domain lab.

## Assignment A — Sarah joins Finance

Agreed fictional requirements: Sarah needs email, MFA, and read/write access to Finance documents. Alex in Sales must have no access to Finance documents. Neither employee needs an administrator role.

- [x] Confirm administrator access and available licences.
- [x] Create Sarah's account.
- [ ] Verify Sarah's department fields and create Alex's Sales account.
- [x] Assign Sarah an available Business Premium licence.
- [ ] Establish and test MFA registration for the test accounts.
- [ ] Create department groups and a private Finance document area.
- [ ] Grant Finance access through group membership.
- [ ] Add a fictional welcome document.
- [x] Test Sarah's sign-in, password change and internal email in both directions.
- [ ] Test Sarah's Finance document read/write access.
- [ ] Test that Alex is denied access.

Use separate browser sessions for administrator and employee tests. Record the method used for MFA and access management.

## Assignment B — Sarah moves to Sales

The manager confirms Sarah no longer needs Finance access. Update her department and membership, then verify Sales access and loss of Finance access. Check for direct permissions or shared links that could preserve unwanted access.

## Assignment C — Alex leaves

The manager requests immediate access removal. Document a retention and ownership decision before deleting data or removing licences. Block sign-in, revoke sessions, remove relevant memberships and verify the account's access state. Record service/session delays and any test you cannot complete. Blocking an account does not undo previously downloaded files.

## Incident — missing department access

After the healthy baseline is recorded, remove one test membership and investigate the resulting access problem. Capture the symptom, check the permission path, restore the intended membership and retest authorised plus unauthorised access.

## Acceptance evidence

| Test | Expected | Actual | Evidence |
| --- | --- | --- | --- |
| Sarah uses email | Test message sent and received | Passed — operator confirmed internal delivery both ways | [Validation record](progress.md) |
| Sarah completes MFA registration | Successful registration and a recorded challenge test | Pending | Pending |
| Sarah edits Finance document | Allowed | Pending | Pending |
| Alex opens Finance document | Denied | Pending | Pending |
| Sarah moves to Sales | Sales access allowed; Finance denied | Pending | Pending |
| Alex leaves | Sign-in blocked; session-revocation action recorded | Pending | Pending |
| Missing access is repaired | Intended access restored; unrelated access still denied | Pending | Pending |

## Deliverables

Create a joiner/mover/leaver checklist, a configuration summary, test evidence and one incident report using the [ticket template](../../it-support/tickets/TEMPLATE.md). Name evidence descriptively and redact personal details and credentials.

## Interview practice

Explain why access was assigned through groups, how you checked the employee experience, and why removing a licence alone is insufficient as a leaver workflow. Use your actual test results.

## First session

Complete tenant setup, record the available services and create the first fictional employee. Do not mark any tests complete until they have been performed.
