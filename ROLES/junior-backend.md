# Junior Backend Developer

> Role untuk Ihsan — fokus pada Laravel 13, PostgreSQL/NeonDB, Sanctum, Spatie Permission, Service Layer.
> Learning path: 8 minggu menuju kemandirian.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `junior-backend` |
| **Dibuat** | 2026-06-25 (revisi 2026-06-30) |
| **Maintainer** | Sandikodev |
| **Level** | Junior |

---

## Ringkasan

Junior Backend Developer bertanggung jawab mengimplementasikan API endpoint, database migration & seeder, validation, business logic (Service Layer), authentication (Sanctum), dan RBAC (Spatie Permission) menggunakan Laravel 13 dengan PostgreSQL/NeonDB. Bekerja di bawah supervisi Sandikodev dengan pendampingan harian dari Azis (Learning Mentor). Target mandiri di akhir minggu ke-8.

---

## Tanggung Jawab

### 1. Backend Development (60%)
- Laravel API endpoint (Inertia controller di `Controllers/Web/` + API controller di `Controllers/Api/`)
- **Service Layer pattern** — business logic di `app/Services/`, controller hanya memanggil service
- Eloquent model & relationship (PostgreSQL syntax — JSONB untuk metadata, array untuk multiple values)
- Database migration & seeder (PostgreSQL native types)
- Form Request validation
- Laravel Sanctum (token management, session auth)
- Spatie Laravel Permission (role & permission assignment, middleware)

### 2. Database Management (20%)
- PostgreSQL query optimization (eager loading, chunk, cursor, explain analyze)
- Indexing untuk query sering (B-tree, GIN untuk JSONB)
- Data integrity & constraint (CHECK constraint, FOREIGN KEY, UNIQUE)
- NeonDB branching untuk preview deployment
- Backup & restore testing (NeonDB point-in-time recovery)

### 3. Testing & Documentation (10%)
- Unit test (PHPUnit) — minimal 70% coverage
- Feature test untuk API endpoint
- API documentation (Postman/Insomnia/Stoplight)
- Self-testing sebelum submit PR

### 4. Learning & Growth (10%)
- Ikuti learning path 8 minggu (dengan Azis sebagai discussion partner)
- Pair programming 2x/minggu (bergantian dengan Azis dan Sandikodev)
- Code review feedback implementation

---

## AI Instructions

### Konteks Role
Saya adalah **Junior Backend Developer** di PT Koneksi Jaringan Indonesia. Saya bekerja dengan Laravel 13, PostgreSQL 16 (NeonDB), Laravel Sanctum, Spatie Permission, dan Service Layer architecture. Saya perlu AI untuk membantu saya menulis kode backend yang bersih, aman, dan sesuai standar.

### Cara AI Harus Membantu
1. **Tulis kode Laravel yang idiomatis** — Gunakan Eloquent, Form Request, Policy, Service Layer. Hindari raw query kecuali diperlukan.
2. **Service Layer pattern** — Logic di `app/Services/`, controller hanya memanggil method service. Jangan taruh logic di controller.
3. **PostgreSQL-aware** — Gunakan PostgreSQL features (JSONB, array, window functions) ketika relevan.
4. **Jelaskan sebelum kode** — Saat memberi solusi, jelaskan dulu konsepnya secara singkat, baru kode. Saya sedang belajar.
5. **Security first** — Selingi kode dengan reminder: "jangan lupa validasi", "ini rawan N+1", "ini perlu policy", "Sanctum token perlu ability".
6. **English-only** — All code, comments, and concept explanations in English
7. **Test-driven mindset** — Saat saya minta fitur, AI harus ingatkan: "Sudah siap test case-nya?" atau "Buat feature test dulu."
8. **Self-review prompt** — Setelah kode selesai, AI harus tanya: "Sudah self-review? Cek: validation? N+1? hardcode? Service Layer sudah sesuai?"

### Constraints
- Jangan commit `.env`, key, token, password ke git
- Jangan gunakan `DB::raw()` tanpa alasan jelas
- Jangan skip Form Request — validasi di Controller itu tidak boleh
- Jangan hardcode credentials atau konfigurasi environment
- Jangan taruh business logic di Controller — harus di Service Layer
- Jangan gunakan MySQL-specific syntax — pakai PostgreSQL-compatible

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (core.git) | write (branch) | Push branch fitur, buat PR |
| GitHub (aksesekolah.git) | read-only | Dokumentasi & monorepo |
| GitHub Issues | create, comment | Assign sendiri issue |
| Trello (Sprint Board) | view, comment | Update status card |
| Environment (local) | full | Laragon, PostgreSQL, Bun, Redis |
| Environment (staging) | view, operate | Test hasil deploy |
| NeonDB | read-write | Dashboard untuk monitor query, branching |

---

## Output yang Diharapkan

- API endpoint sesuai acceptance criteria
- Service Layer pattern — semua business logic di `app/Services/`
- Migration & seeder yang bisa di-revert (PostgreSQL compatible)
- Unit test coverage > 70%
- Sanctum authentication & Spatie RBAC terintegrasi
- PR dengan self-review checklist tercentang
- Learning journal di `.openkb/PERSONAL/ihsan/sessions/`

---

## Learning Path

```
Week 1-2: Git, GitHub, Laravel fundamentals, Service Layer concept
Week 3-4: Eloquent, Migration, Seeder, PostgreSQL specifics
Week 5-6: API Design, Sanctum, Spatie Permission, Form Request, Testing
Week 7-8: Advanced — Queue, Event, Job, NeonDB deployment, Performance
```

Target: Level 3 "Independent Developer" di akhir minggu ke-8.

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Junior Backend | - |
| Next (Month 3) | Mid Backend | Laravel advanced, PostgreSQL optimization, API design, Service Layer mastery |
| Next (Year 1) | Senior Backend | Architecture, mentoring, code review, multi-tenant design |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Junior Frontend (Fathan) | API contract, Inertia data flow, integration testing |
| Learning Mentor (Azis) | Diskusi teknis, debugging, pair programming |
| Project Manager (Sandikodev) | Technical clarification, code review final |
| Product Analyst (Hanif) | Requirement clarification, UAT support |

---

## Contoh Penggunaan di opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/ihsan/profile.md",
    "~/.openkb/ROLES/junior-backend.md"
  ]
}
```

---

*Adapted from [team-roles.md](../docs/01-getting-started/team-roles.md).*
