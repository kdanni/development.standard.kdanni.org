# Processes

Process documents describe how work is executed from trigger to completion.
They should provide enough detail that a new contributor can run the workflow with minimal guidance.
Each document in this directory is intended to function as an operational guide, not just a narrative overview: it should spell
out prerequisites, decision points, owners, tooling, and measurable outcomes so teams can self-serve with confidence.

## Outline
- **Testing workflows** – Unit, integration, and end-to-end pipelines including sign-off criteria.
- **Deployment runbooks** – Environment promotion steps, rollback plans, and monitoring checkpoints.
- **Incident response** – Detection, triage, communication, and post-incident review activities.
- **Maintenance cadences** – Patch schedules, dependency updates, and lifecycle milestones.
- **Operational readiness** – Role matrices, prerequisite checklists, and success metrics.

## Minimum Content Expectations
1. Include a process overview, trigger, exit criteria, and responsible roles.
2. Provide step-by-step instructions supplemented with diagrams or tables when needed.
3. Link to supporting templates, policies, or standards that govern the process.
4. Capture metrics, decision logs, and example timelines so teams can benchmark their execution.

## Authoring Checklist
- **Clarity** – Use verbs that describe observable actions ("submit CAB request", "capture logs") rather than vague statements.
- **Evidence** – Indicate what artifacts prove the step was completed (screenshot, ticket ID, pipeline log).
- **Escalation** – Document when to notify leadership or invoke a higher-severity workflow.
- **Tooling** – Reference the canonical scripts, dashboards, or automations so the reader does not have to guess how a step is
  executed.

## Maturity Guidance
- **Level 1 – Descriptive**: outlines what happens today. Useful for onboarding but prone to drift.
- **Level 2 – Prescriptive**: defines owners, timing, and acceptance criteria. Enables repeatability and auditability.
- **Level 3 – Measurable**: links KPIs and feedback loops to the process to ensure continuous improvement.

Each document should strive for Level 2 at a minimum and identify the data sources needed to reach Level 3.

## Baseline Documents
- [Testing Workflow](testing-workflow.md) – Defines the trigger, stages, evidence collection, and escalation paths for automated test suites.
- [Deployment Runbook](deployment-runbook.md) – Details release gates, monitoring expectations, rollback procedures, and communication protocols.
- [Waterfall Development Process](waterfall/README.md) – Documents sequential delivery expectations, governance checkpoints, and required artifacts.
- [Agile Development Process](agile/README.md) – Describes iterative delivery cadences, team roles, and collaboration ceremonies.
- [Hybrid Development Process](hybrid/README.md) – Explains how to blend classic governance with Agile execution, including conflict resolution guidance.
- [Process Overview & Mapping](process-overview-and-mapping.md) – Compares the methodologies, maps roles, and aligns deliverables across the approaches.

## How to Contribute Updates
1. **Identify the Gap** – Capture the operational problem or tribal knowledge you are codifying. Align with affected teams before
   editing to prevent conflicting practices.
2. **Draft and Peer Review** – Propose changes via pull request, tag process owners, and pilot the new guidance with at least one
   delivery team. Note lessons learned in the PR description.
3. **Publish and Evangelize** – After approval, update related runbooks, templates, and training material. Announce the change in
   the delivery channel and schedule a retrospective to confirm the process behaves as expected.

Treat these documents as living assets: every incident, audit, or experiment should result in an incremental improvement here.
