---
tags:
  - db
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Databases MOC]]"
---

# PostgreSQL

Up: [[Databases MOC]] · Compare: [[MongoDB]]

> [!todo] Seed note — empty. High value: it's the substrate of [[Instagram - Scaling Postgres to 2 Billion Users]], your strongest case study.

## To cover

- [ ] MVCC — how readers don't block writers
- [ ] Vacuum and bloat (the consequence of MVCC)
- [ ] Indexes: B-tree, GIN, partial, covering
- [ ] Query planner — reading `EXPLAIN ANALYZE`
- [ ] Transaction isolation levels
- [ ] Streaming replication — used for shard migration in the Instagram case
- [ ] Connection model: process-per-connection, ~1.3 MB each → why pgbouncer exists
- [ ] Partitioning (native) vs [[Sharding]] (application-level)
- [ ] JSONB — where it overlaps [[MongoDB]]

## Already known, from elsewhere in this vault

From [[Instagram - Scaling Postgres to 2 Billion Users]]:

- 1.3 MB memory per connection → **pgbouncer** is mandatory at scale
- **Streaming replication** makes moving a logical shard between physical nodes cheap
- A plain SQL function (`next_id()`) can generate Snowflake IDs in-database — see [[Distributed ID Generation]]

## Connections

- [[Sharding]] — Postgres does not shard for you
- [[Distributed ID Generation]] — `SERIAL` collides the moment there's more than one primary
