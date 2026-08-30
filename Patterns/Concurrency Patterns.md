---
tags:
  - patterns
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Patterns MOC]]"
---

# Concurrency Patterns

Up: [[Patterns MOC]] · Prereq: [[Design Patterns]]

> [!todo] Seed note — empty. Go-flavoured, part of the same track as [[Container Internals]].

## Primitives first

- [ ] Goroutines vs OS threads
- [ ] Channels — buffered vs unbuffered
- [ ] `select`
- [ ] `sync.Mutex`, `WaitGroup`, `Once`
- [ ] `context` — cancellation and deadlines propagating down a call tree
- [ ] Concurrency vs parallelism

## Patterns

- [ ] Worker pool — bounded goroutines over a job channel
- [ ] Fan-out / fan-in
- [ ] Pipeline — stages joined by channels
- [ ] Generator
- [ ] Semaphore / rate limiting
- [ ] Graceful shutdown
- [ ] Errgroup — first error cancels the rest

## Connections

- [[Container Internals]] — same Go learning track; runtime work is concurrency-heavy
- [[Design Patterns]] — a worker pool is Producer/Consumer; a pipeline is Chain of Responsibility over channels
- [[Kafka]] — consumer groups are a distributed worker pool. Same shape, different machine boundary.
- [[Authentication]] — stateless tokens are what let you scale to N concurrent workers with no shared session store

## Open questions

- [ ] Detecting and fixing goroutine leaks
- [ ] When a mutex beats a channel
- [ ] `sync.Map` — what it's actually for
