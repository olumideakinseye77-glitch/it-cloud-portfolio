# Microsoft 365 & Entra ID Lab

Status: core employee-lifecycle scenarios completed; additional checks and evidence improvements remain. [Project handover](01-employee-lifecycle/HANDOVER.md). [Read the validation record](01-employee-lifecycle/progress.md).

Fictional company: Olu Office Services. Use test accounts in a tenant you administer.

## Project brief

[Project 1 — Microsoft 365 Employee Lifecycle](01-employee-lifecycle/README.md) includes business requests, acceptance tests and evidence requirements.

[View the three support projects](../SUPPORT-PROJECTS.md).

## Business assignments

1. A new starter needs an account, appropriate licence, MFA and access to their team's resources.
2. An employee changes department: update access and verify old access is removed.
3. An employee leaves: block sign-in, revoke sessions and remove access under a documented retention plan.

## Interview walkthrough

“I created and licensed a test user with Microsoft Graph PowerShell, verified sign-in, MFA approval and email, then used Microsoft 365 groups and SharePoint to test a move between departments. During offboarding I blocked a separate user's fresh sign-in and initiated session sign-out.”

| Choice | Why it fit the lab |
| --- | --- |
| Microsoft Graph PowerShell and admin centres | Graph gave me repeatable account and licence commands. The admin centres let me inspect settings and perform targeted support actions. |
| Private Microsoft 365 groups and SharePoint | Group membership matched department access. Assigning permissions document by document would make a department transfer harder to review. |
| Block sign-in and retain the account for review | This let me verify fresh sign-in was denied while preserving lab data. I did not measure when existing sessions expired. |

[Diagrams and full interview walkthrough](01-employee-lifecycle/DIAGRAMS.md) · [Portfolio interview guide](../INTERVIEW-GUIDE.md)

## Evidence and follow-up

- [Completed checklist and handover](01-employee-lifecycle/HANDOVER.md).
- Redacted configuration screenshots.
- Positive and negative access tests.
- Three incident records with operator-confirmed outcomes, linked from the handover.

Features depend on the available tenant and licences. Confirm access and costs before provisioning. This cloud identity lab is separate from the Windows domain unless hybrid integration is actually implemented and tested.

[Back to portfolio](../README.md)
