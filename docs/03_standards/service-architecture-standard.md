# Service Architecture Standard

## Scope and Mandate
This standard defines the architectural guardrails for HTTP services deployed by the engineering organization. Compliance is mandatory for all net-new services and major revisions to existing systems. Exceptions require approval from the governance working group.

## Architectural Principles
1. **Explicit boundaries** – Each service exposes a single API surface with versioned endpoints documented in OpenAPI.
2. **Stateless compute** – Web tiers remain stateless; persistence layers own state and are accessed through defined repositories.
3. **Dependency inversion** – Shared libraries provide interfaces; consuming services supply adapters so upgrades remain isolated.
4. **Observability baked-in** – Emit structured logs, metrics, and distributed traces following the `obs-*` naming conventions.
5. **Security by default** – Enforce TLS 1.3 for all inbound and outbound calls, rotate credentials automatically, and run threat
   modeling whenever a service exposes new externally visible functionality.

## Service Topology Requirements
- **API Gateway alignment** – All public traffic enters through the managed API gateway with mutual TLS enforcement.
- **Data ownership** – Each service owns its primary datastore. Cross-service reads must go through published APIs or event streams; direct database access is prohibited.
- **Resiliency posture** – Implement circuit breakers and retry policies for outbound calls. Document default timeouts in deployment manifests.
- **API lifecycle** – Version APIs using `v{n}` prefixes, publish deprecation dates at least 90 days in advance, and surface
  changelog entries in the API catalog managed by the developer experience team.
- **Event contracts** – Event payloads must use the canonical domain schema. Breaking changes require parallel topics with
  consumer sign-off recorded in the architecture review minutes.

## Quality Gates
| Gate | Metric | Target |
| --- | --- | --- |
| Test coverage | Line coverage on critical packages | ≥ 80% |
| Performance | p95 latency per endpoint | ≤ 300 ms under baseline load |
| Availability | Uptime per quarter | ≥ 99.5% |
| Security | Dependency scans | Zero high/critical CVEs before release |

## Release Readiness Checklist
1. Architecture review completed with evidence stored in the design-doc repository.
2. Runbook updated with operational dashboards, on-call rotations, and rollback procedures.
3. API documentation merged into the service repository and published to the developer portal.
4. Automated chaos experiments (fault injection, dependency outages) executed at least once per quarter.

## Enforcement and Validation
- Architecture reviews confirm alignment before provisioning infrastructure.
- CI pipelines run coverage, load smoke tests, and security scans. Failing any gate blocks the release per the [Secure Release Policy](../04_policies/secure-release-policy.md).
- Observability dashboards are reviewed monthly; deviations trigger corrective action plans managed under the [Testing Workflow](../05_processes/testing-workflow.md).
- Platform engineering captures evidence of compliance in the service catalog, including links to latest test reports and
  incident retrospectives. Missing evidence is treated as a Sev-2 operational risk until remediation is complete.

## Related Guidance
- [Coding Conventions Guideline](../02_guidelines/coding-conventions.md)
- [Glossary](../06_references/glossary.md)
- [Resiliency Playbook](../02_guidelines/resiliency-playbook.md)
