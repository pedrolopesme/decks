---
id: 2d1b8e7c-3a9f-4b5d-8e6a-1c7f9d8b3a44
name: CAP Theorem Interview Prep
description: 20 technical questions on the CAP theorem, distributed consensus, and trade-offs in distributed data systems.
author: Gemini
tags:
  - distributed-systems
  - cap-theorem
  - system-design
---

## 1. What does each letter in CAP stand for?
Consistency (every read receives the most recent write), Availability (every request receives a non-error response), and Partition Tolerance (the system continues to operate despite network failures).

## 2. Why is Partition Tolerance considered non-negotiable in distributed systems?
Because network partitions are inevitable in distributed systems; if you do not handle them (P), your system will crash or lose data during any network glitch.

## 3. Does CAP mean you must choose between C and A in all scenarios?
No. You only face the trade-off during a network partition. When the network is healthy, a well-designed system can provide both C and A.

## 4. What is the difference between "Consistency" in CAP and "ACID Consistency"?
CAP consistency refers to "Linearizability" (all nodes see the same data at the same time); ACID consistency refers to the database transitioning from one valid state to another, maintaining invariants.

## 5. What is an AP system and when is it preferred?
An AP system favors Availability and Partition Tolerance. It is preferred for systems where high uptime and low latency are critical (e.g., shopping carts, social media feeds).

## 6. What is a CP system and when is it preferred?
A CP system favors Consistency and Partition Tolerance. It is preferred for financial systems or inventory management where stale data could lead to business errors.

## 7. What does "Eventual Consistency" imply for an AP system?
It implies that while the system remains available during a partition, it guarantees that replicas will converge to the same value *eventually* once the partition is resolved.

## 8. Can a distributed system be CA?
Technically, yes, but only if the network never partitions. In real-world distributed systems, a CA system is a "single-node" database, as it cannot survive network failures.

## 9. How do you resolve conflicts in AP systems after a partition is healed?
Use techniques like Last-Write-Wins (LWW), Vector Clocks, or Conflict-Free Replicated Data Types (CRDTs).

## 10. What is a "Read Repair"?
A strategy where the system checks data across multiple replicas during a read; if a mismatch is found (due to a previous partition), it corrects it on the fly.

## 11. What is the role of a "Quorum" in balancing C and A?
Quorums (e.g., $W+R > N$) allow you to tune the consistency level. By increasing the read/write quorum, you favor Consistency; by decreasing them, you favor Availability.

## 12. Explain the "PACELC" theorem in relation to CAP.
PACELC states that even when there is no partition (E), there is still a trade-off between Latency (L) and Consistency (C).

## 13. What is "Linearizability"?
A strong consistency model where, once a write is acknowledged, any subsequent read must reflect that write or a later one.

## 14. What are the dangers of "Stale Reads" in an AP system?
Inaccurate decision-making, such as a user purchasing an item that is actually out of stock, or displaying outdated account balances.

## 15. How does the "Paxos" or "Raft" algorithm relate to CAP?
They are consensus protocols used to build CP systems. They ensure that a majority of nodes agree on the state, even if some nodes fail or the network is partitioned.

## 16. What is the impact of high-speed networks on CAP?
Faster networks reduce the duration and frequency of partitions, allowing developers to implement stronger consistency models with less impact on perceived availability.

## 17. How do you decide between a CP and AP database for a new microservice?
Evaluate the "Cost of Inconsistency" vs. "Cost of Downtime." If the business cost of a wrong read is high, pick CP; if the cost of not being able to read/write is high, pick AP.

## 18. What is a "Split-Brain" scenario?
A result of a partition where two parts of a system both believe they are the "master" and accept conflicting writes, leading to significant data integrity issues.

## 19. How does "Fencing" help in CP systems?
Fencing tokens prevent a "zombie" node (which was partitioned away) from performing writes on a resource after a new master has been elected.

## 20. Why is the CAP Theorem often misunderstood?
It is often misunderstood as a "pick 2 of 3" menu, when it is actually a constraint on how systems behave specifically during network failure.
