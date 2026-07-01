# Project Context — PT Koneksi Jaringan Indonesia Playbook

## Summary
Playbook is the central documentation hub for SOPs, workflows, templates, ADRs, and role definitions for all PT Koneksi Jaringan Indonesia projects.

## Structure
```
ROLES/         — Dynamic role definitions (template per role)
WORKFLOWS/     — AI Agent workflow (TACO protocol)
ACCESS/        — Access matrix & outsourced policy
docs/
   01-getting-started/  — Onboarding, environment, team roles
   02-workflow/         — Git, Trello, GitHub, communication
   03-sop/              — Code review, deployment, testing
   04-templates/        — Issue, PR, sprint, user story
   05-adr/              — Architecture Decision Records
   06-learning-path/    — Junior dev roadmap
   07-project/          — MVP scope, sprint plans
```

## Current Project
- **SMART Absen SMA UII** (backend: core.git, entrypoint: aksesekolah.git, power-up: kaede-powerup.git)

## Rules
1. Every role definition must go through review before considered final
2. Update `docs/07-project/` whenever a new sprint starts
3. ADR must be written for every significant architecture decision
4. Templates in `docs/04-templates/` must always be up to date
