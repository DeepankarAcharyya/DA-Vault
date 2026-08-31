---
tags:
  - moc
  - patterns
type: moc
status: growing
---

# Patterns MOC

Up: [[Home]]

## Notes

- [[OOP Concepts]] — the foundation the design patterns assume `#growing`
- [[SOLID Principles]] — the five design rules `#growing`
- [[Design Patterns]] — creational, structural, behavioral `#growing`
- [[Concurrency Patterns]] — Go-flavoured `#seed`

## Dependency order

[[OOP Concepts]] → [[SOLID Principles]] → [[Design Patterns]] → [[Concurrency Patterns]]

Design patterns are mostly *applied polymorphism and composition*. Reading them before [[OOP Concepts]] is backwards, and each SOLID principle names the pattern that enforces it.

## Where these show up

- **Singleton** → app config, logger
- **Facade** → an SDK hiding a multi-step workflow; compare with the API-gateway idea in [[Backend MOC]]
- **Proxy** → caching layers, [[Authentication]] middleware, service meshes
- **Adapter** → wrapping a third-party client so your code doesn't depend on its interface
- **Observer** → pub/sub and event streams; see [[Kafka]]

## Related maps

- [[Backend MOC]] — where these patterns get used
- [[Infrastructure MOC]] — [[Container Internals]] is the Go/concurrency track

## Open questions

- [ ] Chain of Responsibility — the one behavioral pattern still unwritten
- [ ] Go concurrency: worker pool, fan-in/fan-out, pipeline, context cancellation
- [ ] When a pattern is over-engineering
