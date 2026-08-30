---
tags:
  - infra
  - concept
  - growing
type: concept
status: growing
up:
  - "[[Infrastructure MOC]]"
---

# Terraform

Up: [[Infrastructure MOC]] · Concept: [[IaC Fundamentals]]

- It is a tool that enables us to do IaC ( Infrastructure as Code)

HashiCorp Terraform is an IaC tool that lets you define both cloud and on-prem resources in human-readable configuration files that you can version, reuse and reshare.

---

## Core loop

`write .tf` → `terraform init` → `terraform plan` (show the diff) → `terraform apply`

The **plan** step is the whole value proposition: you see what will change before it changes.

## Connections

- [[IaC Fundamentals]] — the why behind this tool
- [[Container Internals]] — Terraform provisions the hosts; containers package what runs on them

## Open questions

- [ ] State: local vs remote backend, locking, `terraform import`
- [ ] Providers and how the resource graph gets built
- [ ] Modules — structuring dev/staging/prod without copy-paste
- [ ] Terraform vs Pulumi vs CloudFormation
- [ ] Handling stateful resources ([[PostgreSQL]], volumes) — what must never be `-replace`d
