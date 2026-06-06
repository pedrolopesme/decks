# Staff Engineer Interview Topic Map

This repo already covers a useful core of system design, DSA, DDD, design patterns, and Go concurrency.
The list below is the recommended Staff-level topic map for big tech interviews at companies like Uber, Meta, and Google.

Use these as deck families. Each one should stay focused enough to become a 20-card deck without overlap.

## Priority 1: Core System Design

| Deck family | Why it matters | Key question themes |
|---|---|---|
| System Design Fundamentals | Every Staff design loop starts here | requirements, constraints, APIs, data flow, SLIs/SLOs, capacity planning, tradeoffs |
| Scalability and Capacity | Base layer for large-scale architecture | sharding, replication, load balancing, autoscaling, hotspots, traffic spikes |
| Distributed Systems Fundamentals | Core Staff-level depth check | consensus, quorum, leader election, consistency models, failure modes |
| Data Stores and Modeling | Critical for real production systems | RDBMS vs NoSQL, indexing, schema evolution, transactions, polyglot persistence |
| Caching and State Management | Common performance and reliability topic | cache-aside, invalidation, stampede, hot keys, TTLs, multi-region caching |
| Event-Driven Architecture | Essential for async backend systems | delivery semantics, ordering, idempotency, sagas, outbox, replay, DLQs |
| Reliability and Resilience | Staff engineers are judged on operating systems | retries, timeouts, circuit breakers, bulkheads, graceful degradation, incident response |
| APIs and Service Boundaries | Important in modular service design | REST/gRPC, versioning, backward compatibility, idempotency, service decomposition |
| Search, Feed, and Ranking | Common at Meta/Google/Uber scale | indexing, freshness, fanout, ranking tradeoffs, deduping, personalization |
| Networking, Latency, and Edge | Often used to probe practical depth | DNS, TCP/HTTP basics, CDN/edge, tail latency, batching, compression |
| Security, Privacy, and Abuse | Required for production design quality | authn/authz, secrets, PII, tenant isolation, rate limiting, fraud/abuse controls |
| Data Pipelines and Analytics | Important for modern large-scale platforms | CDC, ETL/ELT, stream processing, warehouse/lakehouse, replay, schema evolution |

## Priority 2: Core Coding and Algorithms

| Deck family | Why it matters | Key question themes |
|---|---|---|
| DSA Core Patterns | Fastest signal for coding rounds | arrays, strings, hash maps, two pointers, sliding window, prefix sums, stacks, queues |
| Trees, Tries, and Heaps | Frequent interview staples | recursion, traversals, BSTs, tries, priority queues, ordered retrieval |
| Graphs and Union-Find | Common medium/hard coding territory | BFS, DFS, shortest path, topological sort, connectivity, cycle detection |
| Dynamic Programming and Backtracking | Staff-level coding still needs rigor | state design, memoization, tabulation, combinatorics, pruning |
| Greedy and Sorting | Good for problem decomposition | invariant reasoning, interval scheduling, selection, stable vs unstable sort tradeoffs |

## Priority 3: Architecture and Craft

| Deck family | Why it matters | Key question themes |
|---|---|---|
| OOP and Design Patterns | Useful for system decomposition and code quality | SOLID, factories, builders, decorators, observers, adapters, mediators |
| Domain-Driven Design | Important for modeling complex product domains | bounded contexts, aggregates, domain events, ACLs, modular monolith vs microservices |
| Go Concurrency and Runtime | Relevant when the role is Go-heavy | goroutines, channels, mutexes, context, race conditions, cancellation, worker pools |

## Priority 4: Staff Behavioral

| Deck family | Why it matters | Key question themes |
|---|---|---|
| Staff Behavioral and Leadership | Mandatory for Staff loops | leading through influence, conflict, ambiguity, prioritization, mentoring, hiring, failures, execution |

## Recommended Order To Generate Decks

1. System Design Fundamentals
2. Scalability and Capacity
3. Distributed Systems Fundamentals
4. Reliability and Resilience
5. Data Stores and Modeling
6. Caching and State Management
7. Event-Driven Architecture
8. APIs and Service Boundaries
9. DSA Core Patterns
10. Trees, Tries, and Heaps
11. Graphs and Union-Find
12. Dynamic Programming and Backtracking
13. OOP and Design Patterns
14. Domain-Driven Design
15. Staff Behavioral and Leadership

## Notes

- The repo already contains strong coverage for caching, CAP, scalability, EDA, databases, OOP patterns, DDD, DSA, and Go concurrency.
- The biggest missing piece for a true Staff interview prep set is behavioral/leadership coverage.
- The most valuable next decks are the ones that combine high interview frequency with high production relevance.
