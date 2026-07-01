# SMA UII Yogyakarta — Engineering Playbook

> Operating system for the PT Koneksi Jaringan Indonesia engineering team in building the SMA UII Yogyakarta application ecosystem.

**Version:** 1.0.0  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev

---

## 🎯 Vision

Building **SMART Absen SMA UII** as the first product, while forming a **professional engineering team** capable of delivering features with measurable quality within 2 months:
- **Month 1:** MVP Development
- **Month 2:** Production Audit, Testing, Refining

---

## 👥 Engineering Team

| GitHub Username | Name | Role | Focus |
|---|---|---|---|
| [@Sandikodev](https://github.com/Sandikodev) | Sandiko | Project Manager, Architect, Tech Lead | Architecture, Code Review, Mentoring |
| [@Rosyiii](https://github.com/Rosyiii) | Ahmad Hanif Hasan Rosyidi | Product Analyst | Requirement, User Story, UAT |
| [@Hans02-Neo](https://github.com/Hans02-Neo) | Fathan Mubina | Junior Developer | Frontend (Inertia+React, TypeScript, Tailwind) |
| [@Odauna](https://github.com/Odauna) | Ihsan | Junior Developer | Backend (Laravel API, Database, PostgreSQL) |
| | Azis | Learning Mentor | Discussion partner, debugging buddy, concept explainer, code review prep, learning tracker — helps Fathan & Ihsan |

**Stakeholder:**
- **Pak Mahfud** — IT Manager SMA UII Yogyakarta (Client Representative)

---

## 📚 Playbook Structure

### [01-getting-started](docs/01-getting-started) — Onboarding & Setup

| Document | Description | For |
|---|---|---|
| [`onboarding.md`](docs/01-getting-started/onboarding.md) | First day checklist | New members |
| [`environment-setup.md`](docs/01-getting-started/environment-setup.md) | Setup local development | Developers |
| [`team-roles.md`](docs/01-getting-started/team-roles.md) | Role details & responsibilities | All members |

### [02-workflow](docs/02-workflow) — Git, Trello, Communication

| Document | Description | For |
|---|---|---|
| [`git-github-workflow.md`](docs/02-workflow/git-github-workflow.md) | Branching, commit, PR workflow | Developers |
| [`trello-workflow.md`](docs/02-workflow/trello-workflow.md) | Product management with Trello | Ahmad Hanif |
| [`communication.md`](docs/02-workflow/communication.md) | WhatsApp, meeting, escalation | All members |
| [`github-org-setup.md`](docs/02-workflow/github-org-setup.md) | GitHub Organization setup | Sandikodev |

### [03-sop](docs/03-sop) — Standard Operating Procedures

| Document | Description | For |
|---|---|---|
| [`code-review.md`](docs/03-sop/code-review.md) | Checklist & best practice review | Sandikodev |
| [`deployment.md`](docs/03-sop/deployment.md) | Staging & production deployment | Sandikodev |
| [`testing.md`](docs/03-sop/testing.md) | Unit test, integration, UAT | Developers |

### [04-templates](docs/04-templates) — Ready-to-use Templates

| Document | Description | For |
|---|---|---|
| [`user-story.md`](docs/04-templates/user-story.md) | User story template | Ahmad Hanif |
| [`github-issue.md`](docs/04-templates/github-issue.md) | GitHub Issue template | All members |
| [`pull-request.md`](docs/04-templates/pull-request.md) | Pull Request template | Developers |
| [`sprint-planning.md`](docs/04-templates/sprint-planning.md) | Sprint planning template | Sandikodev |

### [05-adr](docs/05-adr) — Architecture Decision Record

| Document | Description |
|---|---|
| [`001-monorepo.md`](docs/05-adr/001-monorepo.md) | Decision: Monorepo with submodule |
| [`002-livewire-first.md`](docs/05-adr/002-livewire-first.md) | ⚠️ **Superseded** — see ADR-002-v2 |
| [`002-v2-inertia-react.md`](docs/05-adr/002-v2-inertia-react.md) | Decision: InertiaJS + React from MVP |
| [`003-database-mysql.md`](docs/05-adr/003-database-mysql.md) | ⚠️ **Superseded** — see ADR-003-v2 |
| [`003-v2-database-postgresql.md`](docs/05-adr/003-v2-database-postgresql.md) | Decision: PostgreSQL via NeonDB for production |
| [`004-neondb-sanctum.md`](docs/05-adr/004-neondb-sanctum.md) | Decision: NeonDB + Laravel Sanctum |
| [`005-porting-strategy.md`](docs/05-adr/005-porting-strategy.md) | Decision: Porting strategy Monolith → API + Next.js |

### [06-learning-path](docs/06-learning-path) — Junior Developer Roadmap

| Document | Description | For |
|---|---|---|
| [`junior-dev-roadmap.md`](docs/06-learning-path/junior-dev-roadmap.md) | 8-week learning path | Fathan, Ihsan |

### [07-project](docs/07-project) — SMART Absen Project Plans

| Document | Description |
|---|---|
| [`smart-absen-overview.md`](docs/07-project/smart-absen-overview.md) | Complete project overview |
| [`sprint-1-plan.md`](docs/07-project/sprint-1-plan.md) | Sprint 1: Authentication & SSO |
| [`sprint-2-plan.md`](docs/07-project/sprint-2-plan.md) | Sprint 2: Attendance Module |
| [`mvp-scope.md`](docs/07-project/mvp-scope.md) | MVP definition & scope |

### [ROLES](ROLES) — Dynamic Role Definitions

| Document | Description | For |
|---|---|---|
| [`_TEMPLATE.md`](ROLES/_TEMPLATE.md) | Template for creating new roles | Maintainer |
| [`product-analyst.md`](ROLES/product-analyst.md) | Product Analyst — AI instructions, responsibilities | Ahmad Hanif |
| [`junior-backend.md`](ROLES/junior-backend.md) | Junior Backend — AI instructions, learning path | Ihsan |
| [`junior-frontend.md`](ROLES/junior-frontend.md) | Junior Frontend — AI instructions, learning path | Fathan |
| [`learning-mentor.md`](ROLES/learning-mentor.md) | Learning Mentor — AI instructions, mentoring scope | Azis |
| [`senior-developer.md`](ROLES/senior-developer.md) | Senior Developer / Tech Lead — AI instructions | Sandikodev |
| [`project-manager.md`](ROLES/project-manager.md) | Project Manager — AI instructions | Sandikodev |
| [`stakeholder.md`](ROLES/stakeholder.md) | Stakeholder — AI instructions | Pak Mahfud |

### [WORKFLOWS](WORKFLOWS) — AI Agent Workflows

| Document | Description | For |
|---|---|---|
| [`ai-agent-workflow.md`](WORKFLOWS/ai-agent-workflow.md) | TACO Protocol: Trello → AI → Commit → Output | All developers |

### [ACCESS](ACCESS) — Access Control Policies

| Document | Description | For |
|---|---|---|
| [`matrix-per-role.md`](ACCESS/matrix-per-role.md) | GitHub, Trello, environment access matrix per role | All members |
| [`outsourced-policy.md`](ACCESS/outsourced-policy.md) | Security policy for outsourced workers/partners | Sandikodev |

---

## 🚀 Quick Start

### For Product Analyst (Ahmad Hanif)
1. Read [`ROLES/product-analyst.md`](ROLES/product-analyst.md) — role & AI instructions
2. Read [`docs/04-templates/user-story.md`](docs/04-templates/user-story.md)
3. Setup [OpenKB](https://github.com/SMA-UII-Yogyakarta/aksesekolah/blob/main/.openkb/TEMPLATE.md)
4. Copy role file: `copy ROLES/product-analyst.md ~/.openkb/ROLES/`
5. Create user story in Trello, link to GitHub Issue

### For Developer (Fathan, Ihsan)
1. Read [`ROLES/<role>.md`](ROLES/_TEMPLATE.md) — role & AI instructions
2. Read [`docs/01-getting-started/onboarding.md`](docs/01-getting-started/onboarding.md)
3. Setup environment: [`docs/01-getting-started/environment-setup.md`](docs/01-getting-started/environment-setup.md)
4. Setup OpenKB: `copy ROLES/<role>.md ~/.openkb/ROLES/`
5. Understand AI Agent workflow: [`WORKFLOWS/ai-agent-workflow.md`](WORKFLOWS/ai-agent-workflow.md)
6. Pick up Issue from GitHub Project, work on it with AI Agent

### For Reviewer / Tech Lead (Sandikodev)
1. Code Review Checklist: [`docs/03-sop/code-review.md`](docs/03-sop/code-review.md)
2. Sprint Planning Template: [`docs/04-templates/sprint-planning.md`](docs/04-templates/sprint-planning.md)
3. Outsourced Policy: [`ACCESS/outsourced-policy.md`](ACCESS/outsourced-policy.md)

### For Stakeholder (Pak Mahfud)
1. Read [`ROLES/stakeholder.md`](ROLES/stakeholder.md) — role & expectations
2. View progress on Trello Product Roadmap

---

## 🛠️ Tech Stack

### Current Architecture (MVP — Phase 1)
```
Backend  : Laravel 13 (PHP 8.4) + Service Layer
Frontend : InertiaJS 3 + React 19 + TypeScript 5.7 + Tailwind CSS 4 + Vite 8
Database : PostgreSQL 16 via NeonDB
Auth     : Laravel Sanctum + Spatie Laravel Permission (RBAC)
Packages : Bun (frontend), Composer (backend)
Queue    : Database driver (Redis later)
Storage  : S3-compatible (Wasabi / MinIO)
Deploy   : Laragon (dev) → Nginx (production)
```

### Target Architecture (Phase 2 — Dedicated Backend + Multi Client)
```
Backend  : Laravel 13 API-Only (Core) — Service Layer, Queue, SSO Provider
Frontend : Next.js (Web App) — SSR/SSG, PWA
Mobile   : React Native / Flutter (under consideration by team & stakeholder)
Auth     : SSO (Sanctum Identity Provider) — reusable by all clients
Third-Party: SIAD, external systems via API Gateway
```

### Porting Strategy: Phase 1 → Phase 2
```
Phase 1 (Monolith + Inertia)    →    Phase 2 (API-Only + Multi Client)
├── Thin Controller             →    Thin Controller (same, reuse)
├── Service Layer in App\Services → Service Layer (same, reuse)
├── Inertia renders React       →    Next.js / RN / Flutter consume API
├── API routes (/api/*) active  →    API routes (same, no change)
├── Sanctum session auth        →    Sanctum token auth (switch mode)
└── Zero rewrite — just add new frontend
```

---

## 📊 Project Management Tools

| Tool | Purpose | Link |
|---|---|---|
| **Trello** | Product Roadmap, Sprint Board | [SMART ABSEN SMAUII](https://trello.com/b/BHXA6ZcR/smart-absen-smauii) |
| **GitHub Projects** | Engineering Task Tracking | [Project](https://github.com/orgs/SMA-UII-Yogyakarta/projects/1) |
| **GitHub Issues** | Technical Task | [Issues](https://github.com/SMA-UII-Yogyakarta/core/issues) |
| **WhatsApp Group** | Quick Communication | Private Group |

---

## ⏱️ Timeline & Milestones

```
Week 1-2  → Sprint 1: Synchronization & Setup — env, package, DB, Sanctum, docs sync
Week 3-4  → Sprint 2: Authentication & SSO — registration, login, role, permission
Week 5-6  → Sprint 3: Attendance Module (Core) — check-in, geolocation, selfie
Week 7-8  → Sprint 4: Reports, Admin Panel, UAT, Deployment
```

**MVP Target:** End of Week 6  
**Production Ready:** End of Week 8  
*Note: This timeline reflects the stack reset (from Livewire/MySQL to Inertia+React/PostgreSQL) and learning path adjustments for Fathan, Ihsan, and Azis.*

---

## 📖 Repositories

| Repo | Description | Link |
|---|---|---|
| **aksesekolah** | Monorepo Entrypoint | [GitHub](https://github.com/SMA-UII-Yogyakarta/aksesekolah) |
| **core** | Backend Laravel | [GitHub](https://github.com/SMA-UII-Yogyakarta/core) |
| **webapp** | Frontend (Next.js) | [GitHub](https://github.com/SMA-UII-Yogyakarta/webapp) |
| **flutter** | Mobile App | [GitHub](https://github.com/SMA-UII-Yogyakarta/flutter) |
| **playbook** | Engineering Handbook | [GitHub](https://github.com/SMA-UII-Yogyakarta/playbook) |

---

## 🎓 Learning Culture

> "We don't just build software. We build engineers."

Every Pull Request is a learning opportunity.  
Every Code Review is a teaching moment.  
Every Sprint Retrospective is an improvement.

### Expected Outcome (8 Weeks)
- ✅ Fathan can independently develop features (Livewire/React)
- ✅ Ihsan can independently develop Laravel API features
- ✅ Ahmad can write implementable requirements
- ✅ Sandikodev is not a bottleneck

---

## 📞 Contact

**PT Koneksi Jaringan Indonesia**  
📧 Email: [hello@koneksi.id](mailto:hello@koneksi.id)  
📱 WhatsApp: [Contact Link](https://wa.me/...)

**SMA UII Yogyakarta**  
📍 Address: Jl. Taman Siswa No.158, Wirogunan, Mergangsan, Kota Yogyakarta 55151  
📞 Phone: (0274) 489693

---

## 📄 License

Internal use only — PT Koneksi Jaringan Indonesia & SMA UII Yogyakarta

---

**Last Commit:** [See History](https://github.com/SMA-UII-Yogyakarta/playbook/commits/main)
