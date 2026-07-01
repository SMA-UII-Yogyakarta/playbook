# ADR 005: Porting Strategy — Monolith (Inertia) → API + Multi Client

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

SMART Absen dibangun dalam dua fase arsitektur:

- **Fase 1 (MVP):** Laravel monolith dengan InertiaJS + React — satu codebase untuk backend dan frontend
- **Fase 2 (Dedicated Backend):** Laravel API-only — backend terpisah dari frontend, melayani multiple client (Next.js webapp, React Native / Flutter mobile, SIAD, sistem eksternal)

Keputusan ini mendokumentasikan strategi porting agar transisi dari Fase 1 ke Fase 2 berjalan mulus tanpa rewrite.

## Decision

### Service Layer Pattern

Seluruh business logic ditulis di `app/Services/` sejak Fase 1, bukan di controller:

```
app/Services/
├── AuthService.php          → Login, register, SSO
├── PresensiService.php      → Check-in, geolokasi, swafoto
├── IzinService.php          → Pengajuan izin, approval
├── LaporanService.php       → Generate laporan, export
├── SiswaService.php         → CRUD siswa, import
├── GuruService.php          → CRUD guru, assign
└── KelasService.php         → CRUD kelas, wali kelas
```

**Mengapa Service Layer?**
- Controller (Inertia maupun API) hanya memanggil service — tidak berisi logic
- Saat porting ke Fase 2, cukup buat API controller baru yang panggil service yang sama
- Service bisa di-test secara independen tanpa mocking HTTP

### Dua Jenis Controller Sejak Fase 1

```
app/Http/Controllers/
├── Web/                    ← Controller untuk Inertia pages
│   ├── AuthController.php
│   ├── PresensiController.php
│   └── DashboardController.php
│
├── Api/                    ← Controller untuk API endpoints
│   ├── AuthController.php
│   ├── PresensiController.php
│   └── LaporanController.php
│
└── Services/              ← (link ke app/Services)

routes/
├── web.php                 ← Inertia routes
└── api.php                 ← Sanctum-protected API routes
```

**Mengapa dua controller sejak awal?**
- API routes tetap aktif meski Inertia dipakai sebagai frontend utama
- Mobile app bisa testing endpoint API sejak Sprint 2 (walau pakai Postman dulu)
- Tidak ada "big bang migration" — API sudah ada dan teruji saat Next.js siap

### Porting Matrix

| Komponen | Fase 1 (Inertia) | Fase 2 (API-only) | Action |
|----------|-----------------|-------------------|--------|
| **Service Layer** | `app/Services/*` | Sama, tidak berubah | ✅ **Zero change** |
| **Models** | `app/Models/*` | Sama, tidak berubah | ✅ **Zero change** |
| **Migrations** | `database/migrations/*` | Sama, tidak berubah | ✅ **Zero change** |
| **Web Controllers** | `app/Http/Controllers/Web/*` | Hapus/tidak aktif | ⚠️ Remove |
| **API Controllers** | `app/Http/Controllers/Api/*` | Sama, tetap aktif | ✅ **Zero change** |
| **Inertia Pages** | `resources/js/Pages/*` | Pindah ke Next.js | 🔄 Migrate |
| **React Components** | `resources/js/Components/*` | Pindah ke Next.js | 🔄 Migrate |
| **Sanctum Auth** | Session mode | Token mode | 🔄 Switch mode |
| **Spatie RBAC** | Sama | Sama | ✅ **Zero change** |
| **Routes web.php** | Inertia routes | Hapus | ⚠️ Remove |
| **Routes api.php** | API routes | API routes (sama) | ✅ **Zero change** |

### Trigger Porting

Porting ke Fase 2 dilakukan ketika SATU atau LEBIH kondisi berikut terpenuhi:

1. **Tim frontend dedicated** — Ada developer khusus frontend yang tidak handle backend
2. **Mobile development dimulai** — React Native / Flutter membutuhkan API endpoint stabil
3. **Performance requirement** — Inertia server rendering tidak mencukupi (concurrent users > 500)
4. **Third-party integration** — SIAD atau sistem eksternal perlu akses API
5. **Team size > 5** — Separation of concern menjadi kebutuhan

### Porting Step-by-Step

```
Fase 2 Porting Plan (estimasi: 1-2 sprint / 1-2 minggu)

Sprint N:
  ├── Buat Next.js project + copy komponen React dari resources/js
  ├── Setup Sanctum token auth di API
  ├── Update CORS untuk allow Next.js origin
  └── Deploy Next.js ke Vercel / Cloudflare Pages

Sprint N+1:
  ├── Testing parity: Inertia pages vs Next.js pages
  ├── Deprecate web.php routes
  ├── Update deployment pipeline
  └── Documentation update
```

### Risk Mitigation

| Risk | Impact | Mitigation |
|------|--------|------------|
| Service Layer tidak dipakai konsisten | High | Code review wajib: controller hanya memanggil service |
| API controller tidak ter-test | Medium | Tulis API controller bersamaan dengan Web controller |
| React components beda framework | Medium | Hindari Inertia-specific API di komponen React (pakai tanstack-query) |
| Sanctum session-to-token migration | Low | Sanctum support dual mode sejak awal |

## Consequences

### Pros
- **Zero rewrite** — Komponen React, service, model, migration semua reuse
- **Gradual migration** — Bisa per fitur, bukan big bang
- **API sudah ada sejak MVP** — Mobile development tidak blocked
- **Risk rendah** — Tim sudah familiar dengan codebase yang sama

### Cons
- **Double controller** — Maintenance overhead (Web + API controller untuk fitur yang sama)
- **Service Layer butuh disiplin** — Harus di-code review agar tidak ada logic di controller
- **Inertia-specific code** — Beberapa kode (Inertia::render, form helper) hanya di Web controller

---

**Last Updated:** 2026-06-30
