---
tags:
  - db
  - distributed
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Databases MOC]]"
---

# Cassandra

Up: [[Databases MOC]] · [[Distributed Systems MOC]] · Paper: [[Paper Reading List]]

> [!todo] Seed note — empty. Read the [[DynamoDB]] (Dynamo) paper first; the Cassandra paper assumes it.

Wide-column store. Dynamo's distribution model + BigTable's data model.

## To cover

- [ ] Ring topology, consistent hashing, virtual nodes
- [ ] **Leaderless** replication — every node accepts writes
- [ ] Tunable consistency: R + W > N
- [ ] Partition key vs clustering key — query patterns dictate the schema
- [ ] LSM-tree storage: memtable → SSTable → compaction
- [ ] Hinted handoff, read repair, anti-entropy
- [ ] Why there are no joins, and why you denormalize instead
- [ ] Tombstones and the delete problem

## Connections

- [[Sharding]] — consistent hashing means no mapping layer, unlike [[Instagram - Scaling Postgres to 2 Billion Users]]
- [[DynamoDB]] — shared ancestry
- [[PostgreSQL]] — the opposite tradeoff: joins and transactions vs write throughput and availability
- [[Paper Reading List]] — Facebook, 2009
