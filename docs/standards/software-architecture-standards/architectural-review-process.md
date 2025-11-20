# Architectural Review Process

This document outlines the process for architectural reviews and sign-offs within the organization. The goal is to ensure that software designs are robust, extensible, maintainable, and aligned with the organization's long-term technical strategy.

## Purpose

The Architectural Review Process serves to:
-   Validate that proposed changes align with [Software Architecture Standards](./README.md).
-   Ensure consistent application of design patterns and principles.
-   Identify potential risks (scalability, security, performance) early in the lifecycle.
-   Promote knowledge sharing across teams.

## Distinction: Architectural Review vs. Code Review

To streamline development, it is crucial to separate concerns between architectural reviews and code reviews.

| Feature | Architectural Review | Code Review |
| :--- | :--- | :--- |
| **Focus** | **System Design & Structure** | **Implementation & Readability** |
| **Scope** | Component boundaries, data flow, design patterns, scalability, security, tech stack choices. | Syntax, formatting, variable naming, logic correctness, test coverage, error handling. |
| **Standards** | [Software Architecture Standards](./README.md) (Extensibility, Maintainability, Patterns) | [Coding Standards](../coding-standards/README.md) (Clear, readable source code) |
| **Timing** | Before implementation (Design Phase) or early in development. | During implementation (Pull Request). |
| **Artifacts** | Architecture Design Documents (ADD), Architecture Decision Records (ADR). | Source Code, Unit Tests. |

**Key Takeaway:**
*   **Architectural Standards** ensure the system is built *right* (extensible, maintainable structure).
*   **Coding Standards** ensure the code is written *well* (readable, compliant with language idioms).

## When is an Architectural Review Required?

Not every change requires a formal architectural review. Reviews are mandatory for:
1.  **New Services or Applications**: Any new deployable unit.
2.  **Significant Refactoring**: Changes affecting module boundaries or core logic.
3.  **New Dependencies**: Introducing new libraries, frameworks, or external services.
4.  **Data Model Changes**: Significant schema modifications or new data stores.
5.  **API Changes**: Breaking changes or new public-facing endpoints.
6.  **Non-Functional Impact**: Changes significantly affecting performance, security, or scalability.

## The Review Process

### 1. Preparation
The proposer must prepare the necessary documentation.
-   For specific decisions, create an [Architecture Decision Record (ADR)](./architecture-decision-record-process.md).
-   For larger designs, draft an Architecture Design Document using the [Architecture Design Document Template](./architecture-design-document-template.md).

### 2. Submission
-   Submit the documentation (ADR or ADD) as a Pull Request to the repository or a designated documentation location.
-   Tag the **Architecture Review Board (ARB)** or designated Domain Architects for review.

### 3. Review
The review can be conducted asynchronously (via PR comments) or synchronously (review meeting) depending on complexity.

**Reviewers will verify:**
-   **Alignment:** Does the design fit the broader system architecture?
-   **Modularity:** Are concerns properly separated?
-   **Extensibility:** Can the system evolve without major rewrites?
-   **Maintainability:** Is the complexity justified?
-   **Patterns:** Are standard design patterns used correctly?

### 4. Outcome & Sign-off
One of the following outcomes will be reached:
-   **Approved:** The design is accepted. The reviewer approves the PR or signs off on the document.
-   **Approved with Conditions:** Minor changes required before implementation proceeds.
-   **Request for Changes:** Significant issues identified; rework and re-review required.
-   **Rejected:** The approach is fundamentally flawed or incompatible with standards.

### 5. Implementation & Verification
Once approved, implementation begins.
-   The **Code Review** phase (during PRs) should verify that the implementation matches the approved architecture.
-   Any significant deviation from the approved design requires a re-evaluation.
