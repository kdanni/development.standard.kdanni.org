# Contracting and Commercial Controls Policy

Establishes mandatory contract language for secure SDLC commitments, vulnerability remediation timelines, SBOM delivery, escrow, audit rights, and service-level enforcement for third-party development and operations partners.

## Purpose
Standardize commercial terms that enforce security, quality, and operational expectations for all software delivery agreements.

## Scope
- Applies to new contracts, renewals, statements of work, and change orders involving software delivery or operations.
- Covers vendors with access to source code, CI/CD, infrastructure, data, or production support activities.
- Includes subcontractors engaged by primary vendors when they access systems or handle deliverables.

## Roles and Responsibilities
- **Legal Counsel:** Owns template language, negotiates deviations, and ensures regulatory alignment.
- **Procurement/Vendor Management:** Ensures correct templates are used, tracks approvals, and records contract metadata.
- **Security Lead:** Defines security requirements, SBOM expectations, and vulnerability SLAs; approves exceptions.
- **Business Owner:** Confirms commercial terms, deliverables, and penalties align with business goals.
- **Engineering/Product Lead:** Verifies technical commitments (architecture, quality gates, observability) are contractually captured.

## Required Clauses
- **Security and SDLC Commitments**
  - Compliance with internal security policies, coding standards, and dependency management practices.
  - Mandatory vulnerability scanning, remediation SLAs (e.g., critical within 7 days, high within 30 days), and proof of closure.
  - Secure handling of secrets, credentials, and customer data.
- **SBOM and Supply Chain Transparency**
  - SBOM delivery for each release in accepted formats (e.g., SPDX or CycloneDX).
  - Obligation to disclose open-source licenses and third-party components with associated risks.
- **Service Levels and Remedies**
  - Defined SLOs/SLAs for availability, performance, and support response times with service credits or other remedies.
  - Incident participation requirements and communication timelines.
- **Audit and Assurance Rights**
  - Right to request penetration tests or attestations (e.g., SOC 2, ISO 27001) and review remediation plans.
  - Access to logs, evidence packages, and change history to validate compliance.
- **Intellectual Property and Licensing**
  - Clear IP ownership of deliverables, licensing obligations, and restrictions on copyleft components without approval.
  - Escrow requirements for critical systems, including release triggers and verification cadences.
- **Data Protection and Privacy**
  - Data processing terms consistent with privacy classifications and cross-border transfer requirements.
  - Breach notification timelines and cooperation obligations.
- **Termination and Transition**
  - Exit assistance, knowledge transfer, and handover of documentation, credentials, and artifacts.
  - Obligations to support incident or vulnerability response during wind-down.

## Approval and Governance
- Contracts must use approved templates; deviations require Legal and Security Lead sign-off.
- High-risk engagements (production data access, customer-facing services) require executive sponsor approval.
- Maintain a contract register with scope, term, risk rating, and exception records.

## Evidence Requirements
- Signed agreements with tracked redlines and approvals.
- Documented vulnerability SLAs, SBOM delivery commitments, and audit clauses.
- Records of attestations, penetration tests, and remediation outcomes.
- Escrow verification reports when applicable.

## Exception Management
- Exceptions to required clauses must document business justification, risk acceptance, compensating controls, and duration.
- Security Lead and Legal Counsel must approve; Business Owner signs off on commercial impacts.

## Review Cadence
- Review templates and standard clauses at least annually or when regulations change.
- After each major incident or audit finding, assess whether contract language requires updates.

## Related Documents
- [Third-Party Software Delivery Policy](../third-party-governance/README.md)
- [Repository and Environment Access Governance Policy](../access-governance/README.md)
- [Vendor Onboarding and Offboarding Process](../../05_processes/vendor-onboarding-and-offboarding/README.md)
