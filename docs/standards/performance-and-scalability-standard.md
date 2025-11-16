# Performance and Scalability Standard

## Purpose
This standard defines how services plan, measure, and respond to performance and scalability objectives.
It applies to every production-facing workload, regardless of hosting model, and is enforced by the
Architecture Guild with input from operations and product owners.

## Service-Level Objectives
1. Declare at least one latency, availability, and throughput SLO per service. Publish targets and owners in
   the service README and status pages.
2. Derive SLO values from customer or regulatory commitments, not solely infrastructure limits.
3. Express SLOs using a measurement window (e.g., 99.9% availability over 30 days) and document how breaches
   impact downstream teams.
4. Review SLOs quarterly with the Governance Office. Update baselines whenever feature scope materially changes.

## Instrumentation Requirements
- Emit RED metrics (Rate, Errors, Duration) for each API or asynchronous worker.
- Forward metrics and traces to the centralized observability platform with environment labels.
- Configure alerts with thresholds aligned to SLO error budgets and route notifications to the
  on-call rotation documented in the [Deployment Runbook](../processes/deployment-runbook.md).
- Capture profiling or capacity snapshots before each major release so regressions can be compared to a known baseline.
- Persist raw metrics for at least 13 months to support seasonal trending analysis and architecture planning.
- Annotate deployments in dashboards automatically so correlation between changes and regressions is trivial during incident reviews.

## Capacity Planning and Testing
1. Maintain load-test scripts (k6, Locust, or Gatling) that simulate peak usage at 1.5x historical highs.
2. Run capacity tests before quarterly planning or whenever the architecture changes significantly.
3. Document saturation points and scaling levers (e.g., autoscaling policies, cache warm-up steps) inside the
   service README and link back to this standard.
4. For data stores, record per-shard limits and failover mechanics in the runbook to aid rapid decision making.
5. Validate background jobs, queues, and batch processes with soak tests that run for at least the duration of the
   longest production workload to ensure resource leaks are caught early.

## Scalability Readiness
- Every service must list its vertical and horizontal scaling options, including rate limits imposed by shared platforms.
- Feature teams coordinate anticipated traffic spikes with capacity management at least two sprints ahead of launch.
- Caches and CDNs require documented cache-invalidation strategies plus monitoring for hit ratios below 80%.
- Where multi-region deployments exist, demonstrate failure-domain isolation via game-day exercises twice per year.

## Escalation and Governance
- Track error budget consumption weekly. If more than 50% is consumed mid-cycle, schedule a reliability review
  to prioritize remediation work.
- Declare a severity-one incident if an SLO is breached for longer than 30 minutes without mitigation. Escalate
  to the Architecture Guild and the Change Advisory Board (CAB).
- Require CAB approval for performance-impacting configuration changes during freeze windows as defined in the
  [Change-Management Policy](../policies/change-management-policy.md).
- Store evidence of SLO reviews, test results, and incident reports for at least one year to support audits.
- Share lessons learned from major incidents with the Architecture Guild and record architectural remediation actions
  in the backlog with explicit owners and due dates.

## Compliance Checklist
1. SLOs published and reviewed quarterly.
2. RED metrics instrumented with alerting tied to error budgets.
3. Capacity testing artifacts stored with the deployment runbook.
4. Escalation paths documented, including CAB membership and paging rotations.
5. Audit evidence retained for twelve months and referenced in changelog entries when standards change.

## Related Documents
- [Documentation Hygiene Guideline](../guidelines/documentation-hygiene.md)
- [Deployment Runbook](../processes/deployment-runbook.md)
- [Change-Management Policy](../policies/change-management-policy.md)
