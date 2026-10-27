# Onboarding Validation — 22 October 2026

[Project brief](README.md) · [Sign-in incident](../../it-support/tickets/HD-001-new-starter-sign-in.md)

Status: core lifecycle scenarios, group review and membership-recovery exercise completed. Additional unperformed checks remain listed below. [Handover](HANDOVER.md).

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

Sarah's MFA was tested separately as described below; password changes alone are not MFA evidence. Internal delivery does not prove external email delivery.

## Finance access validation

The operator created Finance Lab and a Finance Welcome document. Sarah's edit/save test succeeded. Alex could initially open the document and type; the group was found to be Public. After changing it to Private, the operator tested Alex in a separate Guest browser session and received an account-specific access denial. Sarah's access was then retested successfully.

[HD-002 — Finance privacy incident](../../it-support/tickets/HD-002-finance-public-access.md) records the issue, browser-session confusion, fix and retests. These are operator-confirmed results, not an independent permission audit. Effective group membership and sharing-link configuration still need explicit review.

## MFA validation

On 22 October 2026, the operator confirmed Microsoft Authenticator registration for Sarah. After being instructed to use a fresh browser session, the operator confirmed that sign-in requested and accepted an Authenticator approval and then succeeded.

Evidence basis: operator reports from the guided session. No QR codes, approval codes or authentication secrets are retained. This records one successful MFA challenge; the underlying enforcement policy and sign-in logs have not been independently inspected. Alex's MFA remains unverified.

## Department transfer — 27 October 2026

The operator confirmed creating a Private Sales Lab Microsoft 365 group, adding Sarah, changing her department to Sales, and removing her from Finance membership (including checking owner status). A Sales Welcome document was created. The operator explicitly confirmed that Sarah could edit and save Sales Welcome while the original Finance Welcome document returned an access-denial result.

Evidence basis: guided-session operator confirmations. No fresh permission export or screenshots were collected. These tests demonstrate the observed access transition, not an audit of all direct permissions and sharing links.

## Offboarding — 27 October 2026

Lab retention decision: retain Alex's account, licence and data for the evidence review; no deletion, licence removal, data export or ownership transfer was performed or verified.

The operator confirmed selecting Block sign-in, initiating Sign out of all sessions, reviewing/removing lab group memberships and attempting a fresh sign-in. The reported result was that the account was locked/blocked. The exact Microsoft error text and code were not supplied, so no particular error code is claimed.

Evidence basis: operator reports from the guided session. Existing-session invalidation timing was not measured; this record does not claim all cached tokens became unusable immediately. Blocking sign-in does not erase files already downloaded.

## Final group review and recovery exercise — 27 October 2026

The operator confirmed Finance Lab and Sales Lab were Private, the administrator remained an owner of both, Sarah was in Sales and absent from Finance membership/ownership, and Alex was absent from both.

Sarah was then temporarily removed from Sales. The operator confirmed the denied-access test and, after re-adding her, confirmed restored document editing and saving. See [HD-003](../../it-support/tickets/HD-003-sales-membership-recovery.md). Finance denial was last confirmed during the department-transfer test, not separately after recovery.

## Unperformed checks and evidence improvements

- Alex's MFA registration and challenge; review the policy responsible for Sarah's challenge.
- Full document sharing-link inventory and independent department-field readback. Group membership/privacy was reviewed through operator confirmation.
- Redacted test screenshots and sign-in/effective-permission exports.

Trial expiry and recurring-billing settings remain to be verified from the subscription details; no cancellation or billing change is claimed.

## Handover

[Review the final checklist, CV wording and evidence limits](HANDOVER.md). The Windows Server and wider ten-ticket help desk projects remain separate work.
