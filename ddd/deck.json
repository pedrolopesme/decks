---
id: 8d2c9e1a-5b3f-4e92-9d8a-6c7b9a5f4d22
name: Domain-Driven Design (DDD) Interview Prep
description: 20 advanced questions on Domain-Driven Design for Staff-level engineers, focusing on strategic and tactical modeling.
author: Gemini
tags:
  - ddd
  - system-design
  - software-architecture
---

## 1. What is the difference between the "Ubiquitous Language" and a standard project glossary?
The Ubiquitous Language is a living model shared by developers and domain experts; it is used in code, documentation, and conversation to minimize translation errors between the business and implementation.

## 2. When should you use a "Bounded Context" vs. a "Subdomain"?
Subdomains define the business problem space (Core, Supporting, Generic); Bounded Contexts define the technical solution space where a specific model is applied consistently.

## 3. What is the role of an "Aggregate Root" in DDD?
The Aggregate Root is the only object in an aggregate that can be referenced from outside; it is responsible for ensuring consistency and enforcing business invariants.

## 4. How do you handle cross-aggregate consistency?
Use eventual consistency via domain events or the Saga pattern, as true ACID transactions across aggregate boundaries are an anti-pattern in distributed systems.

## 5. Explain the concept of "Value Objects" and why they should be immutable.
Value Objects represent descriptive aspects of the domain with no conceptual identity. Immutability prevents side effects and thread-safety issues, making them predictable.

## 6. What is the purpose of an "Anti-Corruption Layer" (ACL)?
The ACL prevents a legacy system or an external third-party model from "polluting" your clean domain model by acting as a translation layer.

## 7. How does "Domain Events" support the decoupling of aggregates?
Domain Events allow aggregates to signal state changes to other parts of the system without having direct dependencies, enabling a modular architecture.

## 8. What is the "Repository Pattern" in DDD and what does it abstract?
Repositories provide an interface to aggregate roots as if they were in an in-memory collection, abstracting the persistence layer (database/caching) from the domain logic.

## 9. When should you choose a "Service" over an "Entity"?
Use a Service when a business operation does not naturally belong to an Entity or Value Object (e.g., cross-aggregate calculations or external system orchestration).

## 10. What is "Context Mapping" and why is it essential in large systems?
Context Mapping documents the relationships between different Bounded Contexts (e.g., Partnership, Shared Kernel, Customer/Supplier), identifying integration points and communication styles.

## 11. What is a "Generic Subdomain" and how should you handle it?
These are parts of the business that are necessary but not competitive advantages (e.g., Auth, Billing). Buy these components rather than building them.

## 12. How does DDD handle the "Anemic Domain Model" anti-pattern?
DDD promotes "Rich Domain Models," where domain logic is encapsulated inside Entities and Value Objects rather than sitting in "manager" or "service" classes.

## 13. What is the "Shared Kernel" pattern and what are the risks?
It involves sharing a small subset of the domain model between teams. The risk is high coupling; it requires strict coordination and high communication overhead.

## 14. How do you determine the boundaries of an Aggregate?
Boundaries are determined by business invariants (what must be consistent at all times) and the transactional scope required for those invariants.

## 15. What is the difference between an Entity and a Value Object?
Entities have a distinct identity that persists through time/changes; Value Objects are defined purely by their attributes and are interchangeable if their values match.

## 16. How does "Event Sourcing" align with DDD principles?
It aligns by capturing the "intent" of the domain as a sequence of events, which creates a rich audit trail and better represents the business process compared to simple CRUD.

## 17. What is "Strategic Design" vs. "Tactical Design" in DDD?
Strategic design focuses on the big picture (Bounded Contexts, Subdomains); Tactical design focuses on the fine-grained implementation (Entities, Aggregates, Repositories).

## 18. How do you refactor an existing monolithic database into DDD-aligned microservices?
Identify Bounded Contexts, break them out into separate services, and use the Strangler Fig pattern to gradually migrate functionality and data.

## 19. What is a "Published Language" in context mapping?
A standardized, widely understood document (like a JSON schema or API specification) used to share data between two Bounded Contexts.

## 20. How do you handle "Ubiquitous Language" drift?
It requires continuous collaboration with domain experts and regular code reviews to ensure the code remains a reflection of the evolving business understanding.
