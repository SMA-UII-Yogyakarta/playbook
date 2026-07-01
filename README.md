# SMA UII Yogyakarta — Engineering Playbook

> Operating system untuk tim engineering PT Koneksi Jaringan Indonesia dalam membangun ekosistem aplikasi SMA UII Yogyakarta.

**Version:** 1.0.0  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev

---

## 🎯 Visi

Membangun **SMART Absen SMA UII** sebagai produk pertama, sekaligus membentuk **tim engineering profesional** yang mampu delivery fitur dengan kualitas terukur dalam waktu 2 bulan:
- **Bulan 1:** MVP Development
- **Bulan 2:** Production Audit, Testing, Refining

---

## 👥 Tim Engineering

| GitHub Username | Nama | Role | Fokus |
|---|---|---|---|
| [@Sandikodev](https://github.com/Sandikodev) | Sandiko | Project Manager, Architect, Tech Lead | Architecture, Code Review, Mentoring |
| [@Rosyiii](https://github.com/Rosyiii) | Ahmad Hanif Hasan Rosyidi | Product Analyst | Requirement, User Story, UAT |
| [@Hans02-Neo](https://github.com/Hans02-Neo) | Fathan Mubina | Junior Developer | Frontend (Inertia+React, TypeScript, Tailwind) |
| [@Odauna](https://github.com/Odauna) | Ihsan | Junior Developer | Backend (Laravel API, Database, PostgreSQL) |
| | Azis | Learning Mentor | Discussion partner, debugging buddy, concept explainer, code review prep, learning tracker — membantu Fathan & Ihsan |

**Stakeholder:**
- **Pak Mahfud** — IT Manager SMA UII Yogyakarta (Client Representative)

---

## 📚 Struktur Playbook

### [01-getting-started](docs/01-getting-started) — Onboarding & Setup

| Document | Description | For |
|---|---|---|
| [`onboarding.md`](docs/01-getting-started/onboarding.md) | Checklist hari pertama | New members |
| [`environment-setup.md`](docs/01-getting-started/environment-setup.md) | Setup local development | Developers |
| [`team-roles.md`](docs/01-getting-started/team-roles.md) | Detail peran & tanggung jawab | All members |

### [02-workflow](docs/02-workflow) — Git, Trello, Communication

| Document | Description | For |
|---|---|---|
| [`git-github-workflow.md`](docs/02-workflow/git-github-workflow.md) | Branching, commit, PR workflow | Developers |
| [`trello-workflow.md`](docs/02-workflow/trello-workflow.md) | Product management dengan Trello | Ahmad Hanif |
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
| [`user-story.md`](docs/04-templates/user-story.md) | Template user story | Ahmad Hanif |
| [`github-issue.md`](docs/04-templates/github-issue.md) | Template GitHub Issue | All members |
| [`pull-request.md`](docs/04-templates/pull-request.md) | Template Pull Request | Developers |
| [`sprint-planning.md`](docs/04-templates/sprint-planning.md) | Template sprint planning | Sandikodev |

### [05-adr](docs/05-adr) — Architecture Decision Record

| Document | Description |
|---|---|
| [`001-monorepo.md`](docs/05-adr/001-monorepo.md) | Decision: Monorepo dengan submodule |
| [`002-livewire-first.md`](docs/05-adr/002-livewire-first.md) | ⚠️ **Superseded** — lihat ADR-002-v2 |
| [`002-v2-inertia-react.md`](docs/05-adr/002-v2-inertia-react.md) | Decision: InertiaJS + React sejak MVP |
| [`003-database-mysql.md`](docs/05-adr/003-database-mysql.md) | ⚠️ **Superseded** — lihat ADR-003-v2 |
| [`003-v2-database-postgresql.md`](docs/05-adr/003-v2-database-postgresql.md) | Decision: PostgreSQL via NeonDB untuk production |
| [`004-neondb-sanctum.md`](docs/05-adr/004-neondb-sanctum.md) | Decision: NeonDB + Laravel Sanctum |
| [`005-porting-strategy.md`](docs/05-adr/005-porting-strategy.md) | Decision: Porting strategy Monolith → API + Next.js |

### [06-learning-path](docs/06-learning-path) — Junior Developer Roadmap

| Document | Description | For |
|---|---|---|
| [`junior-dev-roadmap.md`](docs/06-learning-path/junior-dev-roadmap.md) | 8 minggu learning path | Fathan, Ihsan |

### [07-project](docs/07-project) — SMART Absen Project Plans

| Document | Description |
|---|---|
| [`smart-absen-overview.md`](docs/07-project/smart-absen-overview.md) | Project overview lengkap |
| [`sprint-1-plan.md`](docs/07-project/sprint-1-plan.md) | Sprint 1: Authentication & SSO |
| [`sprint-2-plan.md`](docs/07-project/sprint-2-plan.md) | Sprint 2: Presensi Module |
| [`mvp-scope.md`](docs/07-project/mvp-scope.md) | MVP definition & scope |

### [ROLES](ROLES) — Dinamic Role Definitions

| Document | Description | For |
|---|---|---|
| [`_TEMPLATE.md`](ROLES/_TEMPLATE.md) | Template untuk buat role baru | Maintainer |
| [`product-analyst.md`](ROLES/product-analyst.md) | Product Analyst — AI instructions, tanggung jawab | Ahmad Hanif |
| [`junior-backend.md`](ROLES/junior-backend.md) | Junior Backend — AI instructions, learning path | Ihsan |
| [`junior-frontend.md`](ROLES/junior-frontend.md) | Junior Frontend — AI instructions, learning path | Fathan |
| [`learning-mentor.md`](ROLES/learning-mentor.md) | Learning Mentor — AI instructions, mentoring scope | Azis |
| [`senior-developer.md`](ROLES/senior-developer.md) | Senior Developer / Tech Lead — AI instructions | Sandikodev |
| [`project-manager.md`](ROLES/project-manager.md) | Project Manager — AI instructions | Sandikodev |
| [`stakeholder.md`](ROLES/stakeholder.md) | Stakeholder — AI instructions | Pak Mahfud |

### [WORKFLOWS](WORKFLOWS) — AI Agent Workflows

| Document | Description | For |
|---|---|---|
| [`ai-agent-workflow.md`](WORKFLOWS/ai-agent-workflow.md) | TACO Protocol: Trello → AI → Commit → Output | Semua developer |

### [ACCESS](ACCESS) — Access Control Policies

| Document | Description | For |
|---|---|---|
| [`matrix-per-role.md`](ACCESS/matrix-per-role.md) | Matriks akses GitHub, Trello, environment per role | All members |
| [`outsourced-policy.md`](ACCESS/outsourced-policy.md) | Kebijakan keamanan pekerja outsourcing/mitra | Sandikodev |

---

## 🚀 Quick Start

### Untuk Product Analyst (Ahmad Hanif)
1. Baca [`ROLES/product-analyst.md`](ROLES/product-analyst.md) — role & AI instructions
2. Baca [`docs/04-templates/user-story.md`](docs/04-templates/user-story.md)
3. Setup [OpenKB](https://github.com/SMA-UII-Yogyakarta/aksesekolah/blob/main/.openkb/TEMPLATE.md)
4. Copy role file: `copy ROLES/product-analyst.md ~/.openkb/ROLES/`
5. Buat user story di Trello, link ke GitHub Issue

### Untuk Developer (Fathan, Ihsan)
1. Baca [`ROLES/<role>.md`](ROLES/_TEMPLATE.md) — role & AI instructions
2. Baca [`docs/01-getting-started/onboarding.md`](docs/01-getting-started/onboarding.md)
3. Setup environment: [`docs/01-getting-started/environment-setup.md`](docs/01-getting-started/environment-setup.md)
4. Setup OpenKB: `copy ROLES/<role>.md ~/.openkb/ROLES/`
5. Pahami workflow AI Agent: [`WORKFLOWS/ai-agent-workflow.md`](WORKFLOWS/ai-agent-workflow.md)
6. Ambil Issue dari GitHub Project, kerjakan dengan AI Agent

### Untuk Reviewer / Tech Lead (Sandikodev)
1. Code Review Checklist: [`docs/03-sop/code-review.md`](docs/03-sop/code-review.md)
2. Sprint Planning Template: [`docs/04-templates/sprint-planning.md`](docs/04-templates/sprint-planning.md)
3. Outsourced Policy: [`ACCESS/outsourced-policy.md`](ACCESS/outsourced-policy.md)

### Untuk Stakeholder (Pak Mahfud)
1. Baca [`ROLES/stakeholder.md`](ROLES/stakeholder.md) — role & ekspektasi
2. Lihat progress di Trello Product Roadmap

---

## 🛠️ Tech Stack

### Current Architecture (MVP — Fase 1)
```
Backend  : Laravel 13 (PHP 8.4) + Service Layer
Frontend : InertiaJS 3 + React 19 + TypeScript 5.7 + Tailwind CSS 4 + Vite 8
Database : PostgreSQL 16 via NeonDB
Auth     : Laravel Sanctum + Spatie Laravel Permission (RBAC)
Packages : Bun (frontend), Composer (backend)
Queue    : Database driver (Redis nanti)
Storage  : S3-compatible (Wasabi / MinIO)
Deploy   : Laragon (dev) → Nginx (production)
```

### Target Architecture (Fase 2 — Dedicated Backend + Multi Client)
```
Backend  : Laravel 13 API-Only (Core) — Service Layer, Queue, SSO Provider
Frontend : Next.js (Web App) — SSR/SSG, PWA
Mobile   : React Native / Flutter (dipertimbangkan oleh tim & stakeholder)
Auth     : SSO (Sanctum Identity Provider) — reusable oleh semua client
Third-Party: SIAD, sistem eksternal via API Gateway
```

### Porting Strategy: Fase 1 → Fase 2
```
Fase 1 (Monolith + Inertia)    →    Fase 2 (API-Only + Multi Client)
├── Controller tipis            →    Controller tipis (sama, reuse)
├── Service Layer di App\Services → Service Layer (sama, reuse)
├── Inertia merender React      →    Next.js / RN / Flutter consume API
├── API routes (/api/*) aktif   →    API routes (sama, no change)
├── Sanctum session auth        →    Sanctum token auth (switch mode)
└── Zero rewrite — tinggal tambah frontend baru
```

---

## 📊 Project Management Tools

| Tool | Purpose | Link |
|---|---|---|
| **Trello** | Product Roadmap, Sprint Board | [SMART ABSEN SMAUII](https://trello.com/b/BHXA6ZcR/smart-absen-smauii) |
| **GitHub Projects** | Engineering Task Tracking | [Project](https://github.com/orgs/SMA-UII-Yogyakarta/projects/1) |
| **GitHub Issues** | Technical Task | [Issues](https://github.com/SMA-UII-Yogyakarta/core/issues) |
| **WhatsApp Group** | Komunikasi Cepat | Private Group |

---

## ⏱️ Timeline & Milestones

```
Week 1-2  → Sprint 1: Sinkronisasi & Setup — env, package, DB, Sanctum, docs sync
Week 3-4  → Sprint 2: Authentication & SSO — registrasi, login, role, permission
Week 5-6  → Sprint 3: Presensi Module (Core) — check-in, geolokasi, swafoto
Week 7-8  → Sprint 4: Laporan, Admin Panel, UAT, Deployment
```

**MVP Target:** Akhir Minggu 6  
**Production Ready:** Akhir Minggu 8  
*Catatan: Timeline ini merefleksikan reset stack (dari Livewire/MySQL ke Inertia+React/PostgreSQL) dan penyesuaian learning path untuk Fathan, Ihsan, dan Azis.*

---

## 📖 Repositori

| Repo | Deskripsi | Link |
|---|---|---|
| **aksesekolah** | Monorepo Entrypoint | [GitHub](https://github.com/SMA-UII-Yogyakarta/aksesekolah) |
| **core** | Backend Laravel | [GitHub](https://github.com/SMA-UII-Yogyakarta/core) |
| **webapp** | Frontend (Next.js) | [GitHub](https://github.com/SMA-UII-Yogyakarta/webapp) |
| **flutter** | Mobile App | [GitHub](https://github.com/SMA-UII-Yogyakarta/flutter) |
| **playbook** | Engineering Handbook | [GitHub](https://github.com/SMA-UII-Yogyakarta/playbook) |

---

## 🎓 Learning Culture

> "We don't just build software. We build engineers."

Setiap Pull Request adalah kesempatan belajar.  
Setiap Code Review adalah teaching moment.  
Setiap Sprint Retrospective adalah improvement.

### Expected Outcome (8 Minggu)
- ✅ Fathan mampu develop fitur Livewire/React secara mandiri
- ✅ Ihsan mampu develop fitur Laravel API secara mandiri
- ✅ Ahmad mampu menulis requirement yang implementable
- ✅ Sandikodev tidak menjadi bottleneck

---

## 📞 Kontak

**PT Koneksi Jaringan Indonesia**  
📧 Email: [hello@koneksi.id](mailto:hello@koneksi.id)  
📱 WhatsApp: [Contact Link](https://wa.me/...)

**SMA UII Yogyakarta**  
📍 Alamat: Jl. Taman Siswa No.158, Wirogunan, Mergangsan, Kota Yogyakarta 55151  
📞 Telp: (0274) 489693

---

## 📄 License

Internal use only — PT Koneksi Jaringan Indonesia & SMA UII Yogyakarta

---

**Last Commit:** [See History](https://github.com/SMA-UII-Yogyakarta/playbook/commits/main).
