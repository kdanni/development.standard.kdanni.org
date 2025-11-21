# Vendor Onboarding and Offboarding Process

Details qualification, security due diligence, environment access setup, and exit/offboarding steps for suppliers contributing to in-house repositories and pipelines.

## Purpose
Provide a repeatable, auditable process for bringing vendors into delivery workflows and safely removing access at contract end or termination.

## Scope
- Applies to all third-party contributors with repository, CI/CD, or environment access.
- Covers onboarding, periodic reviews, and offboarding for new engagements and renewals.
- Includes subcontractors when they access systems or deliver code.

## Roles (RACI)
- **Business Owner (A/R):** Initiates engagement, funds work, and approves onboarding/offboarding completion.
- **Procurement/Vendor Manager (R):** Validates contract terms, tracks renewals, and maintains vendor records.
- **Security Lead (C/A):** Performs risk assessment, validates controls, and approves exceptions.
- **Engineering/Product Lead (R):** Confirms delivery scope, integration points, and code ownership expectations.
- **Platform/DevOps (R):** Provisions access, configures CI/CD roles, and validates audit logging.
- **Vendor Technical Lead (R):** Supplies required artifacts, ensures vendor staff complete training, and signs off on offboarding.
- **Audit/Compliance (C):** Reviews evidence and recertification results.

## Onboarding Workflow
1. **Initiation**
   - Business owner submits request including scope, data classifications, environments, and timeline.
   - Procurement verifies contracting steps and required clauses (security, SBOM, audit rights).
2. **Due Diligence**
   - Security lead completes supplier risk assessment and reviews security questionnaires.
   - Confirm required attestations (e.g., SOC 2, ISO 27001) and insurance coverage.
3. **Access and Tooling Setup**
   - Platform/DevOps provisions named accounts with least privilege; enable MFA and SSO.
   - Configure repository permissions, branch protections, CI/CD roles, secrets management access, and logging.
4. **Enablement**
   - Engineering/Product lead conducts orientation on architecture, coding standards, and Definition of Done.
   - Vendor staff complete security and privacy training; acknowledge policies.
5. **Readiness Verification**
   - Validate SBOM expectations, vulnerability SLAs, and release approval process.
   - Capture evidence: access tickets, training completion, risk assessment, and contract references.
6. **Go-Live Approval**
   - Security Lead and Business Owner approve onboarding; engagement manager records milestone and schedules first review.

## Periodic Review
- Quarterly access recertification and review of vendor performance against SLAs and quality metrics.
- Validate adherence to security scanning, SBOM delivery, and incident participation requirements.
- Update risk assessments when scope changes or new data types are processed.

## Offboarding Workflow
1. **Trigger Identification**
   - Contract end, termination, scope reduction, or personnel changes.
2. **Access Removal**
   - Revoke accounts, tokens, VPN keys, and integration credentials; document in tickets.
   - Remove from groups and pipelines; rotate shared secrets and keys.
3. **Asset and Knowledge Transfer**
   - Collect code, documentation, runbooks, and test evidence; confirm repository ownership.
   - Validate IP rights and licensing declarations are delivered.
4. **Service Continuity Checks**
   - Confirm monitoring, alerts, and deployment pipelines function without vendor accounts.
   - Execute handover walkthroughs with internal teams; update on-call schedules.
5. **Closeout**
   - Audit/Compliance reviews evidence; Business Owner signs off on completion.
   - Archive vendor records and update contract register.

## Evidence Checklist
- Supplier risk assessment and questionnaires.
- Executed contracts with security and audit clauses; redlines and approvals.
- Access provisioning and revocation tickets; recertification reports.
- Training acknowledgments and policy attestations.
- SBOMs, vulnerability remediation records, and release approvals during engagement.
- Handover artifacts and sign-offs at offboarding.

## Metrics and Controls
- Time to complete onboarding/offboarding.
- Number of overdue access revocations or recertifications.
- SLA adherence, defect escape rate, and change failure rate for vendor-delivered work.

## Related Documents
- [Third-Party Software Delivery Policy](../../04_policies/third-party-governance/README.md)
- [Contracting and Commercial Controls Policy](../../04_policies/contracting-controls/README.md)
- [Repository and Environment Access Governance Policy](../../04_policies/access-governance/README.md)
- [Operational Readiness and Handover Process](../operational-readiness-handover/README.md)
