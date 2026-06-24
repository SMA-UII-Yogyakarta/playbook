# Junior Backend Developer

> Role untuk Ihsan — fokus pada Laravel, API, database, dan logic backend.
> Learning path: 8 minggu menuju kemandirian.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `junior-backend` |
| **Dibuat** | 2026-06-25 |
| **Maintainer** | Sandikodev |
| **Level** | Junior |

---

## Ringkasan

Junior Backend Developer bertanggung jawab mengimplementasikan API endpoint, database migration, seeder, validation, dan business logic menggunakan Laravel 13. Bekerja di bawah supervisi Sandikodev dengan target mandiri di akhir minggu ke-8.

---

## Tanggung Jawab

### 1. Backend Development (60%)
- Laravel API endpoints sesuai spesifikasi
- Eloquent model, relationship, scope
- Database migration & seeder
- Form Request validation
- Policy & authorization

### 2. Database Management (20%)
- Query optimization (eager loading, chunk, cursor)
- Indexing untuk query sering
- Data integrity & constraint
- Backup & restore testing

### 3. Testing & Documentation (10%)
- Unit test (PHPUnit) — minimal 70% coverage
- Self-testing sebelum submit PR
- API documentation (export Postman)

### 4. Learning & Growth (10%)
- Ikuti learning path 8 minggu
- Pair programming 2x/minggu
- Code review feedback implementation

---

## AI Instructions

### Konteks Role
Saya adalah **Junior Backend Developer** di PT Koneksi Jaringan Indonesia. Saya bekerja dengan Laravel 13, MySQL 8, dan Sanctum. Saya perlu AI untuk membantu saya menulis kode backend yang bersih, aman, dan sesuai standar.

### Cara AI Harus Membantu
1. **Tulis kode Laravel yang idiomatis** — Gunakan Eloquent, Form Request, Policy. Hindari raw query kecuali diperlukan.
2. **Jelaskan sebelum kode** — Saat memberi solusi, jelaskan dulu konsepnya secara singkat, baru kode. Saya sedang belajar.
3. **Security first** — Selingi kode dengan reminder: "jangan lupa validasi", "ini rawan N+1", "ini perlu policy"
4. **Bahasa campuran** — Kode dan komentar teknis dalam bahasa Inggris, penjelasan konsep dalam bahasa Indonesia
5. **Test-driven mindset** — Saat saya minta fitur, AI harus ingatkan: "Sudah siap test case-nya?"
6. **Self-review prompt** — Setelah kode selesai, AI harus tanya: "Sudah self-review? Cek: validation? N+1? hardcode?"

### Constraints
- Jangan commit `.env`, key, token, password ke git
- Jangan gunakan `DB::raw()` tanpa alasan jelas
- Jangan skip Form Request — validasi di Controller itu tidak boleh
- Jangan hardcode credentials atau konfigurasi environment

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (core.git) | write (branch) | Push branch fitur, buat PR |
| GitHub (aksesekolah.git) | read-only | Dokumentasi & monorepo |
| GitHub Issues | create, comment | Assign sendiri issue |
| Trello (Sprint Board) | view, comment | Update status card |
| Environment (local) | full | Laragon, MySQL, Node.js |
| Environment (staging) | view, operate | Test hasil deploy |

---

## Output yang Diharapkan

- API endpoint sesuai acceptance criteria
- Migration & seeder yang bisa di-revert
- Unit test coverage > 70%
- PR dengan self-review checklist tercentang
- Learning journal di `.openkb/PERSONAL/ihsan/sessions/`

---

## Learning Path

```
Week 1-2: Git, GitHub, Laravel fundamentals (routing, controller, blade)
Week 3-4: Eloquent, Migration, Seeder, Relationship
Week 5-6: API Design, Sanctum, Form Request, Policy
Week 7-8: Advanced — Queue, Event, Job, Testing
```

Target: Level 3 "Independent Developer" di akhir minggu ke-8.

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Junior Backend | - |
| Next (Month 3) | Mid Backend | Laravel advanced, performance optimization, API design |
| Next (Year 1) | Senior Backend | Architecture, mentoring, code review |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Junior Frontend (Fathan) | API contract, integration testing |
| Project Manager (Sandikodev) | Technical clarification, code review |
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
