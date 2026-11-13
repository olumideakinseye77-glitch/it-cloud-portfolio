# Project 3 — Help Desk & Troubleshooting

[Portfolio home](../../README.md) · [Support project plan](../../SUPPORT-PROJECTS.md)

**Status:** Three Microsoft 365 incidents resolved and documented. The remaining ticket scenarios are planned.
Company: Olu Office Services (fictional).

## Business request

“Staff contact IT by phone and email, but there is no consistent record of what happened. Create a small help desk process so requests are prioritised, investigated and closed with evidence.”

## Build the help desk

Use Markdown ticket files in this repository and the existing [ticket template](../tickets/TEMPLATE.md). A paid ticketing product is not required.

Define open, investigating, waiting, resolved and closed states. Separate incidents from service requests. Give each ticket an impact, urgency and explained priority. Service targets may be fictional, but label them as lab targets and record actual elapsed time without inventing SLA performance.

## Resolved incidents

| Ticket | What I verified |
| --- | --- |
| [HD-001 — New-starter sign-in](../tickets/HD-001-new-starter-sign-in.md) | A password reset restored sign-in and internal email. The original cause was unresolved. |
| [HD-002 — Finance privacy](../tickets/HD-002-finance-public-access.md) | Changing the group to Private denied Alex access while Sarah retained editing access. |
| [HD-003 — Sales membership](../tickets/HD-003-sales-membership-recovery.md) | A controlled group membership removal denied Sarah access. Restoring membership let her edit and save. |

## Planned scenarios

Windows DNS, Finance share permissions, Group Policy, account lockout, slow workstation, application startup and mailbox provisioning. Assign ticket numbers as cases are recorded.

Introduce a reversible fault only after recording healthy behaviour. Use a bounded, reversible workload for a slow-PC simulation; do not fill a disk or destabilise your actual laptop. If a scenario cannot be reproduced, label it a tabletop exercise and keep it separate from hands-on results.

## How to work a ticket

1. Ask when it started, who is affected, the exact error and what changed.
2. State a hypothesis and choose a check that could confirm or reject it.
3. Record the actual result before choosing another action.
4. Apply a justified fix and record how to reverse it.
5. Retest the user's task and check for unwanted side effects.
6. Write a short user update and close only when verified.

Include one escalation example with symptoms, impact, checks, evidence and a clear reason to involve another team.

## Deliverables

- Ten tickets, distinguishing hands-on and tabletop work.
- Three help articles based on verified fixes.
- A short user-facing update for each incident.
- A summary of root causes and repeat issues.
- Counts of resolved, blocked and tabletop tickets based on the actual records.

## Definition of done

At least five tickets include reproducible hands-on evidence from your labs, and all ten clearly identify their test method and outcome. No invented production experience or user confirmation.

## Interview practice

“I tested access as the affected user, confirmed the signed-in identity and found that the Finance group was Public. I switched it to Private, tested Alex in a fresh session and verified that Sarah could still edit. That gave me an allow and a deny result after the change.”

**Why a fresh browser session?** The existing session reused the administrator's identity. A clean session let me verify access as Alex. For a wider audit I'd also inspect direct grants and sharing links.

[More interview examples](../../INTERVIEW-GUIDE.md)
