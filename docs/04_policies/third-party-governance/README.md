# Third-Party Software Delivery Policy

Defines governance for supplier-led delivery, including onboarding, code ownership expectations, joint release criteria, and incident collaboration requirements when vendors commit to in-house repositories and CI/CD pipelines.

## Purpose
Ensure third-party contributors deliver secure, resilient, and supportable software while aligning with internal SDLC, security, and compliance expectations.

## Scope
- Applies to all suppliers, contractors, and managed service providers with access to source control, CI/CD, artifact registries, or production environments.
- Covers new engagements, renewals, and incremental change orders that modify delivery scope.
- Applies to both dedicated vendor repositories and shared in-house repositories.

## Roles and Responsibilities
- **Business Owner:** Sponsors the engagement, funds the work, and validates contractual obligations.
- **Engagement Manager:** Coordinates onboarding, delivery milestones, and vendor performance reporting.
- **Product/Engineering Lead:** Ensures backlog alignment, code quality, and architectural compliance.
- **Security Lead:** Performs supplier risk assessment, validates secure SDLC controls, and approves exceptions.
- **Vendor Manager/Procurement:** Confirms contractual clauses, insurance, audit rights, and termination terms.
- **Vendor Technical Lead:** Assigns qualified staff, enforces agreed workflows, and supplies required evidence.

## Policy Requirements
- **Onboarding and Access Controls**
  - Grant least-privilege access only after contract execution, security review, and identity verification.
  - Use named accounts with MFA; shared accounts are prohibited.
  - Recertify access at least quarterly and upon staff changes.
- **Secure Delivery Expectations**
  - Vendors must follow internal coding standards, dependency management practices, and vulnerability management SLAs.
  - SBOMs are required for every release and must align with contracting controls.
  - CI/CD pipelines must include security scanning equivalent to internal thresholds.
- **Code Ownership and Review**
  - Vendors commit code through pull requests with internal reviewer approval for protected branches.
  - Architectural changes require review through the Architecture Decision Record (ADR) process.
  - Intellectual property and licensing declarations must accompany third-party components.
- **Release Readiness and Quality Gates**
  - Definition of Done includes unit/integration test coverage, observability hooks, and rollback procedures.
  - Releases must satisfy documented SLOs and performance benchmarks.
  - Joint release go/no-go meetings are mandatory for production deployments.
- **Incident Management and Collaboration**
  - Vendors must participate in incident response, post-incident reviews, and corrective action tracking.
  - On-call expectations, escalation paths, and communication channels must be documented before go-live.
- **Data Protection**
  - Data handling must follow privacy classifications and approved data-transfer mechanisms.
  - Production data access requires explicit approval and logging; synthetic data must be used by default for testing.

## Workflow
1. **Intake:** Business owner raises an engagement request including scope, data classifications, and expected delivery model.
2. **Risk Assessment:** Security lead completes supplier risk and data-protection assessment; Procurement confirms contractual clauses.
3. **Onboarding:** Identity setup, access provisioning, tooling induction, and confirmation of SBOM and scanning expectations.
4. **Delivery Governance:** Vendors follow internal branching, review, and release gates; engagement manager tracks metrics.
5. **Release Approval:** Product/engineering lead and security lead approve releases based on evidence packages.
6. **Operational Participation:** Vendors join incident, change, and problem-management workflows with defined RACI.
7. **Periodic Review:** Quarterly business and security reviews assess performance, SLA adherence, and control evidence.
8. **Offboarding:** Access revoked, artifacts archived, IP rights verified, and knowledge transfer completed.

## Evidence and Records
- Signed agreements containing required clauses (security, IP, audit rights, SLAs, SBOM delivery).
- Supplier risk assessments, security questionnaires, and penetration test reports when applicable.
- Access recertification logs and onboarding/offboarding checklists.
- Release evidence packages (test results, SBOMs, approvals, rollout plans, and rollback playbooks).
- Incident participation notes and post-incident remediation plans.

## Exception Handling
- Exceptions must document scope, risk, compensating controls, and expiry date.
- Security lead approves security-related exceptions; business owner approves commercial deviations.
- Exceptions are time-bound and reviewed at least quarterly.

## Monitoring and Review
- KPI set includes code quality metrics, vulnerability remediation times, change failure rate, and SLA adherence.
- Annual policy review to align with updated contracting controls, access governance, and incident response processes.

## Related Documents
- [Contracting and Commercial Controls Policy](../contracting-controls/README.md)
- [Repository and Environment Access Governance Policy](../access-governance/README.md)
- [Operational Readiness and Handover Process](../../05_processes/operational-readiness-handover/README.md)
- [Vendor Onboarding and Offboarding Process](../../05_processes/vendor-onboarding-and-offboarding/README.md)
