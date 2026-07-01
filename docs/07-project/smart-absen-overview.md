# SMART Absen — Project Overview

> Complete documentation of the SMART Absen SMA UII Yogyakarta project.

---

## 🎯 Project Vision

**SMART Absen** — Digital Attendance System for SMA UII Yogyakarta

**Vision:**
Build a modern, accurate, and real-time attendance system to improve discipline and monitoring of attendance for students, teachers, and staff of SMA UII Yogyakarta.

---

## 📊 Project Facts

| Attribute | Value |
|---|---|
| **Client** | SMA UII Yogyakarta |
| **Developer** | PT Koneksi Jaringan Indonesia |
| **Project Manager** | Sandikodev |
| **Product Analyst** | Ahmad Hanif Hasan Rosyidi |
| **Developers** | Fathan Mubina (Frontend), Ihsan (Backend) |
| **Learning Mentor** | Azis |
| **Stakeholder** | Pak Mahfud (IT Manager SMA UII) |
| **Timeline** | 8 weeks (2 months) |
| **Budget** | Rp 8,500,000 |
| **Start Date** | June 2026 |
| **Target MVP** | July 2026 (Week 4) |
| **Production Ready** | August 2026 (Week 8) |

---

## 🏗️ Architecture

### Current Architecture (MVP — Phase 1: Monolith + Inertia)

```
┌─────────────────────────────────────┐
│         User (Browser)              │
│   (Desktop / Mobile / Tablet)       │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│    Laravel 13 + InertiaJS 3         │
│    (Monolith with API-ready)        │
├─────────────────────────────────────┤
│  ┌────────┐  ┌────────────────────┐ │
│  │ React  │  │  Inertia Bridge   │ │
│  │ 19+TS  │  │  (Server->Client) │ │
│  └────────┘  └────────────────────┘ │
│  ┌────────────┐  ┌────────────────┐ │
│  │ Tailwind   │  │  Vite 8 + Bun  │ │
│  │ CSS 4      │  │  (HMR)         │ │
│  └────────────┘  └────────────────┘ │
│  ┌────────────────────────────────┐ │
│  │ Service Layer (app/Services/)   │ │
│  └────────────────────────────────┘ │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│    PostgreSQL 16 via NeonDB         │
│    (Serverless, auto-scale)         │
│                                     │
│  ┌─────────────────────────────┐   │
│  │  Tables (10 total):         │   │
│  │  - users                    │   │
│  │  - siswa                    │   │
│  │  - guru                     │   │
│  │  - wali_murid               │   │
│  │  - kelas                    │   │
│  │  - presensi                 │   │
│  │  - pengajuan_izin           │   │
│  │  - jadwal_piket             │   │
│  │  - pengaturan_jam_presensi   │   │
│  │  - kalender_akademik        │   │
│  └─────────────────────────────┘   │
└─────────────────────────────────────┘
```

### Target Architecture (Phase 2 — API-Only + Multi Client)

```
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│   Web Browser   │  │   Mobile App    │  │   Third-Party   │
│   (Next.js)     │  │ (RN / Flutter)  │  │   (SIAD, etc)   │
└────────┬────────┘  └────────┬────────┘  └────────┬────────┘
         │                    │                     │
         └────────────────────┼─────────────────────┘
                              │
                    ┌─────────▼───────────┐
                    │  Laravel 13 API     │
                    │  (Core Backend)     │
                    │  — Sanctum SSO      │
                    │  — Spatie RBAC      │
                    │  — Service Layer    │
                    │  — Queue/Job        │
                    └─────────┬───────────┘
                              │
                              ▼
                  ┌───────────────────────┐
                  │   PostgreSQL 16       │
                  │   via NeonDB          │
                  │   + Redis Cache       │
                  └───────────────────────┘
```

**Porting Strategy:** Service Layer + dual controller (Web + API) from Phase 1 — zero rewrite when migrating to Phase 2. See [`ADR-005`](../05-adr/005-porting-strategy.md) for details.

---

## 📦 Features

### MVP Features (Sprint 1-2)

#### 1. Authentication & Authorization
- Login with email & password
- Role-based access (Admin, Teacher, Student, Staff)
- Session management
- Logout

#### 2. Student Attendance
- Attendance form with geolocation
- Camera selfie mandatory
- Radius validation 50m from school
- Time validation (06:00 - 07:30 WIB)
- Status: On Time, Late, Absent
- Duplicate prevention (1x per day)
- Attendance history

#### 3. Teacher & Staff Attendance
- Similar to student attendance
- Without selfie (optional)
- Teaching schedule validation

#### 4. Dashboard
- Admin Dashboard: Complete statistics
- Teacher Dashboard: Teaching schedule, own attendance
- Student Dashboard: Own attendance, history

#### 5. Reports
- Export attendance per class (Excel)
- Export attendance per student (PDF)
- Period filter

---

### Phase 2 Features (Sprint 3-4)

#### 6. Leave Application
- Students can submit leave (sick, permission, absent)
- Upload medical certificate (if sick)
- Homeroom teacher approval
- WhatsApp notification (optional)

#### 7. Duty Schedule
- Duty schedule management
- Duty attendance
- Duty reports

#### 8. Academic Calendar
- Effective days management
- Holiday management
- Attendance validation based on calendar

---

## 🗺️ Roadmap

```
Week 1-2  → Sprint 1: Setup & Auth Foundation
            └─ Docs synchronization, installation, NeonDB setup
            └─ Sanctum, Spatie, Service Layer
            └─ Learning: React basics, TypeScript, PostgreSQL

Week 3-4  → Sprint 2: Authentication & SSO
            └─ Login/Register, RBAC, Session Management
            └─ Profile Page, Basic Dashboard

Week 5-6  → Sprint 3: Attendance Module (MVP)
            └─ Student Attendance (geolocation + selfie)
            └─ Teacher Attendance, Role-specific Dashboards

Week 7-8  → Sprint 4: Reports & Production
            └─ Export Excel/PDF, Admin Panel
            └─ UAT, Bug fixing, Performance, Deployment
```

> **Note:** This timeline reflects the stack reset from Livewire/MySQL to Inertia+React/PostgreSQL in weeks 1-2. MVP target shifts to end of Sprint 3. See ADR-002-v2 and ADR-003-v2 for decision details.

---

## 📁 Repository Structure

```
aksesekolah/ (Monorepo Entrypoint)
│
├── apps/
│   ├── backend/     → core (Laravel 13)
│   ├── frontend/    → webapp (Next.js 14, Sprint 3+)
│   └── mobile/      → flutter (Mobile app, Backlog)
│
├── docs/            → Complete documentation
│   ├── 01-brief-project.md
│   ├── 02-arsitektur-sistem.md
│   ├── 03-database-erd.md
│   └── ...
│
├── .opencode/       → AI Agent configuration
├── .openkb/         → Knowledge base
└── README.md

core/ (Backend Laravel)
│
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   ├── Middleware/
│   │   └── Requests/
│   ├── Models/
│   ├── Services/
│   └── Policies/
│
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── factories/
│
├── resources/
│   ├── views/
│   ├── js/
│   └── css/
│
├── routes/
│   ├── web.php
│   └── api.php
│
├── tests/
│   ├── Unit/
│   └── Feature/
│
└── .env.example
```

---

## 👥 Team Roles

| Role | Person | Responsibilities |
|---|---|---|
| **Project Manager** | Sandikodev | Planning, Architecture, Code Review, Mentoring |
| **Product Analyst** | Ahmad Hanif | Requirement, User Story, UAT, Stakeholder Communication |
| **Frontend Developer** | Fathan Mubina | React, TypeScript, Tailwind CSS, InertiaJS |
| **Backend Developer** | Ihsan | Laravel API, Database, Validation, Testing |
| **Learning Mentor** | Azis | Mentoring, Code Review, Concept Explainer, Debugging Buddy |

---

## 🛠️ Tech Stack

### Backend
- **Framework:** Laravel 13
- **PHP:** 8.4 NTS
- **Architecture:** Service Layer (`app/Services/`) — thin controller
- **Database:** PostgreSQL 16 via NeonDB (production), PostgreSQL 16 (local)
- **Cache:** Redis 7.0 (optional)
- **Queue:** Database driver (Redis later)
- **Auth:** Laravel Sanctum (session for Inertia, token for API)
- **RBAC:** Spatie Laravel Permission
- **Validation:** Form Request
- **Testing:** PHPUnit + Feature Test

### Frontend (MVP — Phase 1)
- **Framework:** InertiaJS 3 + React 19 + TypeScript 5.7
- **Styling:** Tailwind CSS 4
- **Build:** Vite 8
- **Package Manager:** Bun
- **Testing:** Jest + React Testing Library

### Frontend (Phase 2 — Dedicated)
- **Framework:** Next.js (Web App)
- **Language:** TypeScript
- **Styling:** Tailwind CSS 4
- **State:** TanStack Query + React Context

### Mobile (Phase 2 — Under Consideration)
- **Option 1:** React Native (reuse React knowledge)
- **Option 2:** Flutter (cross-platform)

### Infrastructure
- **Local Dev:** Laragon 6.0 + PostgreSQL
- **Database Cloud:** NeonDB (serverless PostgreSQL)
- **Production:** Nginx + PHP-FPM
- **SSL:** Let's Encrypt
- **Storage:** Wasabi / MinIO (S3-compatible)
- **Monitoring:** Laravel Telescope, Sentry

---

## 📊 Database Schema

### Main Tables

```
users
├── id
├── name
├── email
├── password
├── role (admin, guru, siswa, staff)
└── timestamps

siswa
├── id
├── user_id
├── nis
├── nisn
├── kelas_id
└── timestamps

guru
├── id
├── user_id
├── nip
├── mata_pelajaran
└── timestamps

kelas
├── id
├── nama (X-A, XI-IPA-1, etc)
├── wali_murid_id
└── timestamps

presensi
├── id
├── siswa_id / guru_id
├── tanggal
├── jam_masuk
├── jam_pulang (optional)
├── latitude
├── longitude
├── foto (URL to object storage)
├── status (ontime, late, absent, izin, sakit, alfa)
└── timestamps
```

---

## 🔐 Security Considerations

### Authentication
- Password hashing (bcrypt)
- Session management (Sanctum)
- CSRF protection
- XSS prevention

### Authorization
- Role-based access control (RBAC)
- Policy for each resource
- Middleware for route protection

### Data Protection
- Input validation
- SQL injection prevention (Eloquent)
- Mass assignment protection ($fillable)
- Rate limiting for API

---

## 📈 Success Metrics

### Development Metrics
- Sprint velocity consistency
- Code coverage > 70%
- PR review time < 24 hours
- Bug rate < 5%

### Business Metrics
- Attendance accuracy > 95%
- System uptime > 99%
- User satisfaction > 4.0/5.0
- Admin efficiency (time saved)

---

## 🚀 Deployment Plan

### Staging
- URL: `staging.smauiiyk.sch.id`
- Purpose: UAT, Testing
- Deploy: Every merge to main

### Production
- URL: `smauiiyk.sch.id`
- Purpose: Live users
- Deploy: End of sprint (2 weeks)

---

## 📞 Contact

**PT Koneksi Jaringan Indonesia**
- Email: hello@koneksi.id
- WhatsApp: [Group Link]

**SMA UII Yogyakarta**
- Address: Jl. Taman Siswa No.158, Wirogunan, Mergangsan, Kota Yogyakarta 55151
- Phone: (0274) 489693
- Stakeholder: Pak Mahfud

---

**Next:** [`sprint-1-plan.md`](sprint-1-plan.md)  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
