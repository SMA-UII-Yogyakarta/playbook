# Learning Resources — SMART Absen SMAUII

> Structured learning guide for the SMART Absen development team.

---

## 📚 Main Curriculum — OpenKB for Junior

The team uses **[openkb-for-junior](https://github.com/konxc/openkb-for-junior)** as the main learning curriculum. This repo contains **15 phases** of Laravel learning from zero to job-ready.

### How to Access

```bash
# Clone curriculum
git clone git@github.com:konxc/openkb-for-junior.git
cd openkb-for-junior
```

**Structure:**
```
openkb-for-junior/
├── journey/                    ← Main curriculum (15 phases)
│   ├── 00-CURRICULUM.md        ← Master learning map
│   ├── FASE-01-FONDASI-MUTLAK/ ← Programming basics
│   ├── FASE-02-PHP-FUNDAMENTAL/
│   ├── FASE-03-OOP/
│   ├── FASE-04-FUNCTIONAL/
│   ├── FASE-05-WEB-FUNDAMENTAL/
│   ├── FASE-06-LARAVEL-DEEP-DIVE/    ← Laravel core
│   ├── FASE-07-DATABASE/             ← SQL & database design
│   ├── FASE-08-DESIGN-PATTERN/
│   ├── FASE-09-FRONTEND/
│   ├── FASE-10-INFRASTRUKTUR/
│   ├── FASE-11-TOOLS/
│   ├── FASE-12-TESTING/
│   ├── FASE-13-CODE-QUALITY/
│   ├── FASE-14-PORTFOLIO/
│   └── FASE-15-BISNIS/
└── PRAKTIK-CODING/             ← Practice exercises
```

---

## 🎯 Learning Path Per Role

### Fathan — Junior Frontend Developer

**Focus:** Frontend track with InertiaJS + React 19 + TypeScript

| Phase | Topic | Estimated Time | Priority |
|-------|-------|----------------|----------|
| 01 | Absolute Foundation | 1-2 weeks | ✅ Required |
| 02 | PHP Fundamental | 2-3 weeks | ✅ Required |
| 03 | OOP | 2-3 weeks | ✅ Required |
| 05 | Web Fundamental | 2 weeks | ✅ Required |
| 06 | Laravel Deep Dive | 4-6 weeks | ✅ Required |
| 09 | Frontend in Laravel | 1-2 weeks | ✅ **Main focus** |
| 11 | Tools & Workflow | 1-2 weeks | ✅ Required |

**Key Documents:**
- `FASE-09/09-01-cara-kerja-vite.md`
- `FASE-09/09-02-tailwind-css.md`
- `FASE-09/09-06-inertiajs-dan-react.md` (if available)
- `FASE-09/09-05-hot-reload-hmr.md`
- React + TypeScript official docs

**Additional Materials:**
- [React 19 Documentation](https://react.dev/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/)
- [InertiaJS Documentation](https://inertiajs.com/)
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro)

**Sprint 1 Target:**
- US-005: Login page (React + Inertia + Tailwind)
- Integration with backend Sanctum via Inertia

---

### Ihsan — Junior Backend Developer

**Focus:** Backend track with Laravel Sanctum & Database

| Phase | Topic | Estimated Time | Priority |
|-------|-------|----------------|----------|
| 01 | Absolute Foundation | 1-2 weeks | ✅ Required |
| 02 | PHP Fundamental | 2-3 weeks | ✅ Required |
| 03 | OOP | 2-3 weeks | ✅ Required |
| 05 | Web Fundamental | 2 weeks | ✅ Required |
| 06 | Laravel Deep Dive | 4-6 weeks | ✅ **Main focus** |
| 07 | Database & SQL | 2 weeks | ✅ **Main focus** |
| 08 | Design Pattern | 2-3 weeks | ✅ Required |
| 11 | Tools & Workflow | 1-2 weeks | ✅ Required |

**Key Documents:**
- `FASE-06/06-03-routing-web-php.md`
- `FASE-06/06-04-controller-dan-request.md`
- `FASE-06/06-05-model-dan-eloquent-orm.md`
- `FASE-06/06-07-middleware-dan-auth.md`
- `FASE-06/06-08-service-layer.md`
- `FASE-07/07-03-relationship-dan-join.md`
- `FASE-07/07-06-n-plus-one-problem.md`

**Sprint 1 Target:**
- US-001: Login with Sanctum token
- US-002: Logout + revoke token
- US-003: RBAC middleware
- US-004: Session management

---

### Azis — Learning Mentor / Technical Guide

**Focus:** Master the entire stack for mentoring

| Phase | Topic | Estimated Time | Priority |
|-------|-------|----------------|----------|
| 01-05 | Foundation (review) | 1-2 weeks | ⚡ Quick review |
| 06 | Laravel Deep Dive | 2-3 weeks | ✅ Required |
| 07 | Database & SQL | 1-2 weeks | ✅ Required |
| 08 | Design Pattern | 1-2 weeks | ✅ Required |
| 09 | Frontend in Laravel | 1 week | ⚡ Overview |
| 10 | Infrastructure & Deployment | 2 weeks | ✅ **Main focus** |
| 11 | Tools & Workflow | 1 week | ✅ Required |
| 12 | Testing & QA | 1-2 weeks | ✅ Required |

**Key Documents:**
- `FASE-10/10-03-laragon-di-windows.md`
- `FASE-10/10-05-ssh-dan-terminal.md`
- `FASE-10/10-06-docker-dasar.md`
- `FASE-11/11-04-artisan-cli.md`
- `FASE-11/11-05-tinker-dan-repl.md`
- `laravel-telescope.md`
- `laragon-vs-artisan-serve.md`

**Responsibilities:**
- Facilitate environment setup (Laragon, database, Node.js)
- Debugging session (Telescope, log reading, Tinker)
- Concept explanation (Laravel lifecycle, middleware, Eloquent)
- Initial code review before submitting to PM/Senior

---

### Hanif — Product Analyst

**Focus:** Understanding technical constraints & possibilities

| Phase | Topic | Estimated Time | Priority |
|-------|-------|----------------|----------|
| 01 | Absolute Foundation | 1 week | ⚡ Overview |
| 05 | Web Fundamental | 1 week | ✅ Required |
| 06 | Laravel Deep Dive | 2 weeks | ⚡ Overview |
| 15 | Business & Industry | 1 week | ✅ Required |

**Key Documents:**
- `FASE-05/05-01-cara-kerja-web.md`
- `FASE-05/05-02-http-dan-rest.md`
- `FASE-06/06-02-arsitektur-laravel.md`
- `FASE-15/15-01-web-industri-ekosistem.md`
- `FASE-15/15-02-dari-kode-ke-produk.md`
- `FASE-15/15-03-peran-tim-pengembang.md`

**Target:**
- Understand technical feasibility of features
- Map requirement → technical implementation
- Effective communication with dev team

---

## 🛠️ Tools & Environment

### Development Stack (Laragon 6.0)

| Tool | Version | Path |
|------|---------|------|
| PHP | 8.4.22 NTS | `C:\laragon\bin\php\php-8.4.22-nts-Win32-vs17-x64\` |
| Apache | 2.4.54 | `C:\laragon\bin\apache\` |
| PostgreSQL | 16 | `C:\laragon\bin\postgresql\postgresql-16.x-winx64\` |
| Node.js | 22.14.0 | `C:\laragon\bin\nodejs\` |
| **Bun** | latest | `C:\Users\<user>\.bun\bin\bun.exe` |
| Composer | latest | `C:\laragon\bin\composer\composer.phar` |
| Redis | 5.0.14.1 | `C:\laragon\bin\redis\` |

**Setup Guide:**
- [`02-lingkungan-development.md` (aksesekolah)](https://github.com/SMA-UII-Yogyakarta/aksesekolah/blob/main/docs/02-lingkungan-development.md)
- [OpenKB FASE-10: Laragon on Windows](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-10-INFRASTRUKTUR-DAN-DEPLOYMENT/10-03-laragon-di-windows.md)

---

## 📖 How to Learn Effectively

### Method 1: Sequential Learning (Recommended)

1. Open `journey/00-CURRICULUM.md` — understand the learning map
2. Start from `FASE-01/01-01-what-is-programming.md`
3. Each document has a **Practice** section — do it!
4. After a few phases, open `PRAKTIK-CODING/` for hands-on practice
5. Continue to the next phase

### Method 2: Topic-Based Learning

| Need | Open |
|------|------|
| Understand MVC in Laravel | `FASE-08/08-02-mvc-architecture.md` |
| How Eloquent works | `FASE-06/06-05-model-dan-eloquent-orm.md` |
| Deploy to hosting | `FASE-10/10-07-cpanel-dan-hosting.md` |
| Interview preparation | `FASE-14/14-06-pertanyaan-interview-laravel.md` |

### Method 3: Learn by Doing

After reading a few phases, jump straight into practice in `PRAKTIK-CODING/`:
- `latihan-01` — Variables and data types ⚡
- `latihan-02` — Loops and conditions ⚡
- `latihan-03` — Simple class
- `latihan-04` — Routing and controller ⚡
- `latihan-05` — Eloquent query ⚡
- `latihan-06` — Building CRUD features ⚡
- `latihan-07` — Payment API integration
- `capstone` — Create a simple feature ⚡

---

## 🧪 Progress Tracking

Learning progress is tracked on the **Trello board** [`SMART ABSEN SMAUII`](https://trello.com/b/BHXA6ZcR/smart-absen-smauii).

**List:** `📚 Learning Path (Azis)`

Each team member has a card with:
- Checklist of phases to complete
- Link to openkb-for-junior documents
- Progress status (To Do / In Progress / Done)
- Discussion & blockers in comments

---

## 📞 Mentor & Support

| Role | Person | Scope |
|------|--------|-------|
| **Learning Mentor** | Azis | Environment, debugging, concept explanation |
| **Project Manager** | Sandikodev | Final code review, sprint planning, merge PR |
| **Senior Developer** | Sandikodev | Architecture decision, technical guidance |

**How to Ask for Help:**
1. Try reading openkb-for-junior documentation first
2. If still stuck, ask on the Trello card (comment) or Discord/WhatsApp
3. For debugging, prepare: error message, log, screenshot

---

## 📊 Estimated Timeline

| Week | Activity |
|------|----------|
| 1-2 | **Sprint 1 — Setup:** Sync docs, installation (Bun, NeonDB, PostgreSQL), setup Sanctum & Spatie. Fathan: React basics + TypeScript. Ihsan: Laravel Service Layer + PostgreSQL. Azis: Onboarding + facilitate setup |
| 3-4 | **Sprint 2 — Auth:** Sanctum login/register, Spatie RBAC, profile page (React+Inertia). Fathan: InertiaJS + React hooks. Ihsan: Sanctum API, Spatie middleware |
| 5-6 | **Sprint 3 — Attendance:** Attendance with geolocation, selfie photo. Fathan: React advanced. Ihsan: Attendance API, photo upload |
| 7-8 | **Sprint 4 — Reports:** Attendance reports, admin panel, UAT. Review & final assessment |

**Note:** Timeline is flexible — the important thing is to **understand the concepts** before moving on.

---

## 🔗 External References

| Resource | Description |
|----------|-------------|
| [Laravel Documentation](https://laravel.com/docs) | Official docs — always up to date |
| [Laracasts](https://laracasts.com) | Video tutorials (free + paid) |
| [PHP The Right Way](https://phptherightway.com) | PHP best practices |
| [Stack Overflow](https://stackoverflow.com/questions/tagged/laravel) | Q&A community |

---

<p align="center">
  <b>Learning is a lifelong process — enjoy every step! 🚀</b><br>
  <i>"The expert in anything was once a beginner."</i>
</p>
