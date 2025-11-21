# Change-Management Policy

## Purpose and Scope
This policy governs how production-affecting changes are proposed, reviewed, approved, and documented across
all services owned by `development.standard.kdanni.org`. It applies to application code, infrastructure,
configuration, data migrations, and documentation updates that influence compliance posture.

## Roles and Responsibilities
- **Change Owner** – Prepares the change record, risk assessment, and rollback plan.
- **Reviewer** – Validates test coverage, dependency impacts, and alignment with relevant standards.
- **Change Advisory Board (CAB)** – Approves or rejects high-risk or freeze-window changes. Membership is listed
  in `meta/README.md`.
- **Release Manager** – Coordinates scheduling, communicates status, and ensures evidence is archived.

## Change Categories
| Category | Examples | Approval Requirements |
| --- | --- | --- |
| Standard | Routine deployments, documentation hygiene updates, feature flags toggled within guardrails. | Peer reviewer plus service owner acknowledgment. |
| Elevated | Schema migrations, dependency major upgrades, changes affecting SLO instrumentation. | CAB approval plus Release Manager sign-off. |
| Emergency | Security patches or production fixes that cannot wait for the next window. | Incident commander approval with CAB retroactive review within 24 hours. |

## Required Artifacts
1. Change request ID with links to design docs, tickets, and pull requests.
2. Test evidence aligned with the [Testing Workflow](../05_processes/testing-workflow.md), including regression and load tests when applicable.
3. Deployment plan detailing sequencing, validation checkpoints, and automation scripts.
4. Rollback strategy with time-to-restore estimates and owner assignments.
5. Communication plan covering stakeholder notifications, status updates, and post-change summaries.

## Exception Logging and Audit Traceability
- Log all exceptions or expedited approvals in the change record with justification, compensating controls, and expiration dates.
- Store approvals and exception logs in the central change-management tool for at least one year.
- Update the [Documentation Hygiene Guideline](../02_guidelines/documentation-hygiene.md) sections when governance expectations change.
- Tag releases that required exceptions so downstream consumers can trace risk.

## Compliance Checklist
1. Change categorized correctly with approvals captured before execution.
2. Test and rollback evidence attached to the change record.
3. Communication and status updates distributed via the agreed channels (chat, status page, or incident bridge).
4. Exceptions logged with expiration dates and follow-up actions tracked.
5. Post-change review completed within two business days, feeding insights into the [Deployment Runbook](../05_processes/deployment-runbook.md).

## Related Documents
- [Secure Release Policy](secure-release-policy.md)
- [Performance and Scalability Standard](../03_standards/performance-and-scalability-standard.md)
- [Deployment Runbook](../05_processes/deployment-runbook.md)
