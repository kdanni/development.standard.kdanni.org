# Coding Standards

This directory captures the baseline coding standards for the organization. Each language
or framework-specific document should answer *what good looks like* and cite the
automation that enforces the rules.

## Minimum Expectations for Each Language Standard
1. **Scope and maturity** – Clarify which repositories must adopt the standard, supported runtime versions,
   and the deprecation timeline for older compilers or interpreters.
2. **Style and ergonomics** – Reference the canonical formatter configuration, naming conventions, and
   error-handling idioms. Include links to shared `.editorconfig` or formatter configs stored in the tooling repo.
3. **Security defaults** – Document required linters (e.g., `bandit`, `gosec`) and secure coding checklists.
4. **Testing expectations** – Define required unit, integration, and contract test coverage and how tests
   are organized in the repository layout.
5. **Review automation** – Describe which CI bots enforce formatting, linting, and coverage so reviewers
   can focus on architectural risks rather than style debates.

## How to Contribute
- Start each new standard with an ADR referencing the motivating incidents or audit findings.
- Provide ready-to-copy snippets (Makefile targets, GitHub Actions) that teams can drop into their repos.
- Link back to relevant guidance in `docs/02_guidelines` so the standards remain lightweight yet actionable.
