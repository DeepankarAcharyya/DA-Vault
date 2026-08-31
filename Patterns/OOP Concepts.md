---
aliases:
  - OOPs concept
tags:
  - patterns
  - concept
  - growing
type: concept
status: growing
up:
  - "[[Patterns MOC]]"
---

# OOP Concepts

Up: [[Patterns MOC]] · Next: [[SOLID Principles]] → [[Design Patterns]]

The prerequisite for [[Design Patterns]] — most of those patterns are applied polymorphism and composition.

## Four pillars

- **Encapsulation** — related data and methods that operate on them should be packaged together → objects. State private, behaviour public.
- **Abstraction** — hide the implementation complexities behind a simpler interface. Helps with reducing the impact of change.
- **Inheritance** — eliminate redundant code. Also the pillar that gets overused; see composition below.
- **Polymorphism** — "many forms". The same method defined for each of the classes; the one triggered depends on the type of class. Technique for eliminating long if-else structures, and the mechanism every pattern in [[Design Patterns]] relies on.

## Interfaces vs abstract classes

| | Interface | Abstract class |
| --- | --- | --- |
| What it is | a collection of abstract methods that define a contract for a class to implement | a class that cannot be instantiated, designed to be subclassed by other classes |
| State | cannot hold any state | can have state |
| Methods | abstract methods and default methods only | abstract *and* non-abstract methods |

## Beyond the pillars

- [ ] Composition over inheritance — Decorator and Adapter are this argument made concrete
- [x] SOLID — split out into [[SOLID Principles]]
- [ ] Go's take: no inheritance, structural interfaces, embedding — relevant to [[Container Internals]]

## Connections

- [[SOLID Principles]] — the design rules built on these pillars
- [[Design Patterns]] — every entry there assumes this note
- [[Concurrency Patterns]] — the Go track, where OOP intuitions partly stop applying
