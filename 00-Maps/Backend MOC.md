---
tags:
  - moc
  - backend
type: moc
status: growing
---

# Backend MOC

Up: [[Home]]

## API layer

- [[GraphQL]] — `#seed`

## Identity

- [[Authentication]] — basic → session → JWT → OAuth2 → OIDC → SSO `#solid`

## Related maps

- [[Databases MOC]] — the persistence layer underneath
- [[Patterns MOC]] — how to structure the code
- [[Distributed Systems MOC]] — what changes when the backend is many machines

## Threads worth pulling

- Session auth is **stateful** and doesn't scale horizontally → the reason JWT exists → see [[Authentication]] and [[Sharding]] for the same statelessness argument in the data layer.
- An API gateway is the Proxy pattern from [[Design Patterns]] applied at the network layer.

## Open questions

- [ ] REST vs GraphQL vs gRPC — tradeoffs
- [ ] Rate limiting strategies
- [ ] Idempotency keys for retried writes
