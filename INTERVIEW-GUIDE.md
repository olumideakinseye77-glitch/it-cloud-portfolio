# Portfolio Interview Guide

[Portfolio home](README.md) · [Azure projects](azure-projects/README.md) · [Project tracker](PROJECT-TRACKER.md)

## A 30-second introduction

> I'm moving from mechanical engineering into Azure cloud engineering. In my labs I've taken a Python app from local development into Azure, operated Linux workloads, built a hub-and-spoke network with Terraform, and tested Azure access and governance controls. My engineering background shapes how I work through faults. I establish a baseline, follow the evidence and test recovery before I close the issue.

## Pick a project that answers the question

| If they ask about… | Lead with… | Open this evidence |
| --- | --- | --- |
| Networking, DNS or troubleshooting | Enterprise Azure Network | [Network Watcher route and port tests](https://github.com/olumideakinseye77-glitch/azure-enterprise-network/blob/main/docs/troubleshooting.md) |
| Monitoring, Linux or incident response | Operations & Incident Lab | [Stopped Nginx incident](https://github.com/olumideakinseye77-glitch/azure-operations-incident-lab/blob/main/incidents/001-stopped-web-service.md) |
| Availability zones or deployment | Highly Available Web App | [Backend failover test](https://github.com/olumideakinseye77-glitch/azure-ha-webapp#high-availability-failover-test) |
| Regional resilience | Multi-Region Platform | [Request test and alert result](https://github.com/olumideakinseye77-glitch/azure-multi-region-platform#validation-so-far) |
| Identity, security or governance | Azure Identity, Security & Governance | [RBAC, policy, Key Vault and lock tests](https://github.com/olumideakinseye77-glitch/azure-identity-security-governance#validation-evidence) |
| Containers or Terraform staging | West Africa Capitals Quiz | [Staging plan and deployment](https://github.com/olumideakinseye77-glitch/Olu/pull/1) |
| Platform engineering or automation | Landing Zone & Self-Service prototype | [Local validator demo](https://github.com/olumideakinseye77-glitch/azure-landing-zone-platform#run-the-local-demo) |
| Microsoft 365 or user access | Employee Lifecycle Lab | [Joiner, mover and leaver evidence](microsoft-365/01-employee-lifecycle/HANDOVER.md) |
| Handling a support ticket | Help Desk & Troubleshooting | [Finance permissions incident](it-support/tickets/HD-002-finance-public-access.md) |
| On-premises identity basics | Windows Server & Active Directory | [Paused lab checkpoint](it-support/01-windows-active-directory/README.md#checkpoint) |

## Walk through a project in two minutes

1. **Requirement.** What needed to work, and what constraint mattered?
2. **Decision.** What did you choose, and what would have made you choose something else?
3. **Implementation.** Follow one request, packet or identity through the design.
4. **Evidence.** Show one result. Say what you expected, what happened and what you changed.
5. **Limit.** Identify the next test or change you'd make and what it would prove.

### Example answer for a networking interview

> My lab needed the app spoke to reach the data spoke on TCP 443. I used hub-and-spoke because I wanted the spokes isolated with a shared forwarding point. My first connection failed. Network Watcher showed no usable next hop and an outbound deny. I added a Linux forwarding appliance, routes in both directions and a scoped NSG allow. The retest showed 66 successful probes on 443 through the appliance, and 8080 was denied. Direct peering would be simpler for just two networks. I used an appliance to practise central transit, and I'd evaluate a managed firewall and resilient design before using that pattern in production.

## Questions to practise out loud

- **Why did you use different compute services?** I used Container Apps for a packaged stateless quiz, VMs when the learning goal was Linux administration, and App Service when I wanted to focus on regional routing.
- **What did Terraform and GitHub Actions each do?** Terraform described the resources and tracked their state. GitHub Actions ran checks and, in the HA app, hosted the rolling deployment workflow. A green validation run is evidence that the checks passed. I use separate deployment and runtime results to show what worked in Azure.
- **How did you verify recovery?** I repeated the original failing task, such as requesting the HTTP endpoint or editing the affected document. I also checked the component state or the intended deny case where the lab supported it.
- **What work is still open?** The HA app's revised rollback and Operations Lab's scheduled alerts need live Azure validation. The Landing Zone is a local prototype. Windows Server is paused after the initial domain and group setup.

Open the README for the project you're presenting. Its walkthrough gives you the architecture, the reasons for the choices and the evidence you can refer to during follow-up questions.
