---
aliases:
  - Low Level for Container & Infra Management
tags:
  - infra
  - concept
  - seed
type: concept
status: seed
up:
  - "[[Infrastructure MOC]]"
---

# Container Internals

Up: [[Infrastructure MOC]] · Source: [[Containers From Scratch - Liz Rice]]

Learning track: low-level container and infrastructure management, in Go.

- Roadmap : https://docs.google.com/document/d/1w7xxd5bMoiaIpY4STLDorQrvf1wzobxn3UERbAwDU5A/edit?usp=sharing

---

## The one-sentence version

A container is not a thing. It's a normal Linux process with three restrictions applied: **namespaces** (what it can see), **cgroups** (what it can use), **chroot/pivot_root** (what filesystem it thinks is root).

Worked through concretely in [[Containers From Scratch - Liz Rice]].

## To cover

- [ ] Namespaces one by one — PID, NET, MNT, UTS, IPC, USER
- [ ] cgroups v2 — CPU, memory, IO limits
- [ ] `pivot_root` vs `chroot`, and why chroot alone isn't a boundary
- [ ] Layered filesystems — overlayfs, why image layers are cheap
- [ ] `clone()`, `unshare()`, `setns()` from Go
- [ ] OCI runtime spec; where runc sits
- [ ] Build a minimal container runtime end to end

## Connections

- [[Containers From Scratch - Liz Rice]] — the source that seeds this
- [[Concurrency Patterns]] — same Go track; the runtime work is concurrency-heavy
- [[Terraform]] / [[IaC Fundamentals]] — the layer above: provisioning the machines that run these
