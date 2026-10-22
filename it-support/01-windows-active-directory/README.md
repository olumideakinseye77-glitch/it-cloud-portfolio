# Project 2 — Windows Server & Active Directory

[Portfolio home](../../README.md) · [Support project plan](../../SUPPORT-PROJECTS.md)

Status: planned; environment not yet verified.
Company: Olu Office Services (fictional).

## Business request

“Our office needs centrally managed logins, department folders and a consistent screen-lock policy. Staff need help when their accounts or folder access stop working.”

## Environment

Use an isolated Windows Server lab and a domain-capable Windows client. The proposed server is DC01, client CLIENT01 and domain olu-lab.test. Confirm laptop resources, virtualisation support and legitimate installation media before choosing the local setup. An 8 GB laptop may need an alternative arrangement.

This Windows domain is separate from the Microsoft 365 tenant unless hybrid integration is deliberately implemented later.

## Assignments

1. [Sarah joins Finance](scenario-001-finance-onboarding.md): implement a company login and Finance-folder access; verify a Sales user is denied.
2. Create IT, Finance and Sales organisational units and suitable security groups. Document the difference between an organisational unit and a security group.
3. Apply a screen-lock Group Policy, inspect the resulting policy on CLIENT01 and record a behavioural test.
4. Handle a forgotten password and account lockout. Record identity verification as a simulated step; investigate repeated lockouts instead of only unlocking again.
5. Diagnose a lab DNS misconfiguration that prevents domain discovery. Restore the baseline and confirm domain access.

## Evidence required

- A simple network diagram and resource allocation.
- Domain join and successful domain-user login.
- Share and NTFS permissions, with allowed/denied tests.
- Group Policy scope and client verification.
- Three incident records: folder access, account problem and DNS.
- A short explanation of each root cause and verified fix.

## Definition of done

The client joins the domain; the right employee can access Finance while another cannot; the policy applies; and each incident includes diagnosis, resolution and successful retest.

## Interview practice

Explain how you would investigate Access denied, how DNS affects domain logins and when you would escalate an account problem.
