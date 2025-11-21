# Architecture Design Document: [Project/Feature Name]

## Metadata
| Attribute | Details |
| :--- | :--- |
| **Author(s)** | [Name] |
| **Status** | [Draft / In Review / Approved / Deprecated] |
| **Date** | [YYYY-MM-DD] |
| **Reviewers** | [Name], [Name] |
| **Approvers** | [Name] |
| **ADR References** | [Link to ADRs if applicable] |

## 1. Context and Scope
*Briefly describe the problem being solved. What is the business context? What are the limitations of the current system?*

### 1.1. In Scope
* *List what is covered by this design.*

### 1.2. Out of Scope
* *List what is explicitly NOT covered.*

## 2. Goals and Non-Goals
### 2.1. Goals
* *Primary objectives (e.g., improve latency, add new capability).*

### 2.2. Non-Goals
* *Objectives that are not being pursued at this time.*

## 3. Proposed Architecture
*Provide a high-level overview of the solution. Use diagrams (e.g., C4 Context or Container diagrams) to illustrate.*

### 3.1. High-Level Diagram
* *[Insert Diagram]*

### 3.2. Component Description
* *Describe the major components and their roles.*

## 4. Detailed Design
*Dive into the specifics. This section can be broken down further as needed.*

### 4.1. API Design / Interface Specifications
* *Link to OpenAPI specs or describe key endpoints/interfaces.*

### 4.2. Data Model
* *Schema changes, database technologies, or data flow descriptions.*

### 4.3. Interactions and Flows
* *Sequence diagrams or step-by-step descriptions of critical paths.*

## 5. Alternatives Considered
*Describe other approaches that were evaluated and why they were rejected. This is crucial for decision governance.*

| Alternative | Pros | Cons | Reason for Rejection |
| :--- | :--- | :--- | :--- |
| Option A | ... | ... | ... |
| Option B | ... | ... | ... |

## 6. Quality Attributes (Non-Functional Requirements)
*Explain how the design addresses cross-cutting concerns.*

* **Scalability:** *How will the system handle increased load?*
* **Performance:** *Latency/throughput targets.*
* **Security:** *Authentication, authorization, encryption, compliance.*
* **Reliability:** *Availability, fault tolerance, disaster recovery.*
* **Observability:** *Logging, metrics, tracing.*

## 7. Operational Readiness
* **Deployment:** *How will this be deployed? (Blue/Green, Canary, etc.)*
* **Configuration:** *How is configuration managed?*
* **Dependencies:** *New libraries, services, or infrastructure required.*
* **Rollback Plan:** *Steps to revert if things go wrong.*

## 8. Migration Plan
*If replacing an existing system, how will data or traffic be migrated?*

## 9. Appendices
* *Glossary*
* *References*
