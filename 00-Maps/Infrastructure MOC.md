---
tags:
  - moc
  - infra
type: moc
status: growing
---

# Infrastructure MOC

Up: [[Home]]

## Infrastructure as Code

- [[IaC Fundamentals]] — what "infrastructure" means, why codify it
- [[Terraform]] — the tool

## Containers

- [[Container Internals]] — how containers actually work; learning roadmap
- [[Containers From Scratch - Liz Rice]] — source note: namespaces, cgroups, chroot

## The chain

Linux primitives → containers → orchestration → declared with IaC:

`namespaces + cgroups + chroot` ([[Containers From Scratch - Liz Rice]])
→ container runtime ([[Container Internals]])
→ provisioned by [[Terraform]] ([[IaC Fundamentals]])

## Related maps

- [[Distributed Systems MOC]] — what you run *on* this infrastructure
- [[Databases MOC]] — stateful workloads are the hard part of infra

## Open questions

- [ ] Terraform state — remote backends, locking, drift
- [ ] Kubernetes: where it sits above the container runtime
- [ ] cgroups v1 vs v2
