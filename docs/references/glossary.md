# Engineering Glossary and Terminology Index

| Term | Category | Definition | Related Documents | Review Cadence | Owner |
| --- | --- | --- | --- | --- | --- |
| ADR | Artifact | Architecture Decision Record documenting context, decision, and consequences for significant changes. | [Documentation Hygiene Guideline](../guidelines/documentation-hygiene.md) | Quarterly | Standards working group |
| CAB | Acronym | Change Advisory Board responsible for approving elevated and emergency changes. | [Change-Management Policy](../policies/change-management-policy.md) | Monthly | Governance working group |
| Canary Deployment | Process | Incremental rollout that exposes a small percentage of traffic to a new release to detect regressions early. | [Deployment Runbook](../processes/deployment-runbook.md) | Quarterly | Operations working group |
| DeployHub | Tooling | Internal orchestration tool used to schedule, execute, and audit deployments across environments. | [Deployment Runbook](../processes/deployment-runbook.md) | Monthly | Operations working group |
| Error Budget | Concept | Allowable threshold of unreliability derived from an SLO target (e.g., 0.1% downtime per quarter). | [Performance and Scalability Standard](../standards/performance-and-scalability-standard.md) | Monthly | Service owners |
| Pulse | Service Name | Centralized monitoring and alerting service aggregating RED metrics and business KPIs. | [Performance and Scalability Standard](../standards/performance-and-scalability-standard.md) | Monthly | Observability team |
| Release Log | Artifact | Repository of deployment records, approvals, and rollback evidence retained for audits. | [Change-Management Policy](../policies/change-management-policy.md) | Monthly | Release managers |
| SBOM | Acronym | Software Bill of Materials listing dependencies and versions contained in a release artifact. | [Secure Release Policy](../policies/secure-release-policy.md) | Quarterly | Security engineering |
| Service SLO Registry | Artifact | Catalog describing each service’s SLOs, owners, and review dates. | [Performance and Scalability Standard](../standards/performance-and-scalability-standard.md) | Monthly | Architecture Guild |
| SLO | Acronym | Service Level Objective describing the measurable reliability target communicated to stakeholders. | [Performance and Scalability Standard](../standards/performance-and-scalability-standard.md) | Monthly | Service owners |
| Telemetry Pack | Tooling | Predefined dashboards, alerts, and synthetic checks provisioned for every service. | [Deployment Runbook](../processes/deployment-runbook.md) | Quarterly | Observability team |
| Waiver | Artifact | Temporary authorization allowing policy deviation with compensating controls and expiration dates. | [Change-Management Policy](../policies/change-management-policy.md) | Monthly | Governance working group |

## Maintenance Notes
- Knowledge management reviews terms quarterly and coordinates updates with document owners.
- When new terms appear in guidelines, policies, or standards, add them here and cross-link back to the source document.
- Cite external sources (e.g., NIST, OWASP) inline when referencing authoritative definitions.
- Acronyms appear alongside their expansion the first time they are referenced in documents, linking to this file.

## Related Documents
- [Service Architecture Standard](../standards/service-architecture-standard.md)
- [Performance and Scalability Standard](../standards/performance-and-scalability-standard.md)
- [Secure Release Policy](../policies/secure-release-policy.md)
