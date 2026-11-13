# Project 2 — Windows Server & Active Directory

[Portfolio home](../../README.md) · [Support project plan](../../SUPPORT-PROJECTS.md)

**Status: Paused after the initial Active Directory build.**
Company: Olu Office Services (fictional).

## Business request

“Our office needs centrally managed logins, department folders and a consistent screen-lock policy. Staff need help when their accounts or folder access stop working.”

## Environment

DC01 runs in a local VirtualBox VM with a static IP and hosts the `olu-lab.test` Active Directory domain. `CLIENT01` is the intended workstation for client-side validation.

This Windows domain is separate from the Microsoft 365 tenant unless hybrid integration is deliberately implemented later.

## Checkpoint

- Installed and renamed DC01, set a static IP, and created the Active Directory domain.
- Created the Olu Office Services organisational structure with Finance, Sales and IT OUs.
- Created the fictional accounts and department security groups. Sarah was added to `GG_Finance` and Alex to `GG_Sales`.

The GitHub record is a setup summary. Evidence for DNS service discovery, the client domain join and sign-in, Finance share permissions, and client-side Group Policy enforcement is pending. The related Windows troubleshooting exercises are still open.

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

“I set up DC01 in VirtualBox, created the domain and organised Finance, Sales and IT. I used organisational units to structure directory objects and security groups to represent department access. I paused after configuring the groups and memberships. The workstation and permission tests are still open.”

**Why groups and OUs?** I can assign access to a department security group and update membership as people move. OUs organise objects, let me target Group Policy and support delegated administration. I'd use Entra ID for cloud identity and cloud application access. This lab was specifically for Windows domain, DNS and Group Policy fundamentals.

[More interview examples](../../INTERVIEW-GUIDE.md)
