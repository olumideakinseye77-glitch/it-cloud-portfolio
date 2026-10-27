# Microsoft 365 Employee Lifecycle — Project Handover

Core lab scenarios completed through 27 October 2026. Additional checks and evidence improvements remain listed below.

[Project](README.md) · [Validation record](progress.md)

## Business outcome

For fictional company Olu Office Services, the lab exercised a new starter, a department move and a leaver. It also tested three support incidents.

| Scenario | Completed work | Evidence |
| --- | --- | --- |
| Joiner | Created Sarah using Graph PowerShell; assigned Business Premium; tested password change, Outlook and internal email in both directions | Pasted command output and operator confirmations |
| Secure sign-in | Registered Authenticator for Sarah and tested a sign-in approval | Operator confirmation |
| Department access | Created Finance and Sales groups and test documents; confirmed allowed editing and denied access | Operator confirmations; pasted Alex denial |
| Mover | Updated Sarah to Sales, changed membership, tested Sales editing and Finance denial | Operator confirmation |
| Leaver | Blocked Alex, initiated session sign-out, removed lab membership and tested rejected sign-in | Operator confirmation; exact error code not captured |
| Support | Resolved initial sign-in failure, incorrect public group privacy and missing Sales membership | Three incident records |

## Joiner / mover / leaver checklist

### Joiner — Sarah
- [x] Create the account.
- [x] Assign the available Business Premium licence.
- [x] Test sign-in and required password change.
- [x] Register and test Authenticator.
- [x] Test internal email in both directions.
- [x] Test Finance document editing.
- [x] Test Alex's lack of Finance access.

### Mover — Sarah
- [x] Change department to Sales (operator confirmed).
- [x] Add Sales membership and remove Finance membership.
- [x] Test Sales editing and Finance denial.
- [x] Confirm final groups are Private and the administrator remains owner.

### Leaver — Alex
- [x] Retention decision: keep the account, licence and lab data for review.
- [x] Block sign-in.
- [x] Initiate Sign out of all sessions.
- [x] Remove relevant lab group memberships.
- [x] Test blocked fresh sign-in.
- [ ] Decide final data cleanup and licence removal before trial end; not performed.

## Incident records

- [HD-001 — New-starter sign-in](../../it-support/tickets/HD-001-new-starter-sign-in.md)
- [HD-002 — Finance privacy](../../it-support/tickets/HD-002-finance-public-access.md)
- [HD-003 — Sales membership recovery](../../it-support/tickets/HD-003-sales-membership-recovery.md)

## Evidence limits and unfinished checks

The assistant did not directly administer or independently test the tenant. Screenshots of messages, MFA logs and effective permissions are not committed. No deployment/automation script has been committed; command use is documented in the validation record.

Alex's MFA was not tested before offboarding. Sarah's underlying MFA enforcement policy was not inspected. Full document sharing-link inventories, independent department-field readback and access-role exports remain outstanding. Group membership/privacy was reviewed by the operator, but is not a complete direct-permission audit. No claim is made that all users or all sign-ins require MFA.

Existing session expiry timing, data migration, retention-policy enforcement, external email, Windows administration, Teams provisioning, Intune and hybrid identity were not tested. The account and data retention decision was documented; deletion or licence removal was not performed.

Trial cancellation, renewal settings and exact free-period expiry remain unverified in this record. Review the subscription directly before its free period ends.

## CV wording

Independent Microsoft 365 Support Lab: Used Microsoft Graph PowerShell to create and license a test user; tested Authenticator MFA, email and SharePoint access; performed department-transfer and offboarding exercises; documented three support incidents with recovery tests.

Use this under Independent Projects, and explain the operator-performed test scope and evidence limits when asked.

## Interview walkthrough

Explain the business request, why group privacy and membership mattered, how you distinguished browser identity from permissions, and what tests proved each change worked. For the first password problem, the fix is known but the original cause was not established.
