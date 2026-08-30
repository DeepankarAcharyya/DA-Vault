---
aliases:
  - OOPs concept
tags:
  - patterns
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Patterns MOC]]"
---

# OOP Concepts

Up: [[Patterns MOC]] · Next: [[Design Patterns]]

> [!todo] Seed note — empty. This is the prerequisite for [[Design Patterns]]; most of those patterns are applied polymorphism and composition.

## Four pillars

- [ ] **Encapsulation** — state private, behaviour public
- [ ] **Abstraction** — interface without implementation
- [ ] **Inheritance** — and why it's overused
- [ ] **Polymorphism** — the mechanism every pattern in [[Design Patterns]] relies on

## Beyond the pillars

- [ ] Composition over inheritance — Decorator and Adapter are this argument made concrete
- [ ] SOLID
	- [ ] Single responsibility
	- [ ] Open/closed — the point of Strategy and Factory
	- [ ] Liskov substitution — why a Proxy *must* share the interface
	- [ ] Interface segregation
	- [ ] Dependency inversion — why Adapter works
- [ ] Interfaces vs abstract classes
- [ ] Go's take: no inheritance, structural interfaces, embedding — relevant to [[Container Internals]]

## Connections

- [[Design Patterns]] — every entry there assumes this note
- [[Concurrency Patterns]] — the Go track, where OOP intuitions partly stop applying
