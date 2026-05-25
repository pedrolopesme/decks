---
id: 5e3f1c91-b6d2-4f8a-9e3c-8a7e3d2b9f44
name: Event-Driven Architecture (EDA) Interview Prep
description: 20 advanced questions on Event-Driven Architecture, focusing on distributed systems patterns, consistency, and resilience for Staff-level engineers.
author: Gemini
tags:
  - system-design
  - event-driven
  - distributed-systems
---

## 1. How do you ensure exactly-once processing semantics in an event-driven system?
While true exactly-once is impossible, you achieve "effectively once" by combining at-least-once delivery with strict idempotency at the consumer level (e.g., tracking processed Event IDs in a database).

## 2. Compare Orchestration vs. Choreography in the context of the Saga pattern.
Orchestration uses a central coordinator (state machine) to manage the workflow, while Choreography relies on services listening to events and reacting independently, offering higher decoupling but higher complexity in visibility.

## 3. How do you handle "Poison Messages" in a high-throughput message broker?
Redirect them to a Dead-Letter Queue (DLQ) after a fixed number of retries, alert on volume thresholds, and implement an automated or manual inspection process to fix or purge them.

## 4. What is the impact of schema evolution in event streams?
It risks breaking downstream consumers. Use a Schema Registry to enforce backward/forward compatibility rules (e.g., Avro, Protobuf) and manage versioning strictly.

## 5. How do you guarantee event ordering in a partitioned message stream (like Kafka)?
Order is only guaranteed within a partition. You must ensure all events related to a specific entity (e.g., OrderID) are mapped to the same partition using a consistent hashing key.

## 6. How do you manage distributed transactions without two-phase commit?
Use the Transactional Outbox pattern or Event Sourcing to ensure the state change and the event publication happen atomically, eventually leading to consistency.

## 7. What is "Event Sourcing" and when would you use it?
Event Sourcing stores the state of a system as a sequence of events. It is preferred when you need a perfect audit trail, the ability to "time travel" (replay state), or complex analytics on historical state changes.

## 8. What is the danger of "distributed monoliths" in an event-driven system?
When services are so tightly coupled via events that changing one requires changing all others, you lose the primary benefit of EDA (loose coupling) while gaining the complexity of distributed systems.

## 9. How do you handle "Eventual Consistency" in a user-facing application?
Design the UI to handle latency (optimistic updates), provide visual feedback of processing states, or implement read-your-writes consistency if strictly required by the business.

## 10. Explain the role of an Event Mesh in large-scale organizations.
An event mesh connects different event brokers across multiple clouds and on-premise environments, enabling dynamic routing and discovery of events regardless of the underlying infrastructure.

## 11. How does "Backpressure" manifest and get managed in an EDA?
Backpressure occurs when consumers are slower than producers, filling up buffers. Manage it by scaling consumers, implementing rate limiting, or using flow control mechanisms provided by the messaging protocol.

## 12. What are the trade-offs between Pull-based and Push-based event consumption?
Pull-based (polling) allows consumers to control their own pace, preventing overload; Push-based provides lower latency but risks overwhelming the consumer.

## 13. How do you ensure data integrity during "Event Replay"?
The system must be built for re-entrancy. Idempotency is non-negotiable, and you must ensure that replaying events does not trigger side-effect-heavy actions (e.g., sending duplicate emails).

## 14. What is the purpose of a "Change Data Capture" (CDC) connector?
CDC streams database row-level changes into an event broker without modifying the application code, acting as an "event bridge" between legacy data stores and modern event-driven services.

## 15. How do you handle long-running processes that require state?
Use a Process Manager or an orchestrator that tracks the state of the long-running transaction and emits events to trigger subsequent steps.

## 16. What is the difference between an "Event" and a "Command"?
A command expresses an intention (e.g., "ChangePassword"), while an event represents a fact that has already occurred (e.g., "PasswordChanged").

## 17. How do you monitor latency in an asynchronous system?
Trace events using Distributed Tracing (e.g., OpenTelemetry) with Trace IDs and Span IDs passed through event headers to visualize the flow and identify bottlenecks.

## 18. Why would you choose "Log Compaction" in a stream?
It keeps the latest version of every record for a given key, which is essential for "state snapshots" where you only care about the current value of an entity.

## 19. How do you handle "Event Fragmentation" in a high-scale environment?
Fragmentation occurs when an event size exceeds the broker's limit. You should store the payload in an external store (e.g., S3) and pass a URI reference in the event header instead.

## 20. When does EDA become a "bad idea"?
When you have a simple domain, require immediate synchronous consistency, or when the team lacks the operational maturity to debug the inherent complexity of asynchronous, distributed failures.
