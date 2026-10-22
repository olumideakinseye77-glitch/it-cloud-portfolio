# Onboarding Validation — 22 October 2026

[Project brief](README.md) · [Sign-in incident](../../it-support/tickets/HD-001-new-starter-sign-in.md)

Status: account and email milestone complete; wider employee-lifecycle project in progress.

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

## Remaining tests

- MFA registration and challenge.
- Private Finance workspace and Sarah's document read/write access.
- Alex's account and denied Finance access.
- Department move and offboarding.
- The planned permissions incident.

Trial expiry and recurring-billing settings remain to be verified from the subscription details; no cancellation or billing change is claimed.

## Next request

Create a private Finance Microsoft 365 group, with the lab administrator as owner and Sarah as member, then test its document workspace.
