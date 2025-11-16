# Testing Workflow

## Overview
This process describes the testing lifecycle from commit to release. It ensures every change runs automated and manual tests aligned with the [Secure Release Policy](../policies/secure-release-policy.md).

- **Trigger** – Code merged to the main branch or release candidate tags.
- **Exit Criteria** – All required test stages pass and evidence is attached to the release record.
- **Roles** – Test owners maintain suites; service owners respond to failures; release managers collect artifacts.

## Stages
1. **Unit Tests**
   - Scope: modules, functions, and isolated services.
   - Steps: run `make test-unit` or language-specific equivalent; capture coverage artifacts.
   - Success: ≥90% pass rate on flaky test tracker; coverage meets thresholds in the [Service Architecture Standard](../standards/service-architecture-standard.md).
2. **Integration Tests**
   - Scope: service interactions, database migrations, message brokers.
   - Steps: provision ephemeral environment, seed reference data, run `make test-integration`.
   - Success: zero schema drift; all API contracts validated against OpenAPI specs.
3. **Smoke / End-to-End Tests**
   - Scope: deployable artifact validation in staging.
   - Steps: execute canary deployment, run post-deploy health checks, validate dashboards.
   - Success: KPIs remain within 5% of baseline; no P1/P2 incidents open.

## Evidence Collection
- Store test reports under `artifacts/<service>/<build-id>/` with timestamps.
- Attach links to the pull request template and release notes.
- Record deviations or waivers in the exception tracker referenced by the policy.

## Communication and Escalation
- Notify the `#testing-alerts` channel when failures persist beyond two runs.
- File an incident if testing gaps block releases for more than 24 hours.
- Summarize recurring issues in the monthly QA review and feed them into the roadmap backlog.

## Related Documents
- [Coding Conventions Guideline](../guidelines/coding-conventions.md)
- [Secure Release Policy](../policies/secure-release-policy.md)
