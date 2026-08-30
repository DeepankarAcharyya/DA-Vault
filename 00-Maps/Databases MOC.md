---
tags:
  - moc
  - db
type: moc
status: growing
---

# Databases MOC

Up: [[Home]]

## Relational

- [[PostgreSQL]] — `#seed`

## NoSQL

- [[MongoDB]] — document store, shell operations `#growing`
- [[Cassandra]] — wide-column `#seed`
- [[DynamoDB]] — managed key-value `#seed`

## Cross-cutting concepts

- [[Sharding]] — how a single logical DB spans many machines
- [[Distributed ID Generation]] — why `SERIAL` breaks once you shard

## Seen in practice

- [[Instagram - Scaling Postgres to 2 Billion Users]] — the reason to read [[Sharding]] before reaching for NoSQL

## Related maps

- [[Distributed Systems MOC]] — replication, consistency, the papers behind these engines
- [[Backend MOC]] — how the app layer talks to these

## Open questions

- [ ] Postgres vs Mongo — when does the document model actually win?
- [ ] Indexing: B-tree vs LSM-tree, and which engine uses which
- [ ] Transaction isolation levels across all four engines above
