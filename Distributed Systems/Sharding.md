---
tags:
  - distributed
  - db
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Distributed Systems MOC]]"
---

# Sharding

Up: [[Distributed Systems MOC]] · [[Databases MOC]]
Worked example: [[Instagram - Scaling Postgres to 2 Billion Users]]

> [!todo] Seed note — the outline below is extracted from the Instagram case study. Fill in the general theory.

Splitting one logical dataset across many machines because one machine has run out of disk, memory, or IOPS.

## The one idea worth remembering

**Decouple logical shards from physical shards.**

- Logical shard = how data is *partitioned*
- Physical shard = which machine it *lives on*
- A mapping layer connects them

Rebalancing then becomes a mapping update plus a replication catch-up — not a data migration. This is what [[Instagram - Scaling Postgres to 2 Billion Users]] built on top of [[PostgreSQL]]'s streaming replication.

## Shard key choice

The one decision that's expensive to reverse.

- Instagram rejected `user_id` — cross-user queries would span every shard
- Bad key → hot shards, or fan-out reads that touch everything

## To cover

- [ ] Range vs hash vs directory-based partitioning
- [ ] Consistent hashing — how [[DynamoDB]] and [[Cassandra]] avoid a mapping layer
- [ ] Resharding without downtime
- [ ] Cross-shard joins and transactions — the things you give up
- [ ] Hotspots and skew
- [ ] Sharding vs replication vs partitioning — three different words, often confused

## Connections

- [[Distributed ID Generation]] — the direct consequence: `SERIAL` collides across shards
- [[MongoDB]] — ships with sharding; Postgres does not
- [[Cassandra]] / [[DynamoDB]] — consistent hashing instead of an explicit map
- [[Authentication]] — same stateless-vs-stateful argument, applied to sessions instead of rows
