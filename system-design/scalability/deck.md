---
id: 6f4d9b23-1c8a-4d7e-9f3a-2b7d5e4a8c11
name: Scalability Interview Prep
description: 20 technical questions on system scalability, covering data partitioning, consensus, and load balancing for high-scale environments.
author: Gemini
tags:
  - system-design
  - scalability
  - distributed-systems
---

## 1. What is the fundamental difference between Vertical and Horizontal scaling?
Vertical scaling (scaling up) increases the resources (CPU, RAM) of a single node; Horizontal scaling (scaling out) adds more nodes to the system to distribute the load.

## 2. What is "Consistent Hashing" and why is it used?
It is a hashing technique that distributes keys across nodes such that only $k/n$ keys need to be remapped when a node is added or removed, minimizing cache misses or data migration.

## 3. Explain the "CAP Theorem" in the context of distributed databases.
It states that a distributed system can only guarantee two out of three: Consistency, Availability, and Partition Tolerance. In the presence of a network partition, you must choose between C or A.

## 4. How does "Database Sharding" improve write scalability?
It partitions data across multiple physical databases, allowing parallel writes to different shards and reducing the I/O load on any single database instance.

## 5. What are the pros and cons of Master-Slave vs. Multi-Master replication?
Master-Slave simplifies writes but risks a single point of failure; Multi-Master improves availability and local write latency but introduces complex conflict resolution.

## 6. What is the "Load Balancer" bottleneck?
If the load balancer itself is not scaled (e.g., using a cluster of LBs or DNS round-robin), it becomes the single point of failure and a throughput limiter for the entire cluster.

## 7. How do you scale stateful services?
Move the state to an external, scalable distributed store (like Redis or Cassandra) or implement sticky sessions if the state must reside in-process.

## 8. What is the "Thundering Herd" problem in scaling?
It occurs when a cache or node fails, causing all concurrent requests to bypass the cache and slam the backend database simultaneously.

## 9. What is the difference between Synchronous and Asynchronous replication?
Synchronous replication ensures data consistency across replicas before confirming the write, but increases latency; Asynchronous replication improves write performance at the risk of losing recent data on failover.

## 10. When would you use a "Global Server Load Balancing" (GSLB)?
To route users to the geographically closest data center, reducing network latency and improving availability by failing over to a healthy region.

## 11. Explain the concept of "Data Locality".
It is the strategy of moving the computation to where the data resides, rather than moving the data to the computation, to minimize network bandwidth and latency.

## 12. What is the role of a "Circuit Breaker" in a scalable system?
It prevents a failing service from causing cascading failures by "tripping" the circuit, immediately rejecting requests to the failing service until it recovers.

## 13. How does "Denormalization" help in read-heavy scaling?
It reduces the need for expensive "joins" across tables, which are slow to execute in distributed/sharded databases.

## 14. What is the trade-off of "Eventual Consistency"?
It provides high availability and low latency by allowing temporary data discrepancies across replicas, requiring the application to handle stale reads.

## 15. How do "Read Replicas" help with scalability?
They offload read traffic from the primary master database, allowing the system to scale reads linearly by adding more read nodes.

## 16. What is the purpose of "Bulkheading" in distributed systems?
It is a fault-tolerance pattern that isolates resources (e.g., thread pools or connections) so that if one service fails, it only consumes its dedicated resources and doesn't exhaust the entire system.

## 17. Why is "Multi-Tenancy" a scalability challenge?
It requires strict resource isolation to prevent "noisy neighbor" scenarios where one high-traffic tenant starves others of resources.

## 18. How do you scale search functionality?
Use an inverted index and distribute it across multiple search nodes (e.g., Elasticsearch shards) based on document ID or term ranges.

## 19. What is the "PACELC" theorem?
It extends CAP: If there is a Partition (P), trade-off between Availability (A) and Consistency (C); Else (E), trade-off between Latency (L) and Consistency (C).

## 20. How do you handle massive spikes in traffic (Burst Scaling)?
Use auto-scaling groups based on real-time metrics, move heavy processing to background queues, and rely on aggressive edge caching (CDN).
