# Coding Conventions Guideline

## Goal and Audience
This guideline aligns contributors on baseline coding conventions across repositories. It applies to all developers and reviewers contributing to first-party services hosted under the `development.standard.kdanni.org` domain.

## Principles
- **Consistency over preference** – When in doubt, follow the conventions documented here to keep diffs small and codebases predictable.
- **Automation first** – Prefer formatter and linter automation over manual enforcement to reduce reviewer overhead.
- **Documentation as code** – Explain non-obvious logic paths using inline comments and link to relevant standards or policies.

## Language-Agnostic Practices
1. Use descriptive identifiers written in `snake_case` for functions and `PascalCase` for types.
2. Keep files focused on a single responsibility; extract helpers to modules when the file exceeds ~300 lines.
3. Require docstrings for public functions and modules. Include expected inputs, outputs, and edge-case behaviors.
4. Enforce strict linting with the repository-approved tools (see [Tooling Practices](README.md)).
5. Write deterministic unit tests with clear setup/act/assert sections. Tests must run locally without network access.

## Language-Specific Notes
| Language | Formatter | Linter | Additional Notes |
| --- | --- | --- | --- |
| Python | `black` (`line-length 100`) | `ruff` | Prefer dataclasses for structured data; avoid implicit wildcard imports. |
| JavaScript/TypeScript | `prettier` | `eslint` (`typescript-eslint` plugin) | Use ESLint configs stored under `/configs/lint/`. |
| Go | `gofmt` | `golangci-lint` | Keep exported packages documented; run `go test ./...` before pushing. |

## Branching and Review Expectations
- Name feature branches using `feature/<short-topic>` and fix branches with `fix/<issue-id>-<topic>`.
- Require at least one peer reviewer plus one maintainer for changes touching standards or policies.
- Capture reviewer decisions in the pull request template and link to related guidelines or standards.

## Related Documents
- [Secure Release Policy](../policies/secure-release-policy.md)
- [Service Architecture Standard](../standards/service-architecture-standard.md)
- [Testing Workflow](../processes/testing-workflow.md)
