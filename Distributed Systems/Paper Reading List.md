---
aliases:
  - White Paper Index
tags:
  - distributed
  - moc
  - seed
type: moc
status: seed
up:
  - "[[Distributed Systems MOC]]"
---

# Paper Reading List

Up: [[Distributed Systems MOC]]

- Cassandra
- Kafka
- Dynamo DB
---

## Queue

| Paper | Note | Read | Core idea to extract |
| --- | --- | --- | --- |
| Dynamo (Amazon, 2007) | [[DynamoDB]] | [ ] | consistent hashing, quorums, eventual consistency |
| Cassandra (Facebook, 2009) | [[Cassandra]] | [ ] | Dynamo's ring + BigTable's data model |
| Kafka (LinkedIn, 2011) | [[Kafka]] | [ ] | the log as a primitive; partitions and offsets |

Read in that order — Cassandra's paper assumes Dynamo.

## Why these three together

Each answers "one machine is not enough" differently — see the table in [[Distributed Systems MOC]]. Dynamo and Cassandra partition *state*; Kafka partitions a *stream*. All three lean on [[Sharding]].

## Worth adding later

- [ ] Google Spanner — distributed transactions
- [ ] Raft — consensus, readable
- [ ] Bigtable — Cassandra's other parent

## Related

[[Instagram - Scaling Postgres to 2 Billion Users]] — the counterargument to all of the above: they *didn't* switch to NoSQL.
