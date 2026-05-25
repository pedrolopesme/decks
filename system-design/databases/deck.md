---
id: 1f4b8c92-7d3a-4e5b-8f1c-6d2a9e3b4f55
name: Relational vs. Non-Relational Databases Interview Prep
description: 20 comparative questions focusing on data modeling, scaling, and architectural trade-offs between RDBMS and NoSQL systems.
author: Gemini
tags:
  - databases
  - system-design
  - rdbms
  - nosql
---

## 1. What is the fundamental difference in data structure between RDBMS and NoSQL?
RDBMS stores data in structured tables with predefined schemas (rows/columns); NoSQL uses flexible data models like documents, key-values, wide-columns, or graphs.

## 2. When does RDBMS provide a superior advantage?
When complex relationships, transactional integrity (ACID), and strict data schema enforcement are required.

## 3. What is "Schema Flexibility" and how does it benefit NoSQL?
It allows developers to change the data structure on the fly without downtime, which is vital for agile development and evolving data requirements.

## 4. Compare ACID (RDBMS) vs. BASE (NoSQL) consistency models.
ACID prioritizes immediate consistency and reliability; BASE prioritizes availability and performance, accepting that data will become consistent eventually.

## 5. How do horizontal scaling strategies differ between RDBMS and NoSQL?
RDBMS typically scales vertically; horizontal scaling (sharding) is complex. NoSQL is designed for horizontal scaling from the ground up, making it easier to distribute across commodity hardware.

## 6. What is a "Join" and why is it expensive in distributed NoSQL?
A Join combines rows from two tables. In NoSQL, data is often denormalized to avoid joins, as performing joins across distributed nodes is network-intensive and slow.

## 7. When should you choose a Document store (e.g., MongoDB) over a Key-Value store (e.g., Redis)?
Choose Document stores for complex, nested data that requires indexing and querying; choose Key-Value stores for ultra-fast, simple retrieval by primary key.

## 8. What is the "Impedance Mismatch" problem in RDBMS?
It refers to the difficulty of mapping object-oriented application code to relational table structures, often solved by ORMs (which can introduce performance overhead).

## 9. How do you handle complex relationships in a non-relational database?
You either denormalize data (nesting it), use application-level joins, or utilize a Graph Database (e.g., Neo4j) specifically designed for relationships.

## 10. Why is RDBMS considered "Strict" regarding schema?
It enforces data types, constraints, and relationships at the database level, ensuring data integrity but making schema migrations difficult at scale.

## 11. What is "Polyglot Persistence"?
The practice of using multiple database technologies in a single system to meet different needs (e.g., RDBMS for transactional data, Redis for caching, Cassandra for logs).

## 12. How does RDBMS handle concurrency compared to NoSQL?
RDBMS typically uses locking mechanisms (pessimistic/optimistic) to ensure consistency; NoSQL often uses versioning or Last-Write-Wins policies to allow higher throughput.

## 13. Which type of database is better for unstructured data?
NoSQL, as it can store and index binary, semi-structured, or completely schema-less data (like JSON or Blobs) more efficiently than RDBMS.

## 14. What are the trade-offs of denormalization in NoSQL?
Pros: Faster read performance and reduced join complexity. Cons: Potential data inconsistency and increased storage usage due to data duplication.

## 15. Can NoSQL databases support ACID transactions?
Many modern NoSQL databases (like MongoDB or FoundationDB) now offer multi-document ACID transactions, though they may have performance impacts compared to RDBMS.

## 16. What is a "Wide-Column" store and what is its primary use case?
It stores data in columns rather than rows (e.g., Cassandra). It is ideal for massive datasets where you need high-speed writes and analytical queries over specific columns.

## 17. Why is RDBMS often the "default" choice for financial applications?
Due to its proven, rigid adherence to ACID properties, which is non-negotiable for ensuring that money is never lost or incorrectly recorded during concurrent updates.

## 18. How do indexing strategies differ between the two?
RDBMS uses B-Tree indexes for efficient searching/sorting in tables; NoSQL often uses specific indexes optimized for its data type (e.g., inverted indexes for search, geospatial indexes for maps).

## 19. What is the cost of schema migration in RDBMS?
It often requires `ALTER TABLE` operations, which can lock massive tables for extended periods and cause application downtime if not handled carefully.

## 20. How do you decide between RDBMS and NoSQL for a new project?
Evaluate the requirements: Do you need complex joins, strict ACID, and stable data? Use RDBMS. Do you need high scale, schema flexibility, and rapid read/write throughput? Use NoSQL.
