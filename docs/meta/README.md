# Meta Documentation

This document describes how the knowledge base repository is organized, provides the roadmap used to plan work, tracks progress across the roadmap, and lists the working directories that make up the base structure.

## Roadmap Overview
The knowledge base will be completed in four phases. Detailed descriptions live in [docs/roadmap/ROADMAP.md](../roadmap/ROADMAP.md).

| Phase | Objective | Key Deliverables |
| --- | --- | --- |
| Phase 1 – Foundations | Establish structure and conventions | Directory layout, meta documentation, contribution guardrails |
| Phase 2 – Content Development | Produce baseline documents for each category | Draft guidelines, standards, policies, processes, and templates |
| Phase 3 – Review and Validation | Ensure accuracy and cross-document consistency | Review workflow, terminology validation, dependency mapping |
| Phase 4 – Enablement and Adoption | Drive usage and maintenance | Onboarding guide, feedback process, adoption metrics |

## Roadmap Status
| Phase | Current Status | Owner / Role | Next Checkpoint |
| --- | --- | --- | --- |
| Phase 1 – Foundations | In progress | Repository maintainers | Finalize structure and document contribution standards |
| Phase 2 – Content Development | Planned | Subject-matter experts | Begin drafting category documents once Phase 1 closes |
| Phase 3 – Review and Validation | Planned | Review board | Define reviewers and validation tooling after drafts are ready |
| Phase 4 – Enablement and Adoption | Planned | Product enablement | Prepare onboarding materials following validation phase |

_Status Legend: Not Started → Planned → In Progress → Complete._

## Working Directories
| Directory | Purpose |
| --- | --- |
| `docs/roadmap/` | Contains the authoritative repository roadmap and milestone definitions. |
| `docs/meta/` | Hosts this meta documentation and any repository-level coordination notes. |
| `docs/guidelines/` | Holds coding, documentation, and collaboration guidelines. |
| `docs/standards/` | Tracks technical standards, conventions, and compliance requirements. |
| `docs/policies/` | Contains policy statements such as security, release, and review policies. |
| `docs/processes/` | Documents workflows for testing, deployment, incident response, and maintenance. |
| `docs/references/` | Stores glossaries, links, and reference material needed to understand the knowledge base. |
| `docs/templates/` | Provides contribution templates, checklists, and forms that authors can reuse. |

## How to Extend the Knowledge Base
1. Review the roadmap to understand current priorities.
2. Locate the relevant working directory for your contribution.
3. Add or update documents following the repository style guidance in `LLM_HINTS.md`.
4. Request a review aligned with the roadmap status table before merging changes.
