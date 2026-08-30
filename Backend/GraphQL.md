---
aliases:
  - graphQL
tags:
  - backend
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Backend MOC]]"
---

# GraphQL

Up: [[Backend MOC]]

> [!todo] Seed note — empty.

## To cover

- [ ] Schema and type system (SDL)
- [ ] Queries vs Mutations vs Subscriptions
- [ ] Resolvers — one function per field
- [ ] The N+1 problem and DataLoader batching
- [ ] Why it's one endpoint, and what that breaks (HTTP caching, per-route rate limits)
- [ ] Query depth / complexity limits — a client can otherwise ask for anything
- [ ] Versioning: deprecate fields instead of `/v2`

## Connections

- [[Authentication]] — one endpoint means auth moves from route-level to **resolver-level**. Field authorization is the hard part.
- [[Databases MOC]] — N+1 is a database problem wearing an API costume
- [[Design Patterns]] — a resolver layer is a Facade over multiple backing services

## Open questions

- [ ] REST vs GraphQL vs gRPC — when is each actually right?
- [ ] Rate limiting a single endpoint where cost varies per query
