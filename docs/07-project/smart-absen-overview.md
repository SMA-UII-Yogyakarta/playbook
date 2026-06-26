# SMART Absen — Project Overview

> Dokumentasi lengkap project SMART Absen SMA UII Yogyakarta.

---

## 🎯 Project Vision

**SMART Absen** — Sistem Presensi Digital SMA UII Yogyakarta

**Vision:**
Membangun sistem presensi yang modern, akurat, dan real-time untuk meningkatkan disiplin dan monitoring kehadiran siswa, guru, dan staff SMA UII Yogyakarta.

---

## 📊 Project Facts

| Attribute | Value |
|---|---|
| **Client** | SMA UII Yogyakarta |
| **Developer** | PT Koneksi Jaringan Indonesia |
| **Project Manager** | Sandikodev |
| **Product Analyst** | Ahmad Hanif Hasan Rosyidi |
| **Developers** | Fathan Mubina, Ihsan |
| **Stakeholder** | Pak Mahfud (IT Manager SMA UII) |
| **Timeline** | 8 minggu (2 bulan) |
| **Budget** | Rp 8.500.000 |
| **Start Date** | Juni 2026 |
| **Target MVP** | Juli 2026 (Minggu 4) |
| **Production Ready** | Agustus 2026 (Minggu 8) |

---

## 🏗️ Architecture

### Current Architecture (MVP — Bulan 1)

```
┌─────────────────────────────────────┐
│         User (Browser)              │
│   (Desktop / Mobile / Tablet)       │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│      Laravel 13 + Livewire 3        │
│      (Monolithic Application)       │
├─────────────────────────────────────┤
│  ┌──────────┐  ┌──────────┐        │
│  │  Blade   │  │ Livewire │        │
│  │  Views   │  │ Components│       │
│  └──────────┘  └──────────┘        │
│  ┌──────────┐  ┌──────────┐        │
│  │ Tailwind │  │  Alpine  │        │
│  │   CSS    │  │    JS    │        │
│  └──────────┘  └──────────┘        │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│       MySQL 8.0.30 Database         │
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

---

### Target Architecture (Bulan 2+)

```
┌─────────────────┐         ┌─────────────────┐
│   Web Browser   │         │   Mobile App    │
│   (Next.js 14)  │         │   (Flutter)     │
└────────┬────────┘         └────────┬────────┘
         │                           │
         │         REST API          │
         └───────────┬───────────────┘
                     │
                     ▼
         ┌───────────────────────┐
         │   Laravel 13 API      │
         │   (Core Backend)      │
         │   + Sanctum Auth      │
         └───────────┬───────────┘
                     │
                     ▼
         ┌───────────────────────┐
         │   MySQL 8.0.30        │
         │   + Redis Cache       │
         └───────────────────────┘
```

---

## 📦 Features

### MVP Features (Sprint 1-2)

#### 1. Authentication & Authorization
- Login dengan email & password
- Role-based access (Admin, Guru, Siswa, Staff)
- Session management
- Logout

#### 2. Presensi Siswa
- Form presensi dengan geolokasi
- Swafoto kamera wajib
- Validasi radius 50m dari sekolah
- Validasi waktu (06:00 - 07:30 WIB)
- Status: On Time, Late, Absent
- Duplicate prevention (1x per hari)
- Riwayat presensi

#### 3. Presensi Guru & Staff
- Similar dengan presensi siswa
- Tanpa swafoto (opsional)
- Jadwal mengajar validation

#### 4. Dashboard
- Dashboard Admin: Statistik lengkap
- Dashboard Guru: Jadwal mengajar, presensi sendiri
- Dashboard Siswa: Presensi sendiri, riwayat

#### 5. Laporan
- Export presensi per kelas (Excel)
- Export presensi per siswa (PDF)
- Filter per periode

---

### Phase 2 Features (Sprint 3-4)

#### 6. Pengajuan Izin
- Siswa dapat mengajukan izin (sakit, izin, alfa)
- Upload surat dokter (jika sakit)
- Approval wali kelas
- Notifikasi WhatsApp (opsional)

#### 7. Jadwal Piket
- Management jadwal piket
- Presensi piket
- Laporan piket

#### 8. Kalender Akademik
- Management hari efektif
- Management libur
- Validasi presensi berdasarkan kalender

---

## 🗺️ Roadmap

```
Week 1-2  → Sprint 1: Authentication & SSO
            └─ Login, Logout, Role Management

Week 3-4  → Sprint 2: Presensi Module (MVP)
            └─ Presensi Siswa, Guru, Dashboard

Week 5-6  → Sprint 3: Laporan & Admin Panel
            └─ Export Excel/PDF, Admin Features

Week 7-8  → Production Audit, Testing, Refining
            └─ Bug fixing, Performance optimization, UAT
```

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
├── docs/            → Dokumentasi lengkap
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
| **Frontend Developer** | Fathan Mubina | Livewire, Blade, Tailwind, React (later) |
| **Backend Developer** | Ihsan | Laravel API, Database, Validation, Testing |

---

## 🛠️ Tech Stack

### Backend
- **Framework:** Laravel 13
- **PHP:** 8.4 NTS
- **Database:** MySQL 8.0.30
- **Cache:** Redis 7.0 (optional)
- **Queue:** Database driver
- **Auth:** Laravel Sanctum
- **Validation:** Form Request
- **Testing:** PHPUnit

### Frontend (MVP)
- **Templating:** Blade
- **Components:** Livewire 3
- **Styling:** Tailwind CSS 4
- **JavaScript:** Alpine.js
- **Build:** Vite 5

### Frontend (Phase 2)
- **Framework:** Next.js 14
- **Language:** TypeScript
- **Styling:** Tailwind CSS 4
- **State:** Zustand / React Context

### Infrastructure
- **Local Dev:** Laragon 6.0
- **Production:** Nginx + PHP-FPM
- **SSL:** Let's Encrypt
- **Storage:** Local / S3-compatible
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
├── nama (X-A, XI-IPA-1, dll)
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
├── foto (URL ke object storage)
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
- Policy untuk setiap resource
- Middleware untuk route protection

### Data Protection
- Input validation
- SQL injection prevention (Eloquent)
- Mass assignment protection ($fillable)
- Rate limiting untuk API

---

## 📈 Success Metrics

### Development Metrics
- Sprint velocity consistency
- Code coverage > 70%
- PR review time < 24 jam
- Bug rate < 5%

### Business Metrics
- Presensi accuracy > 95%
- System uptime > 99%
- User satisfaction > 4.0/5.0
- Admin efficiency (time saved)

---

## 🚀 Deployment Plan

### Staging
- URL: `staging.smauiiyk.sch.id`
- Purpose: UAT, Testing
- Deploy: Setiap merge ke main

### Production
- URL: `smauiiyk.sch.id`
- Purpose: Live users
- Deploy: End of sprint (2 minggu)

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
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev