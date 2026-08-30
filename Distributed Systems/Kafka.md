---
tags:
  - distributed
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Distributed Systems MOC]]"
---

# Kafka

Up: [[Distributed Systems MOC]] · Paper: [[Paper Reading List]]

> [!todo] Seed note — empty, and it's **#1 on [[Interview Prep]]**. Highest-priority gap in the vault.

## The core idea

Not a queue — an **append-only, partitioned, replayable log**. Consumers track their own offset, so reading doesn't destroy the message.

## To cover

- [ ] Topics, partitions, offsets
- [ ] Partition key → ordering guarantee is *per partition*, not per topic
- [ ] Consumer groups and rebalancing
- [ ] Replication: leader, followers, ISR
- [ ] Delivery semantics — at-most-once / at-least-once / exactly-once
- [ ] Retention: time-based and compacted topics
- [ ] Producer acks (`0`, `1`, `all`) and the durability tradeoff
- [ ] Consumer lag — the metric that actually matters
- [ ] ZooKeeper → KRaft
- [ ] Kafka vs RabbitMQ vs SQS

## Connections

- [[Sharding]] — partitions *are* shards, applied to a stream instead of a table
- [[Concurrency Patterns]] — a consumer group is a distributed worker pool. Same shape, machine boundary instead of goroutine boundary.
- [[Design Patterns]] — Observer / pub-sub, scaled out and made durable
- [[Distributed Systems MOC]] — its slot in the table: services must not block each other
- [[Paper Reading List]] — LinkedIn, 2011
