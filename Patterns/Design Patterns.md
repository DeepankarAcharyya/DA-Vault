---
tags:
  - patterns
  - concept
  - growing
type: concept
status: growing
source: https://www.youtube.com/watch?v=rpt8PpIPhJQ
up:
  - "[[Patterns MOC]]"
---

# Design Patterns

Up: [[Patterns MOC]] · Prereq: [[OOP Concepts]] · [[SOLID Principles]] · Next: [[Concurrency Patterns]]

Source: https://www.youtube.com/watch?v=rpt8PpIPhJQ

Basically proven and reusable approaches to common software design problems.

## Creational — how objects are created

- **Singleton**
	- one shared instance of a class
		- app config
		- logger
	- globally accessible
	- explicit passing the instance
- **Builder**
	- Build the object step by step
		- The constructor is created with the necessary required info
		- Add the other optional data to the object using multiple methods
- **Factory**
	- there is an abstract factory class
	- subclasses implement them
		- Eg : notification
			- can be email, sms

## Structural — how objects are organized and combined

- **Adapter**
	- helps 2 incompatible components work together — when the interfaces doesnt match
	- override the functions
- **Facade**
	- simple interface to a complex system
		- complicated workflow
			- the user / client have to know the underlying complicated steps and the sequence of the steps
	- Facade provides a single interface for the user to use
		- it hides the complexities within it
		- the user doesnt need to know whats happening under the hood
- **Proxy**
	- It places a substitute object infront of the original object to control access to it
	- both real object and the proxy exposes the same interface
		- so the client can use the proxy just like the original object
- **Decorator**
	- add new behavior to an object dynamically without its original class
- **Composite**
	- It lets us treat an individual and group of objects through the same interface
	- Eg : File system

## Behavioral — how objects communicate and divide responsibilities

- **Strategy**
	- multiple ways to do the same thing
	- it allows one object to choose between behaviors
- **Observer**
	- It allows several objects to react when something happens
- **State**
	- Allows the object to change its behavior when its internal state changes
	- The operations allowed for the object depends on the internal state
- **Command**
	- This pattern turns a request / action to separate object
- **Template**
	- common parts of the workflow into a class
	- letting us customize the specific steps
- **Iterator**
	- Let us move through the items without knowing how it is internally stored
	- 2 basic ops
		- hasNext()
		- next()
- **Chain of Responsibility**
	- *not yet written up*

## Adapter vs Facade vs Proxy vs Decorator

All four wrap something. The difference is *intent*:

| Pattern | Interface vs wrapped object | Purpose |
| --- | --- | --- |
| Adapter | **different** | make incompatible things fit |
| Facade | **new, simpler** | hide a multi-step workflow |
| Proxy | **same** | control access to it |
| Decorator | **same** | add behaviour to it |

Proxy and Decorator share an interface with what they wrap — the split is control vs augmentation.

## Where these appear in this vault

- **Proxy** → auth middleware in [[Authentication]]; an API gateway; a caching layer
- **Facade** → any SDK hiding a request/retry/parse sequence
- **Adapter** → wrapping a vendor client so your domain code doesn't depend on it — [[SOLID Principles]] dependency inversion
- **Singleton** → DB connection pool, the thing pgbouncer manages in [[Instagram - Scaling Postgres to 2 Billion Users]]
- **Factory** → the notification example; also driver selection across [[PostgreSQL]] / [[MongoDB]]
- **Observer** → pub/sub, event systems — [[Kafka]]

## Gaps

- [ ] Chain of Responsibility — no notes yet
- [ ] Concrete code for each behavioral pattern; currently one-line definitions only
- [ ] When a pattern is over-engineering
