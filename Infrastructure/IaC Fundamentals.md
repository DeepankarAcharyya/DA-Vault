---
aliases:
  - Section 1 - What is IaC
tags:
  - infra
  - concept
  - growing
type: concept
status: growing
up:
  - "[[Infrastructure MOC]]"
---

# IaC Fundamentals

Up: [[Infrastructure MOC]] · Tool: [[Terraform]]

- Infrastructure : everything that supports the application/service to run
- Includes 
	- servers
	- network configurations
	- storage
	- monitoring ...

---

## Why codify it

Clicking through a cloud console produces infrastructure nobody can review, reproduce, or roll back. IaC makes it a file: version it, diff it, review it, re-apply it.

- **Declarative** — describe the desired end state, let the tool compute the diff. [[Terraform]] works this way.
- **Imperative** — describe the steps. Scripts, Ansible playbooks.

## Connections

- [[Terraform]] — the concrete tool for everything above
- [[Container Internals]] — containers make the *workload* reproducible; IaC makes the *platform* reproducible. Different layers, same goal.

## Open questions

- [ ] State files — where they live, why they lock
- [ ] Drift: someone changes it in the console, now what?
- [ ] Modules and reuse across environments
- [ ] Secrets — never in the repo, so where?
