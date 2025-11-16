# Contribution Guide

This guide explains how to add or update documentation within the repository, with special attention to
referencing, naming, and review expectations. Follow these conventions alongside the shared style
rules in `LLM_HINTS.md`.

## Workflow
1. **Check the roadmap** – Confirm which phase is active using `docs/meta/README.md` and read the detailed
   milestones in `docs/roadmap/ROADMAP.md`.
2. **Propose scope** – Open an issue or note describing the document you plan to create or update.
3. **Create a branch** – Use descriptive branch names such as `feature/add-testing-process` or
   `docs/update-standards-layout`.
4. **Author content** – Write Markdown documents that:
   - Include a clear title (`# Heading`), context paragraph, and structured sections.
   - Cite source material inline using repository-relative links or external references as needed.
   - Reference related documents with full paths (e.g., `docs/processes/testing.md`).
5. **Validate formatting** – Run Markdown linting (when available) and ensure headings follow a logical hierarchy.
6. **Request review** – Tag the working group responsible for the directory (see `STRUCTURE.md`).
7. **Merge and document** – After approval, update any affected index or README files and note the change in
   relevant changelog sections.

## Naming Conventions
- **Files** – Use lowercase, hyphenated filenames that describe the topic (`deployment-runbook.md`).
- **Directories** – Keep existing top-level directories; add subdirectories only when multiple documents
  share the same theme.
- **Headings** – Use sentence case for headings beyond the document title to match repository tone.

## Referencing Guidelines
- **Internal links** – Prefer relative links (e.g., `[Process Outline](../processes/README.md)`) so navigation works
  in any context.
- **External sources** – Include the resource name and URL inline; add a short rationale for why the reference matters.
- **Cross-document context** – When a document depends on another, state the dependency explicitly in a
  “Related Documents” or “Dependencies” section.

## Review Expectations
- Provide at least one reviewer from the responsible working group plus one repository maintainer for
  cross-cutting topics.
- Reviewers validate:
  - Alignment with roadmap goals and existing outlines.
  - Consistency with style guidance from `LLM_HINTS.md`.
  - Proper citation of related documents and sources.
- Use pull request templates (once added under `docs/templates/`) to ensure each submission captures context,
  testing, and outstanding risks.
