---
tags:
  - moc
  - distributed
type: moc
status: growing
---

# Distributed Systems MOC

Up: [[Home]]

## Core concepts

- [[Sharding]] — partitioning data across nodes `#seed`
- [[Distributed ID Generation]] — unique IDs without a coordinator `#seed`

## Systems

- [[Kafka]] — distributed log / messaging `#seed`
- [[Cassandra]] — wide-column, leaderless replication `#seed`
- [[DynamoDB]] — managed key-value `#seed`

## Reading

- [[Paper Reading List]] — the white papers behind the systems above

## Case studies

- [[Instagram - Scaling Postgres to 2 Billion Users]] — the single best worked example in this vault. It touches [[Sharding]], [[Distributed ID Generation]], connection pooling, and replication all at once.

## The recurring tension

Every note in this map is some answer to: **one machine is not enough.**

| Problem | Answer | Note |
| --- | --- | --- |
| Too much data for one node | partition it | [[Sharding]] |
| No global counter across nodes | encode time + node into the ID | [[Distributed ID Generation]] |
| Node dies | replicate | [[Cassandra]], [[PostgreSQL]] streaming replication |
| Services must not block each other | async log | [[Kafka]] |
| Session state pins a user to one server | make it stateless | [[Authentication]] |

## Related maps

- [[Databases MOC]] — most of these *are* databases
- [[Infrastructure MOC]] — what they run on
