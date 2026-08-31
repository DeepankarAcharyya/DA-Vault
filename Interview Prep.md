---
aliases:
  - Topics to prepare for the interview
tags:
  - moc
  - growing
type: moc
status: growing
up:
  - "[[Home]]"
---

# Interview Prep

Up: [[Home]]

Original list: Kafka, MongoDB, Authentication.

## Priority queue

| Topic | Note | Status |
| --- | --- | --- |
| Kafka | [[Kafka]] | `#seed` — nothing written |
| MongoDB | [[MongoDB]] | `#growing` — shell ops only, no aggregation/replication |
| Authentication | [[Authentication]] | `#solid` — ready |

## Recommended additions

Your strongest existing material clusters around data at scale, so these are cheap wins from what's already here:

- [[Instagram - Scaling Postgres to 2 Billion Users]] — a full system-design answer you already know. Practice telling it in 5 minutes.
- [[Sharding]] — the concept behind that story. Asked constantly.
- [[Distributed ID Generation]] — a classic standalone question, and you already have the full option tree.
- [[Design Patterns]] — behavioral patterns now covered; drill the wrapper four.
- [[SOLID Principles]] — named-and-explained is a common warm-up question.
- [[PostgreSQL]] — currently empty, but it's the substrate of your best case study.

## Drill list

- [ ] Explain [[Sharding]] logical-vs-physical without notes
- [ ] Draw the Snowflake 64-bit ID layout from memory — see [[Distributed ID Generation]]
- [ ] Session vs JWT: state, scaling, revocation — [[Authentication]]
- [ ] OAuth2 vs OIDC in one sentence each — [[Authentication]]
- [ ] Kafka: partitions, consumer groups, offsets — [[Kafka]]
- [ ] When would you *actually* pick [[MongoDB]] over [[PostgreSQL]]?
- [ ] Adapter vs Facade vs Proxy vs Decorator — [[Design Patterns]]
- [ ] Name all five of [[SOLID Principles]] and a violation of each
- [ ] What is a container, in syscall terms — [[Container Internals]]

## Maps

[[Databases MOC]] · [[Backend MOC]] · [[Distributed Systems MOC]] · [[Patterns MOC]] · [[Infrastructure MOC]]
