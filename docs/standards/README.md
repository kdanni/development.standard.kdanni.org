# Standards

Standards define mandatory rules for technology choices, architecture, and compliance.
They should articulate the rationale behind the rule and how adherence is validated. Each
document in this folder must spell out what teams are **required** to do, what evidence
they must produce, and where the authoritative record of compliance lives. Companion
guidelines may describe *how* to implement a standard, but the standard itself should be
concise enough for reviewers to enforce during design reviews and release checkpoints.

## Outline
- **Architecture standards** – Service boundaries, API design principles, and dependency rules. Reference
  canonical diagrams or ADRs wherever possible instead of duplicating content.
- **Language/platform standards** – Supported language versions, frameworks, and compatibility matrices,
  including explicit sunset dates for deprecated stacks.
- **Security and compliance** – Encryption requirements, data handling classifications, and audit controls,
  plus the workflow for registering exceptions.
- **Quality gates** – Testing coverage thresholds, performance targets, and release readiness criteria that
  map to CI jobs or observability dashboards.
- **Documentation of rationale** – Required sections that capture context, trade-offs, and decision records so
  future teams understand *why* the rule exists.

## Minimum Content Expectations
1. State whether the standard is mandatory or advisory and list enforcement mechanisms.
2. Provide measurable acceptance criteria or metrics.
3. Link to supporting guidelines, policies, or processes that describe implementation details.
4. Cite the escalation path for variances, including the governing forum that can approve an exception.
5. Point to the canonical evidence store (runbooks, dashboards, ADRs) so audits can sample artifacts.

## Baseline Documents
- [Service Architecture Standard](service-architecture-standard.md) – Defines guardrails, quality gates, and enforcement for HTTP services.
- [Performance and Scalability Standard](performance-and-scalability-standard.md) – Documents SLO expectations, instrumentation requirements, and escalation triggers.
- [Enterprise Architecture Standards](enterprise-architecture-standars/README.md) – Captures mindset-setting recommendations and links to the enterprise architecture knowledge base for canonical requirements.
- [Architecture Decision Record (ADR) Process Standard](software-architecture-standards/architecture-decision-record-process.md) – Describes the required lifecycle, approval, and evidence expectations for architectural decisions.
