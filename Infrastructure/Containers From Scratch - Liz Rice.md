---
aliases:
  - Containers From Scratch - Liz Rice - GOTO 2018
tags:
  - infra
  - source
  - growing
type: source
status: growing
source: https://www.youtube.com/watch?v=8fi7uSYlOdc
up:
  - "[[Container Internals]]"
---

# Containers From Scratch - Liz Rice (GOTO 2018)

Up: [[Container Internals]] · [[Infrastructure MOC]]

video : https://www.youtube.com/watch?v=8fi7uSYlOdc

Linux Concepts :
- Namespaces
	- limit what the process can see
	- created using syscalls
- Chroot
- Cgroups

- hostname inside the container -- hostname
---

## The three primitives

| Primitive | Restricts | Example |
| --- | --- | --- |
| **Namespaces** | what the process can *see* | own PID 1, own hostname, own network interfaces |
| **cgroups** | what it can *use* | memory ceiling, CPU shares |
| **chroot / pivot_root** | what it thinks `/` *is* | its own root filesystem |

The talk's core demo: `hostname` returns something different inside the container because of the **UTS namespace** — no virtualization involved, just a syscall.

## Open questions

- [ ] Which syscall creates each namespace — `clone` flags vs `unshare`
- [ ] Why `chroot` alone is escapable, and what `pivot_root` fixes
- [ ] cgroups v1 vs v2 interface differences

Continue in [[Container Internals]].
