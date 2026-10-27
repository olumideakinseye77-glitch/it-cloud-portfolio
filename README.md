# Olumide Akinseye | IT & Cloud Portfolio

Hands-on projects in **Azure cloud engineering, Microsoft 365 and IT support**.

I bring an engineering and operations background to practical cloud and support labs. This portfolio records what I built, why I chose the approach, how I investigated problems and how I tested the results.

## Explore

| Area | Focus | Progress |
| --- | --- | --- |
| [Azure projects](azure-projects/README.md) | Infrastructure, networking, security and operations | Completed labs and an ongoing platform project |
| [Microsoft 365](microsoft-365/README.md) | Identity, onboarding and access management | Core lifecycle lab completed; limits documented |
| [IT support](it-support/README.md) | Windows Server, Active Directory and troubleshooting | Three support incidents documented; Windows lab planned |

## Selected Azure projects

| Project | What to review |
| --- | --- |
| [Enterprise Azure Network](https://github.com/olumideakinseye77-glitch/azure-enterprise-network) | Hub-and-spoke design, private connectivity and network fault investigation |
| [Identity, Security & Governance](https://github.com/olumideakinseye77-glitch/azure-identity-security-governance) | Least-privilege access, Key Vault and deliberate policy tests |
| [Operations & Incident Lab](https://github.com/olumideakinseye77-glitch/azure-operations-incident-lab) | Linux service failures, Python health checks and verified recovery |

[View all seven Azure projects →](azure-projects/README.md)

## IT support project plan

Three business-scenario projects complement the Azure work: Microsoft 365 employee lifecycle, Windows Server & Active Directory, and help desk troubleshooting.

[View the projects and recommended order](SUPPORT-PROJECTS.md)

## Microsoft 365 support lab

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

## Skills demonstrated in the Azure labs

Azure networking · Linux · Terraform/HCL · Python · Bash · Git/GitHub · GitHub Actions · Entra ID & RBAC · Azure Policy · Key Vault · Azure Monitor & KQL

## About the evidence

These are independent portfolio labs. Each project documents its implementation, test results and limitations. Completion refers to the recorded lab scope; it does not imply a currently running service. Some deployments were removed after testing to control costs.

Source code and commit history live in the individual Azure repositories. Microsoft 365 and IT support exercises are documented here as they are completed. All published support scenarios use fictional users and redacted evidence.
