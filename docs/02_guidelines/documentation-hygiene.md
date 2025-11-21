# Documentation Hygiene Guideline

## Goal and Audience
This guideline defines the minimum documentation hygiene requirements for application and platform teams.
It applies to repository maintainers, feature owners, and reviewers who create or validate README content,
changelogs, and inline comments.

## Core Principles
1. **Every document has a purpose** – State the intent, target audience, and current status in the opening
   section of each README or runbook.
2. **Traceability beats tribal knowledge** – Link to issues, pull requests, and related standards so future
   readers can understand why changes were made.
3. **Small, frequent updates** – Update documentation as part of the same change that modifies behavior to
   avoid drift between code and supporting references.

## README Expectations
| Section | Required Content | Notes |
| --- | --- | --- |
| Overview | Purpose, ownership, and consumers. | Keep it to two paragraphs and link to the owning team roster in `meta/README.md`. |
| Getting Started | Setup prerequisites, commands, and environment variables. | Provide copy/paste commands and reference tooling from [Coding Conventions](coding-conventions.md). |
| Operational Status | Deployment targets, monitoring entry points, and SLO statements. | Reference the [Performance and Scalability Standard](../03_standards/performance-and-scalability-standard.md) for metrics. |
| Directory Map | Short description of each top-level folder in the repo. | Highlight templates or generated assets so reviewers know what not to edit manually. |
| Maintenance Log | Link to the changelog or release notes. | Include a date-stamped summary for material updates.

## Changelog Hygiene
1. Record every production-affecting change in `CHANGELOG.md` using Keep a Changelog format (`Added`, `Changed`, `Fixed`).
2. Include the pull request or issue ID for traceability. Example: `- Added deployment runbook (PR #123).`
3. Group unreleased entries under an "Unreleased" heading until tagged. Move entries to the release version
   when artifacts are published.
4. Capture approvals for policy or standard updates inside the changelog entry so auditors can confirm sign-off.
5. If a change is reverted, leave the original entry and add a follow-up bullet noting the revert date and reason.

## Inline Documentation Expectations
- Prefer docstrings or KDoc-style summaries for public APIs that explain side effects and error handling.
- When commenting inline, describe *why* the code exists, not *what* it does; the code already shows the "what".
- Link to design docs, ADRs, or policies for workflows with compliance requirements (e.g., [Change-Management Policy](../04_policies/change-management-policy.md)).
- Use TODO comments sparingly and always include an owner or issue ID.

## Hygiene Checklist
1. README contains the five sections listed above and was reviewed within the last quarter.
2. `CHANGELOG.md` has no gaps greater than one release cycle between entries.
3. Inline comments were updated to reflect new behavior before merging code.
4. Related guidelines, standards, or policies are linked from the document being updated.
5. Evidence of approvals (where required) is present in the changelog or pull request template.

## Related Documents
- [Coding Conventions Guideline](coding-conventions.md)
- [Change-Management Policy](../04_policies/change-management-policy.md)
- [Deployment Runbook](../05_processes/deployment-runbook.md)
- [Performance and Scalability Standard](../03_standards/performance-and-scalability-standard.md)
