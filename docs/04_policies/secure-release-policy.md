# Secure Release Policy

## Policy Statement
All software releases must demonstrate compliance with security, quality, and approval gates before production deployment. This policy applies to services, libraries, and infrastructure-as-code hosted under the organization’s Git repositories.

## Roles and Responsibilities
- **Service Owners** – Ensure automated pipelines implement every gate and provide attestations in release notes.
- **Security Engineering** – Maintains scanning tools, reviews exceptions, and monitors policy adherence.
- **Release Managers** – Own go/no-go decisions, confirm evidence is archived, and coordinate rollback plans.

## Required Gates
1. **Static and dependency scanning** – Run SAST and SBOM scans on every commit. Block merges with high or critical findings until remediation or approved exceptions.
2. **Test verification** – Execute the [Testing Workflow](../05_processes/testing-workflow.md) suite (unit, integration, smoke). Document pass/fail results.
3. **Change review** – Obtain at least two approvals: one domain reviewer and one maintainer listed in `meta/STRUCTURE.md`.
4. **Release checklist** – Complete the [documentation template](../templates/document-template.md) checklist section to confirm artifacts, owners, and communication.

## Exception Handling
- Submit exception requests using the templates directory and include: scope, duration, compensating controls, and approval signatures.
- Security Engineering responds within two business days. Approved exceptions carry an expiration date and must be tracked in the release notes.

## Enforcement
- Pipelines failing any gate automatically halt deployments.
- Quarterly audits sample three releases per portfolio. Findings feed into the roadmap backlog and may trigger updates to the [Service Architecture Standard](../03_standards/service-architecture-standard.md).

## Related Documents
- [Coding Conventions Guideline](../02_guidelines/coding-conventions.md)
- [Testing Workflow](../05_processes/testing-workflow.md)
