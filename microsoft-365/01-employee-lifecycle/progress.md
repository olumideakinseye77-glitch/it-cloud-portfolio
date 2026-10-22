# Onboarding Validation — 22 October 2026

[Project brief](README.md) · [Sign-in incident](../../it-support/tickets/HD-001-new-starter-sign-in.md)

Status: account, email and Finance document access milestones complete; wider employee-lifecycle project in progress.

## Results

| Check | Result | Evidence basis |
| --- | --- | --- |
| Business Premium licences available | Confirmed | Admin-centre screenshot showed 25 total, 1 assigned and 24 available before Sarah's assignment |
| Microsoft Graph connection | Successful | Pasted PowerShell output reported delegated connection |
| Lab domain | Verified | Pasted Get-MgDomain output showed initial and verified domain |
| Sarah's account | Created | Pasted Get-MgUser output returned Sarah Jones |
| Business Premium assignment | Command succeeded | Pasted Set-MgUserLicense output returned Sarah's account; tenant SKU was SPB |
| Initial sign-in | Failed | Reported account-or-password error |
| Password reset and password change | Successful | Operator confirmed reset, successful sign-in and first-login password change |
| Outlook mailbox | Accessible | Operator confirmed inbox opened |
| Internal email: Sarah to lab administrator | Delivered | Operator confirmed receipt |
| Internal email: administrator reply to Sarah | Delivered | Operator explicitly confirmed both directions |

## Implementation

The operator used PowerShell 7.6.6 in Azure Cloud Shell and Microsoft Graph PowerShell to discover the domain and SKU, create the employee account and assign Business Premium. A password reset was performed through the administrator interface. Employee tests used a separate browser session.

The user-creation request specified Finance, Finance Assistant and GB usage location. A later readback of those profile fields has not yet been recorded.

## Scope of evidence

PowerShell results were supplied during the guided session. Sign-in, password change, mailbox access and message delivery were confirmed by the operator. No screenshots of mailbox messages or exported sign-in logs are committed at this checkpoint. The assistant did not independently sign into the tenant.

Account sign-in and a password change do not prove MFA registration or enforcement. Internal delivery does not prove external email delivery.

## Finance access validation

The operator created Finance Lab and a Finance Welcome document. Sarah's edit/save test succeeded. Alex could initially open the document and type; the group was found to be Public. After changing it to Private, the operator tested Alex in a separate Guest browser session and received an account-specific access denial. Sarah's access was then retested successfully.

[HD-002 — Finance privacy incident](../../it-support/tickets/HD-002-finance-public-access.md) records the issue, browser-session confusion, fix and retests. These are operator-confirmed results, not an independent permission audit. Effective group membership and sharing-link configuration still need explicit review.

## Remaining tests

- MFA registration and challenge.
- Final membership/sharing-link review and department-field readback.
- Department move and offboarding.
- The planned permissions incident.

Trial expiry and recurring-billing settings remain to be verified from the subscription details; no cancellation or billing change is claimed.

## Next request

Verify MFA registration and a fresh-session challenge for Sarah.
