# Repository Structure Reference

This document describes the authoritative directory layout for `development.standard.kdanni.org`.
Use it as the single source of truth when adding new folders or reorganizing existing ones.
Each directory entry lists the intent, typical contents, and the maintainer who stewards updates.

## Base Layout
```
README.md
LLM_HINTS.md
LICENSE
/meta
/docs
  /roadmap
  /guidelines
  /standards
  /policies
  /processes
  /references
  /templates
```

## Directory Details
| Path | Purpose | Primary Maintainer | Notes |
| --- | --- | --- | --- |
| `README.md` | Provides the top-level overview of the repository, audience, and navigation pointers. | Repository maintainers | Must link to `meta/README.md` and highlight any active roadmap phase. |
| `LLM_HINTS.md` | Captures shared writing, tone, and formatting rules for both human and AI contributors. | Repository maintainers | Update when repository-wide style expectations change. |
| `meta/` | Hosts meta documentation, roadmap status, governance, and contribution processes. | Repository maintainers | All structural or workflow changes are recorded here first. |
| `docs/roadmap/` | Stores the long-form roadmap (`ROADMAP.md`) with phase definitions and milestones. | Repository maintainers | Reference this when updating the status table in `meta/README.md`. |
| `docs/guidelines/` | Contains documents that influence day-to-day development practices and etiquette. | Standards working group | Documents map to themes such as coding, documentation, tooling, and collaboration. |
| `docs/standards/` | Defines normative technical standards and compliance obligations. | Standards working group | Each standard states scope, rationale, and enforcement. |
| `docs/policies/` | Houses policy statements describing governance, security, release, and review rules. | Governance working group | Policies should include escalation and exception handling. |
| `docs/processes/` | Documents operational workflows such as testing, deployment, incident response, and maintenance. | Operations working group | Processes map steps to roles, inputs, outputs, and success metrics. |
| `docs/references/` | Provides glossaries, acronym lists, technology matrices, and evergreen reference material. | Knowledge management team | Keep references versioned and cross-linked to dependent documents. |
| `docs/templates/` | Offers reusable templates, checklists, and forms that accelerate consistent documentation. | Knowledge management team | Each template includes short usage notes pointing to relevant guidance. |

## Maintenance Expectations
- **Change tracking** – Update this file whenever the directory tree changes so contributors have a reliable blueprint.
- **Ownership updates** – If stewardship changes hands, adjust the Primary Maintainer column and link to relevant groups.
- **Cross-linking** – Ensure `meta/README.md` and the root `README.md` reference this structure document to avoid diverging descriptions.
