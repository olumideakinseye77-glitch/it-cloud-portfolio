# Microsoft 365 Support Lab — Interview Diagrams

[Project overview](README.md) · [Handover](HANDOVER.md) · [Test evidence](progress.md)

**Olumide Akinseye | Independent Microsoft 365 portfolio lab**

The diagrams show the completed lab journey and the troubleshooting work. They summarise recorded command output and operator-confirmed tests; they do not represent a production environment or an independent tenant audit.

## 1. Employee lifecycle and tested access

Sarah is the joiner and mover. Alex is a separate leaver example.

```mermaid
flowchart TD
    R["Business request: manage employee access"] --> J["JOINER: Sarah joins Finance"]
    R --> M["MOVER: Sarah transfers to Sales"]
    R --> L["LEAVER: Alex leaves"]

    J --> J1["Graph PowerShell: create account and assign Business Premium"]
    J1 --> J2["Test password change, Authenticator approval and email"]
    J2 --> J3["Finance document: edit and save allowed"]

    M --> M1["Update department and group membership"]
    M1 --> M2["Private Sales group added; Finance membership removed"]
    M2 --> M3["Sales: edit allowed; Finance: access denied"]

    L --> L1["Block sign-in and initiate session sign-out"]
    L1 --> L2["Remove lab memberships; retain account and data"]
    L2 --> L3["Fresh sign-in: rejected"]

    classDef joiner fill:#eaf3ff,stroke:#2563eb,color:#10284e;
    classDef mover fill:#e9f8f2,stroke:#16805d,color:#123d31;
    classDef leaver fill:#fff3e5,stroke:#c77716,color:#613b10;
    class J,J1,J2,J3 joiner;
    class M,M1,M2,M3 mover;
    class L,L1,L2,L3 leaver;
```

**Services used:** Microsoft Entra ID for accounts, Microsoft Graph PowerShell for user creation/licensing, Microsoft Authenticator for Sarah's tested approval, Exchange Online/Outlook for email, and Microsoft 365 groups plus SharePoint for department files. Administrative work also used the Microsoft 365 and SharePoint admin centres.

**Final observed state:** Sarah can edit Sales documents and is denied Finance access. Alex's fresh sign-in is blocked. Alex's account, licence and data were retained for lab review.

## 2. Troubleshooting: symptom → evidence → fix → retest

```mermaid
flowchart TD
    T["Troubleshooting: verify identity and reproduce the symptom"] --> A["HD-001: Sarah cannot sign in"]
    T --> B["HD-002: Alex can edit Finance"]
    T --> C["HD-003: Sarah loses Sales access"]

    A --> A1["Account exists; licence command succeeded"]
    A1 --> A2["Reset temporary password; complete password change"]
    A2 --> A3["PASS: sign-in and internal email work"]

    B --> B1["Confirm Alex identity; discover Public group"]
    B1 --> B2["Change Finance to Private; isolate browser sessions"]
    B2 --> B3["PASS: Alex denied; Sarah still edits"]

    C --> C1["Controlled fault: remove Sales membership"]
    C1 --> C2["Confirm denial; restore Sarah's membership"]
    C2 --> C3["PASS: Sales editing and saving restored"]

    classDef fault fill:#fff0f0,stroke:#d1495b,color:#702333;
    classDef check fill:#eef2ff,stroke:#6875c9,color:#263267;
    classDef fix fill:#edf7ff,stroke:#2186b6,color:#154962;
    classDef passed fill:#e8f8ef,stroke:#25865a,color:#164b32;
    class A,B,C fault;
    class A1,B1,C1 check;
    class A2,B2,C2 fix;
    class A3,B3,C3 passed;
```

| Incident | What I learned | Full record |
| --- | --- | --- |
| Initial sign-in failure | An account and licence do not prove the employee can sign in. The password reset fixed access; the original cause was not established. | [HD-001](../../it-support/tickets/HD-001-new-starter-sign-in.md) |
| Finance privacy error | Check Public/Private settings and test both authorised and unauthorised users. Browser-session reuse can make the test use the wrong identity. | [HD-002](../../it-support/tickets/HD-002-finance-public-access.md) |
| Lost Sales access | Group membership can determine access. Use a known-working baseline and retest editing after restoring membership. This was a controlled known-cause exercise. | [HD-003](../../it-support/tickets/HD-003-sales-membership-recovery.md) |

## 3. How to explain the project in an interview

“I built a Microsoft 365 lab around a small company's employee lifecycle. I used Microsoft Graph PowerShell to create and license a test user, then tested sign-in, an Authenticator approval and email delivery in both directions.

I created department workspaces and tested permissions from different user accounts. One access test revealed that the Finance group was Public. I corrected it to Private and verified that the Sales user was denied while the Finance user could still edit.

I then moved Sarah from Finance to Sales, tested both her new access and removal of old access, and offboarded Alex by blocking sign-in, initiating session sign-out and removing memberships. Finally, I removed and restored Sales membership to practise diagnosing and resolving missing access. I documented the tests and limitations in GitHub.”

## Evidence boundaries

- Command output supports account creation and licensing. Most browser outcomes are operator-confirmed, without committed screenshots or exported logs.
- Sarah's MFA registration and one challenge passed; the enforcement policy was not independently inspected. Alex's MFA was not tested.
- Private-group settings are not a substitute for auditing direct grants and sharing links. A full sharing-link inventory remains unfinished.
- Fresh blocked sign-in was tested for Alex; existing-session invalidation timing was not measured.
- No mailbox conversion, licence removal, account deletion, Windows lab, Intune or hybrid identity work is represented as completed.
