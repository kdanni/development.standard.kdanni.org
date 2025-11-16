# Service Architecture Standard

## Scope and Mandate
This standard defines the architectural guardrails for HTTP services deployed by the engineering organization. Compliance is mandatory for all net-new services and major revisions to existing systems. Exceptions require approval from the governance working group.

## Architectural Principles
1. **Explicit boundaries** – Each service exposes a single API surface with versioned endpoints documented in OpenAPI.
2. **Stateless compute** – Web tiers remain stateless; persistence layers own state and are accessed through defined repositories.
3. **Dependency inversion** – Shared libraries provide interfaces; consuming services supply adapters so upgrades remain isolated.
4. **Observability baked-in** – Emit structured logs, metrics, and distributed traces following the `obs-*` naming conventions.

## Service Topology Requirements
- **API Gateway alignment** – All public traffic enters through the managed API gateway with mutual TLS enforcement.
- **Data ownership** – Each service owns its primary datastore. Cross-service reads must go through published APIs or event streams; direct database access is prohibited.
- **Resiliency posture** – Implement circuit breakers and retry policies for outbound calls. Document default timeouts in deployment manifests.

## Quality Gates
| Gate | Metric | Target |
| --- | --- | --- |
| Test coverage | Line coverage on critical packages | ≥ 80% |
| Performance | p95 latency per endpoint | ≤ 300 ms under baseline load |
| Availability | Uptime per quarter | ≥ 99.5% |
| Security | Dependency scans | Zero high/critical CVEs before release |

## Enforcement and Validation
- Architecture reviews confirm alignment before provisioning infrastructure.
- CI pipelines run coverage, load smoke tests, and security scans. Failing any gate blocks the release per the [Secure Release Policy](../policies/secure-release-policy.md).
- Observability dashboards are reviewed monthly; deviations trigger corrective action plans managed under the [Testing Workflow](../processes/testing-workflow.md).

## Related Guidance
- [Coding Conventions Guideline](../guidelines/coding-conventions.md)
- [Glossary](../references/glossary.md)
