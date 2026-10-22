# Project 3 — Help Desk & Troubleshooting

[Portfolio home](../../README.md) · [Support project plan](../../SUPPORT-PROJECTS.md)

Status: planned. Work through this project alongside the Microsoft 365 and Windows labs.
Company: Olu Office Services (fictional).

## Business request

“Staff contact IT by phone and email, but there is no consistent record of what happened. Create a small help desk process so requests are prioritised, investigated and closed with evidence.”

## Build the help desk

Use Markdown ticket files in this repository and the existing [ticket template](../tickets/TEMPLATE.md). A paid ticketing product is not required.

Define open, investigating, waiting, resolved and closed states. Separate incidents from service requests. Give each ticket an impact, urgency and explained priority. Service targets may be fictional, but label them as lab targets and record actual elapsed time without inventing SLA performance.

## Incident queue

| Ticket | User report | Lab dependency |
| --- | --- | --- |
| HD-001 | “I cannot sign in to my work account.” | Microsoft 365 or Windows |
| HD-002 | “My account keeps locking.” | Windows domain |
| HD-003 | “I can open Finance but cannot save a file.” | Windows or SharePoint permissions |
| HD-004 | “Other sites work, but the company resource does not.” | Isolated network/DNS lab |
| HD-005 | “My Windows PC has become slow.” | Windows test client |
| HD-006 | “The application will not open.” | Windows test client |
| HD-007 | “I have no mailbox after joining.” | Microsoft 365 email service |
| HD-008 | “My team files have disappeared.” | SharePoint or Teams, if licensed |
| HD-009 | “A colleague has moved department.” | Service request using either identity lab |
| HD-010 | “An employee is leaving today.” | Leaver service request |

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

Talk through a ticket without jumping straight to the fix. Explain your first check, how evidence changed your hypothesis, how you confirmed recovery and when you would escalate.
