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

# Distributed ID Generation

Up: [[Distributed Systems MOC]]
Worked example: [[Instagram - Scaling Postgres to 2 Billion Users]]

> [!todo] Seed note — the option tree below comes from the Instagram case study. It's already most of the answer.

**The problem:** once [[Sharding]] splits your writes across N primaries, `SERIAL` / `AUTO_INCREMENT` collides. You need IDs that are unique with no coordination.

## The option tree

| Approach | Unique | Sortable | Cost |
| --- | --- | --- | --- |
| `SERIAL` per node | ✗ collides | ✓ | — |
| UUIDv4 | ✓ | ✗ random | bad index locality, 128 bits |
| Flickr ticket server | ✓ | ✓ | single point of failure |
| Twitter Snowflake service | ✓ | ✓ | extra service, more failure points |
| **Snowflake inside the DB** | ✓ | ✓ | a SQL function |

Instagram picked the last: a `next_id()` function in [[PostgreSQL]], no external service, no coordination.

## The 64-bit layout

```
| timestamp (41 bits) | shard (12 bits) | sequence (10 bits) |
```

- **Timestamp in the high bits** → IDs sort by creation time. `ORDER BY id` gives newest-first with no extra index.
- **Shard bits** → uniqueness across nodes without talking to them
- **Sequence** → 1024 IDs per millisecond per shard

Three inputs in, one 64-bit integer out. Purely local.

## To cover

- [ ] 41-bit timestamp lifetime — ~69 years from a chosen epoch. Which epoch?
- [ ] Sequence overflow within a millisecond — block, or borrow from the next ms?
- [ ] Clock skew and NTP going backwards — the real failure mode
- [ ] ULID and UUIDv7 — modern time-sortable alternatives
- [ ] When random UUIDs are still the right call (client-generated, offline-first)

## Connections

- [[Sharding]] — the reason this problem exists at all
- [[PostgreSQL]] — where Instagram's `next_id()` lives
- [[Instagram - Scaling Postgres to 2 Billion Users]] — full narrative
