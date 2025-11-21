# Repository and Environment Access Governance Policy

Covers role-based access controls, separation of duties, least-privilege requirements, and auditability for mixed internal and partner teams across source control, CI/CD, artifact registries, and deployment targets.

## Purpose
Protect repositories, pipelines, and runtime environments through consistent access governance that limits risk and maintains auditability.

## Scope
- Applies to all internal staff, contractors, and vendors using source control, CI/CD, registries, staging, and production environments.
- Covers access provisioning, modification, recertification, and revocation.
- Includes machine identities, service accounts, and automation tokens.

## Roles and Responsibilities
- **System Owners:** Define access requirements per environment and approve privileged access requests.
- **Security Lead:** Defines control requirements, reviews elevated access, and oversees recertification.
- **Platform/DevOps Team:** Implements access controls, integrates identity providers, and maintains audit logs.
- **Team Managers:** Validate user role mappings and request changes when staff assignments shift.
- **Audit/Compliance:** Monitors adherence to policy and coordinates evidence collection.

## Policy Statements
- **Identity Standards**
  - Centralize authentication through approved identity providers with MFA enforced.
  - Service accounts must be uniquely identifiable and bound to specific automations.
- **Least Privilege and SoD**
  - Grant only required roles; prohibit combining conflicting duties (e.g., code approval and prod deployment for the same change) without compensating controls.
  - Use role-based groups aligned to environments (dev, test, prod) and data classifications.
- **Provisioning and Revocation**
  - Require documented approval for new access; time-box elevated roles with expiry dates.
  - Remove or reduce access within one business day of role changes or departures.
- **Recertification and Monitoring**
  - Perform quarterly access reviews for production and semi-annual reviews for lower environments.
  - Log administrative actions, elevation events, and deployment approvals; retain logs per compliance requirements.
- **Credential Management**
  - Store credentials and tokens in approved secrets management systems; rotation at least annually or after incidents.
- **Third-Party Access**
  - Vendors use named accounts and follow the Vendor Onboarding and Offboarding Process.
  - External access to production requires executive sponsor and Security Lead approval.

## Approval Workflow
1. Requester submits access request with justification and duration.
2. System Owner or designated approver validates necessity and scopes permissions.
3. Platform/DevOps provisions access and records change ticket.
4. Security Lead reviews elevated or cross-environment access for compliance.
5. Access recertified on defined cadence; revocation tracked through tickets and logs.

## Evidence and Audit
- Access requests, approvals, and change tickets stored in the ticketing system.
- Audit logs for authentication, authorization changes, and deployment approvals.
- Recertification reports with sign-off from System Owners and Security Lead.
- Records of credential rotations and incident-driven access reviews.

## Exception Handling
- Exceptions must specify scope, justification, compensating controls, owner, and expiry.
- Security Lead approves security exceptions; System Owner approves operational exceptions.
- Track exceptions in a centralized register and review quarterly.

## Review Cadence
- Annual policy review or after significant incidents/regulatory changes.
- Post-incident reviews assess whether access controls require tightening.

## Related Documents
- [Third-Party Software Delivery Policy](../third-party-governance/README.md)
- [Contracting and Commercial Controls Policy](../contracting-controls/README.md)
- [Operational Readiness and Handover Process](../../05_processes/operational-readiness-handover/README.md)
- [Vendor Onboarding and Offboarding Process](../../05_processes/vendor-onboarding-and-offboarding/README.md)
