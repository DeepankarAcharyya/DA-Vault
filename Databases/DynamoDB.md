---
aliases:
  - Dynamo DB
  - Dynamo
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

# DynamoDB

Up: [[Databases MOC]] · [[Distributed Systems MOC]] · Paper: [[Paper Reading List]]

> [!todo] Seed note — empty. **Read the Dynamo paper (2007) first** — it's the foundation for [[Cassandra]] too.

Two things share this name: the **Dynamo paper** (Amazon, 2007) and **DynamoDB** (the managed service). The paper is the one worth reading.

## From the paper

- [ ] Consistent hashing + virtual nodes
- [ ] Quorums: R + W > N
- [ ] Vector clocks and conflict resolution
- [ ] Eventual consistency — what it actually costs the application
- [ ] Gossip, hinted handoff, Merkle-tree anti-entropy
- [ ] "Always writeable" as a design goal

## From the service

- [ ] Partition key vs sort key
- [ ] Single-table design
- [ ] GSI vs LSI
- [ ] Capacity modes; hot partition throttling
- [ ] Streams

## Connections

- [[Cassandra]] — took the ring and quorums directly from this paper
- [[Sharding]] — consistent hashing is a mapping-layer-free approach
- [[Paper Reading List]] — Amazon, 2007; read before Cassandra
