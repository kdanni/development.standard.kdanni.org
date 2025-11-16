# Phase 2 Working Checklist

This document consolidates Phase 2 execution guidance so contributors can quickly reference coding conventions, testing
requirements, and in-scope deliverables. It reflects the authoritative roadmap and repository standards.

## Coding Conventions
- Favor consistency-first approaches and rely on automated formatters/linters to keep diffs predictable.
- Use `snake_case` for functions, `PascalCase` for types, and limit files to a single responsibility whenever possible.
- Provide public docstrings and inline documentation for complex logic paths.
- Tooling requirements:
  - **Python** – `black` (100 columns) and `ruff`
  - **JavaScript/TypeScript** – `prettier` and `eslint` with shared configs
  - **Go** – `gofmt`, `golangci-lint`, and `go test ./...` before pushing changes
- Document deterministic tests and keep them runnable offline.

## Testing Requirements
- Run the full lifecycle for every change:
  1. **Unit tests** via `make test-unit` with ≥90% pass rate and coverage aligned with architecture standards.
  2. **Integration tests** via `make test-integration` ensuring zero schema drift and validated contracts.
  3. **Smoke/E2E checks** covering staging canaries with KPIs within 5% of baselines and no open P1/P2 incidents.
- Preserve test evidence under `artifacts/<service>/<build-id>/` and link artifacts in PRs and release notes.
- Log exceptions, alert `#testing-alerts` after two failed runs, escalate blockers lasting more than 24 hours, and capture
  recurring issues in monthly QA reviews.

## Phase 2 Scope Guidance
- Phase 2 is **In Progress**, owned by SME contributors, and includes a Baseline Document Audit at the end of Week 4.
- Ongoing tracking lives in `docs/meta/README.md` and the Phase 2 plan (`docs/meta/phase-2-plan.md`).
- Requirements:
  - Baseline documents must exist in every directory, backed by SMEs and reusable templates.
  - Each directory needs a navigable README plus SME ownership assignments.
  - Templates must cover review rubrics, communication briefs, and governance guidance.
  - Maintain the SME roster, template inventory, and checklist states in the meta documentation and keep roadmap/meta
    cross-links synchronized.

## Goal Checklist and Owners
| # | Deliverable | Owner | Due | Notes |
| --- | --- | --- | --- | --- |
| 1 | Documentation hygiene guideline (README expectations, changelog hygiene, examples) | Ava Patel | Week 5 midpoint | Align with coding/testing standards. |
| 2 | Performance & scalability standard (SLOs, instrumentation, escalation triggers) | Marco Lee | Week 6 handoff | Supports review milestones. |
| 3 | Change-management policy (approvals, exception logging, audit traceability) | Riley Chen | Week 6 handoff | Complements secure release policy. |
| 4 | Deployment runbook (release gates, rollback checkpoints, communications) | Jordan Smith | Week 5 midpoint | Extends testing workflow. |
| 5 | Terminology index (acronyms, services, tooling) | Morgan Alvarez | Week 5 midpoint | Expand existing glossary and link dependencies. |
| 6 | Review-rubric and communication-brief templates | Priya Nair | Completed Week 4 | Monitor for additional template needs. |
| 7 | Housekeeping (SME roster, template inventory, checklist, roadmap/meta sync) | Repository Maintainers | Ongoing | Maintain cross-links and milestone tracking. |

## Milestones
1. **Week 4 – Baseline validation**: SME acknowledgement plus template circulation.
2. **Week 5 – Deep-dive drafts**: Documentation hygiene guideline, deployment runbook, glossary expansion.
3. **Week 6 – Pre-review audit**: Standards and policies ready for validation; references updated.

## Status Tracking Notes
- Keep roadmap (`docs/roadmap/ROADMAP.md`) and meta references synchronized when updating status tables.
- Continue milestone tracking inside `docs/meta/README.md` and `docs/meta/phase-2-plan.md` for end-to-end visibility.
