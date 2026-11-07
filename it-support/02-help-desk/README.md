# Project 3 — Help Desk & Troubleshooting

[Portfolio home](../../README.md) · [Support project plan](../../SUPPORT-PROJECTS.md) · [Windows lab](../01-windows-active-directory/README.md)

**Status:** In progress. Three Microsoft 365 lab incidents are resolved and documented. Windows incident evidence is pending.

## Business request

Olu Office Services is a fictional company. Build a help desk process that prioritises requests, investigates causes and verifies recovery from the user's perspective.

## Ticket register

| Ticket | Report or request | Type | Status |
| --- | --- | --- | --- |
| [HD-001](../tickets/HD-001-new-starter-sign-in.md) | New starter could not sign in | Microsoft 365 incident | Resolved; original cause undetermined |
| [HD-002](../tickets/HD-002-finance-public-access.md) | Sales user could edit Finance | Microsoft 365 incident | Resolved |
| [HD-003](../tickets/HD-003-sales-membership-recovery.md) | Sales access lost after membership removal | Microsoft 365 incident | Resolved |
| HD-004 | Client cannot discover the domain controller | Windows DNS incident | Pending lab run |
| HD-005 | Authorised employee cannot save to the Finance share | Windows SMB permissions incident | Pending lab run |
| HD-006 | Client misses the screen-lock policy | Windows Group Policy incident | Pending lab run |
| HD-007 | A user cannot sign in after repeated failed attempts | Windows account incident | Pending lab run |
| HD-008 | Finance new starter needs an account and a shared folder | Windows service request | Pending evidence capture |
| HD-009 | A fictional leaver needs sign-in and access removed | Identity service request | Pending evidence capture |
| HD-010 | Multiple users report an unavailable internal application | Escalation exercise | Tabletop planned |

Counts reflect the recorded evidence: **3 resolved, 0 blocked and 0 completed tabletop exercises**. The planned scenarios below are the remaining work.

## Windows lab runs

Confirm the actual domain FQDN, client, domain controller and DNS configuration first. Record a working baseline. Introduce one reversible fault at a time on an isolated test VM, using a fictional account or a dedicated test object. Restore the baseline before moving to the next ticket.

| Ticket | Baseline and fault | Diagnostic evidence | Recovery evidence |
| --- | --- | --- | --- |
| HD-004 | Confirm the client discovers the DC. Record the client DNS settings and temporarily point the test client at a resolver that cannot resolve the lab domain. | Compare the default DNS query for the AD LDAP SRV record with a query sent directly to the lab DNS server. Record both results. | Restore the original client DNS configuration, flush its cache and verify SRV resolution and forced DC discovery. |
| HD-005 | Confirm a Finance test user can save to the share and a Sales test user is denied. Remove only the Finance test user's grant through the relevant test group. | Check signed-in identity, effective group membership and both share and NTFS permissions. Sign out and back in after membership changes. | Restore membership and repeat both tests, including a fresh save as the Finance user and a denial as the Sales user. |
| HD-006 | Verify the existing screen-lock GPO applies and record its settings. Use a dedicated test OU or dedicated test GPO to remove the test client from policy scope. | Compare the baseline and fault-state computer-scope Group Policy results. Record the OU and link. A setting can persist after scope changes; use actual results. | Restore the original scope, refresh policy, confirm the GPO applies and verify the expected lock behaviour. |
| HD-007 | Use a disposable lab account. Check that a lockout threshold exists before attempting to reproduce a lockout. | Check account state and collect the available failed-sign-in or lockout evidence. Record the difference between a bad password and a locked account. | Unlock the test account and confirm successful sign-in. If the lab cannot reproduce the case, record the blocker or run a labelled tabletop. |

For HD-008, reuse the [Finance onboarding scenario](../01-windows-active-directory/scenario-001-finance-onboarding.md) and record its observed acceptance tests. For HD-009, reuse actual leaver evidence if available and verify sign-in denial. For HD-010, write a tabletop handoff with impact, timestamps, checks, evidence and the team that should own the next action. Label it as simulated.

- [Verify Active Directory SRV records](https://learn.microsoft.com/en-us/troubleshoot/windows-server/networking/verify-srv-dns-records-have-been-created)
- [Troubleshoot Group Policy application](https://learn.microsoft.com/en-us/troubleshoot/windows-server/group-policy/applying-group-policy-troubleshooting-guidance)

## How to record a ticket

Use the [ticket template](../tickets/TEMPLATE.md). Record the user report, impact and priority, checks and observed results, confirmed cause or remaining uncertainty, actual fix and retest. Add a brief simulated user update and escalation criteria. Keep screenshots and logs redacted.

## Definition of done

Document ten tickets with their test method and outcome. At least five need reproducible hands-on evidence. Write three short help articles from verified fixes, capture one escalation example and update the resolved, blocked and tabletop counts from the records. Treat the work as independent lab experience.
