# Scenario 001 — Sarah Joins Finance

Type: simulated service request.
Status: open — lab not yet provisioned.
Company: Olu Office Services.

## Manager's request

Sarah starts in Finance on Monday. She needs a company login and access to the Finance folder. Sales employees must not be able to open that folder.

## Your responsibilities

- Identify the required accounts, groups, devices and permissions.
- Explain the proposed approach before making changes.
- Implement the request in your own isolated lab.
- Demonstrate that Sarah can access Finance and a Sales user cannot.
- Record what you built and the test results.

## First task — environment assessment

Do not install or provision anything until these facts are recorded:

- Laptop operating system and processor:
- Total and available RAM:
- Free disk space:
- Existing virtualisation software and VMs:
- Windows Server installation media/licence or evaluation access:
- Domain-capable Windows client edition/media/access:
- Chosen local lab platform and resource allocation:
- Alternative if the laptop cannot run both VMs:

An 8 GB laptop may struggle to run both a server and client together. Choose a workable environment before continuing. GitHub stores documentation and scripts, not running VMs or their disk images.

## Proposed lab

- Server: DC01, with Active Directory Domain Services and DNS.
- Client: CLIENT01, with a Windows edition that supports domain joining.
- Domain: olu-lab.test.
- Fictional users: Sarah in Finance and Alex in Sales.
- Separate department groups and a Finance shared folder.
- Private lab network. No real employer systems or accounts.

Treat this as a proposed design until implemented.

## Acceptance tests

| Test | Expected result | Actual result | Evidence |
| --- | --- | --- | --- |
| CLIENT01 joins the domain | Domain join succeeds | Not tested | Pending |
| Sarah signs in | Domain sign-in succeeds | Not tested | Pending |
| Sarah opens Finance | Access succeeds | Not tested | Pending |
| Alex opens Finance | Access denied | Not tested | Pending |
| Sarah creates a test document | Succeeds if authorised by agreed requirements | Not tested | Pending |

Before granting write access, clarify with the fictional manager whether Sarah needs read-only or read/write access. Use group membership rather than broad access grants.

## Follow-up incident — release after baseline tests pass

Sarah reports: “I could open Finance yesterday; today I get Access denied.”

Introduce one reversible fault inside the lab. Capture symptoms, investigate the cause, restore correct access and retest both Sarah and Alex. Do not fix the fault by granting everyone access.

## Completion record

- Environment and design:
- Requirements agreed:
- Changes made:
- Test evidence:
- Problems encountered:
- Resolution and verification:
- Lessons learned:
- Next action:

Leave this request open until the acceptance tests are supported by evidence.
