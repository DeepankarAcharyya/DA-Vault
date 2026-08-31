---
aliases:
  - SOLID
tags:
  - patterns
  - concept
  - growing
type: concept
status: growing
up:
  - "[[Patterns MOC]]"
---

# SOLID Principles

Up: [[Patterns MOC]] · Prereq: [[OOP Concepts]] · Applied in: [[Design Patterns]]

Five design rules for classes and interfaces. Each one is the reason some pattern in [[Design Patterns]] exists.

## 1. Single Responsibility

- Classes and methods should have a single responsibility.
- High cohesion — be responsible for only a single thing.

## 2. Open/Closed

- Open for extension.
- Closed for modification.
- The point of **Strategy** and **Factory** in [[Design Patterns]].

## 3. Liskov Substitution

- If you have objects in the program, you should be able to replace those objects with their subtypes / subclasses without updating / changing the behavior of the program.
- Why a **Proxy** *must* expose the same interface as the object it wraps.

## 4. Interface Segregation

- Instead of one generic interface, split the interface so each one carries meaningful behaviors.

## 5. Dependency Inversion

- The class should depend on abstractions and not on concrete subclasses.
- Why **Adapter** works — your domain code depends on your interface, not the vendor's.

## Connections

- [[OOP Concepts]] — the pillars these rules are built on
- [[Design Patterns]] — where each principle shows up as a concrete pattern

## Open questions

- [ ] How much of this survives in Go — no inheritance, structural interfaces
- [ ] When applying SRP/ISP tips over into over-engineering
