# Design Pattern Catalog

This catalog summarizes commonly used patterns grouped by system-level architecture patterns and component-level design patterns. Each entry notes when to apply the pattern, expected benefits, and typical trade-offs so teams can make consistent architectural decisions.

## Architecture Patterns (system-level)

| Pattern | Problem Solved | Apply When | Trade-offs and Risks |
| --- | --- | --- | --- |
| Layered Architecture | Separates responsibilities into presentation, domain, and data layers with clear boundaries. | Products need straightforward separation of concerns and predictable deployment units. | Can encourage tight coupling between layers if boundaries are not enforced; performance overhead from deep call stacks. |
| Modular Monolith | Keeps a single deployable artifact while enforcing module boundaries inside the codebase. | You want monolithic deployment with internally isolated modules for teams to own independently. | Module boundary erosion without tooling and reviews; large binary still impacts full deployment cycles. |
| Microservices | Decomposes a system into independently deployable services aligned to business capabilities. | Teams require isolated release cadence, fault isolation, and the ability to scale components independently. | Higher operational complexity, distributed tracing overhead, and consistency challenges across services. |
| Event-Driven Architecture | Uses events for loose coupling and asynchronous communication between components. | Workloads need reactive behavior, auditability of state changes, or decoupled integrations. | Event ordering and idempotency must be designed; debugging becomes harder without strong observability. |
| Command Query Responsibility Segregation (CQRS) | Separates write models from read models to optimize performance and scalability per workload. | Read-heavy systems benefit from specialized projections while maintaining transactional write paths. | Requires synchronization between models; increases storage and operational overhead. |
| Service-Oriented Architecture (SOA) | Groups services around shared schemas and contracts, often mediated by an enterprise service bus. | Legacy landscapes or regulated environments need canonical contracts and centralized governance. | ESB mediation can become a bottleneck; contract versioning and change control may slow delivery. |

## Design Patterns (component-level)

| Pattern | Category | Problem Solved | Apply When | Trade-offs and Risks |
| --- | --- | --- | --- | --- |
| Factory Method | Creational | Encapsulates object creation to select implementations without callers knowing concrete classes. | Callers need to create related objects while keeping construction logic centralized. | Can proliferate factories; excessive abstraction may hide required configuration. |
| Abstract Factory | Creational | Provides a family of related objects that share a common theme without specifying their concrete classes. | Multiple product variants must stay consistent (e.g., UI themes, data sources) across a subsystem. | Additional indirection; can be heavy if only a few variants exist. |
| Builder | Creational | Simplifies construction of complex objects with many optional parameters. | Objects require stepwise construction or fluent configuration without many overloaded constructors. | More code to maintain; builders can drift from the underlying object if not tested. |
| Singleton | Creational | Ensures a class has a single instance and provides a global access point. | A shared resource (e.g., configuration cache) must remain unique within a process. | Can hide dependencies and hinder testability; avoid global state leakage. |
| Adapter | Structural | Translates one interface into another to allow otherwise incompatible components to collaborate. | Integrating third-party or legacy components with mismatched interfaces. | Adds indirection and potential performance overhead; adapters can obscure capability gaps. |
| Facade | Structural | Provides a simplified interface to a complex subsystem. | You want to shield callers from implementation details or reduce onboarding complexity. | Facades can become god-objects if they accumulate too many responsibilities. |
| Decorator | Structural | Attaches additional responsibilities to objects dynamically without altering the original class. | Cross-cutting behaviors (e.g., logging, caching) should be composed at runtime. | Deep decorator chains complicate debugging; ordering of decorators affects behavior. |
| Composite | Structural | Treats individual objects and compositions uniformly through a shared interface. | Hierarchical data or tree structures require uniform traversal and operations. | Can blur distinctions between leaf and composite behaviors; careless recursion can impact performance. |
| Strategy | Behavioral | Defines a family of algorithms and makes them interchangeable at runtime. | Business rules vary by context (e.g., pricing models) and should be selected dynamically. | Too many strategies increase configuration complexity; requires clear selection rules. |
| Observer | Behavioral | Establishes one-to-many dependency so observers are notified of subject state changes. | Multiple components react to state changes (e.g., UI updates, domain events). | Risk of update storms or notification loops; observers must handle stale data safely. |
| Command | Behavioral | Encapsulates a request as an object to support undo/redo, queuing, or logging. | Actions must be replayed, audited, or executed asynchronously. | Command proliferation increases boilerplate; commands need clear idempotency rules. |
| Template Method | Behavioral | Defines the skeleton of an algorithm, deferring variable steps to subclasses. | Common algorithm structure exists with well-understood extension points. | Inheritance can reduce flexibility; overuse may lead to fragile base classes. |
| State | Behavioral | Allows an object to alter its behavior when its internal state changes. | Domain behavior depends heavily on discrete states with distinct transitions. | State explosion without careful modeling; transition logic must avoid cyclical traps. |

## Usage Notes

- Patterns are composable: architecture patterns set system boundaries while design patterns guide implementations inside those boundaries.
- When selecting a pattern, capture the rationale, alternatives considered, and the expected lifespan of the choice in architecture decision records.
- Reassess patterns during major releases or when non-functional requirements (scale, reliability, compliance) shift.
