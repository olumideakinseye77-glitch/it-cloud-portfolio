# Azure Projects

[Portfolio home](../README.md) · [Microsoft 365](../microsoft-365/README.md) · [IT support](../it-support/README.md)

Seven projects covering application hosting, networking, security, resilience and operations. Open a project to review its architecture, code and testing evidence.

| Project | Main focus | Documented progress |
| --- | --- | --- |
| Foundation — [West Africa Capitals Quiz](https://github.com/olumideakinseye77-glitch/Olu) | Python, Docker, Container Apps, Terraform staging | Build and deployment documented |
| 01 — [Highly Available Web Application](https://github.com/olumideakinseye77-glitch/azure-ha-webapp) | Linux VMs, Load Balancer, Terraform, GitHub Actions | Core build and failover verified. Revised rollback and performance-counter verification pending. |
| 02 — [Enterprise Azure Network](https://github.com/olumideakinseye77-glitch/azure-enterprise-network) | Hub-and-spoke networking, routing, Private DNS, Terraform | Completed lab |
| 03 — [Identity, Security & Governance](https://github.com/olumideakinseye77-glitch/azure-identity-security-governance) | RBAC, managed identity, Key Vault, Azure Policy | Completed lab |
| 04 — [Multi-Region Platform](https://github.com/olumideakinseye77-glitch/azure-multi-region-platform) | Front Door, App Service, monitoring, Terraform | Core lab complete; live demo offline |
| 05 — [Operations & Incident Lab](https://github.com/olumideakinseye77-glitch/azure-operations-incident-lab) | Linux troubleshooting, Python, Bash, KQL | Core incident lab verified and offline. Live validation of the scheduled alert extension is pending. |
| 06 — [Landing Zone & Self-Service Platform](https://github.com/olumideakinseye77-glitch/azure-landing-zone-platform) | Terraform modules, request validation, governance | Local request validator implemented. Azure deployment remains planned. |

## Suggested review order

- **Networking:** start with Enterprise Azure Network for routing, private connectivity and troubleshooting.
- **Security:** review Identity, Security & Governance for access controls and deliberate failure tests.
- **Operations:** review Operations & Incident Lab for fault diagnosis and recovery evidence.

Progress reflects the documented project evidence. Each README links to its validation record and open work. Use the [interview guide](../INTERVIEW-GUIDE.md) to choose an example for a specific question.

Each project keeps its own source code and history. The foundation quiz also contains a Terraform staging extension; it is separate from numbered Cloud Engineering Projects 01–06.
