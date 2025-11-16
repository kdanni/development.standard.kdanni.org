# Testing Workflow

## Overview
This process describes the testing lifecycle from commit to release. It ensures every change runs automated and manual tests aligned with the [Secure Release Policy](../policies/secure-release-policy.md).

- **Trigger** – Code merged to the main branch or release candidate tags.
- **Exit Criteria** – All required test stages pass and evidence is attached to the release record.
- **Roles** – Test owners maintain suites; service owners respond to failures; release managers collect artifacts.
- **Cadence** – Unit and integration suites run on every merge; end-to-end suites run nightly and on demand before production pushes.
- **Tooling** – CI orchestrator (GitHub Actions, Jenkins), coverage reporters, observability dashboards, and the exception tracker.

## Stages
1. **Unit Tests**
   - Scope: modules, functions, and isolated services.
   - Steps: run `make test-unit` or language-specific equivalent; capture coverage artifacts; publish flaky test suppressions for review.
   - Success: ≥90% pass rate on flaky test tracker; coverage meets thresholds in the [Service Architecture Standard](../standards/service-architecture-standard.md).
2. **Integration Tests**
   - Scope: service interactions, database migrations, message brokers.
   - Steps: provision ephemeral environment, seed reference data, run `make test-integration`, and archive data snapshots for diffing.
   - Success: zero schema drift; all API contracts validated against OpenAPI specs.
3. **Smoke / End-to-End Tests**
   - Scope: deployable artifact validation in staging.
   - Steps: execute canary deployment, run post-deploy health checks, validate dashboards.
   - Success: KPIs remain within 5% of baseline; no P1/P2 incidents open.
4. **Exploratory or Manual Regression (as needed)**
   - Scope: high-risk user journeys or compliance scenarios that cannot be automated yet.
   - Steps: follow the charter documented in the QA notebook, capture screenshots, log defects with reproduction steps.
   - Success: Charter completed, issues triaged, and sign-off recorded by the business owner.

## Evidence Collection
- Store test reports under `artifacts/<service>/<build-id>/` with timestamps.
- Attach links to the pull request template and release notes.
- Record deviations or waivers in the exception tracker referenced by the policy.
- Note recurring flaky tests and file engineering backlog items when the same test flakes twice in a rolling 14-day window.

## Communication and Escalation
- Notify the `#testing-alerts` channel when failures persist beyond two runs.
- File an incident if testing gaps block releases for more than 24 hours.
- Summarize recurring issues in the monthly QA review and feed them into the roadmap backlog.
- Share a weekly test-health snapshot that surfaces pass rates, coverage deltas, and backlog size for automation debt.
- When a severity-1 bug escapes to production, run a blameless review and update this workflow with the prevention action.

## Related Documents
- [Coding Conventions Guideline](../guidelines/coding-conventions.md)
- [Secure Release Policy](../policies/secure-release-policy.md)
