# ADR 002-v2: InertiaJS + React Sejak MVP

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev  
**Supersedes:** [ADR-002](002-livewire-first.md)

---

## Context

Keputusan awal (ADR-002) memilih Livewire 3 untuk MVP dengan alasan learning curve rendah dan development cepat. Setelah evaluasi lebih lanjut, tim memutuskan revisi karena:

1. **Arahan stakeholder (Pak Mahfud)** — menginginkan aplikasi modern dengan arsitektur yang bisa diport ke mobile (React Native / Flutter) dan webapp terpisah (Next.js) di masa depan.
2. **Tim composition berubah** — Azis bergabung sebagai Learning Mentor, memungkinkan Fathan & Ihsan belajar React/TypeScript lebih cepat dengan pendampingan langsung.
3. **Porting cost** — Membangun dengan Livewire lalu migrasi ke React/Next.js di Fase 2 membutuhkan rewrite frontend total. Memulai dengan Inertia+React menghilangkan biaya porting.
4. **Ecosystem maturity** — InertiaJS 3 + React 19 + TypeScript 5.7 sudah stabil dan mature untuk production.

## Decision

**Fase 1 (MVP):** InertiaJS 3 + React 19 + TypeScript 5.7 + Tailwind CSS 4 + Vite 8  
**Fase 2 (Dedicated Backend):** Laravel API-only + Next.js (Web App) + React Native / Flutter (Mobile)

### Arsitektur Fase 1

```
Browser
  │
  ├── InertiaJS 3 (bridge)
  │     ├── Server-side: Laravel routing + controller
  │     └── Client-side: React 19 + TypeScript
  │
  ├── Tailwind CSS 4 (styling)
  ├── Vite 8 (bundler)
  └── Bun (package manager)
```

### Service Layer Pattern
Seluruh business logic ditulis di `app/Services/` agar:
- Controller tetap tipis — tinggal panggil service
- API routes (`/api/*`) bisa reuse service yang sama
- Porting ke Fase 2 tinggal ganti controller → API controller

## Rationale

### Kenapa Inertia + React, Bukan Livewire?

| Aspek | Livewire 3 | InertiaJS + React |
|-------|-----------|-------------------|
| **Learning curve** | Rendah (Blade familiar) | Sedang (React baru) |
| **Porting ke Next.js** | Rewrite total | Partial (pindah routing) |
| **Type safety** | Tidak ada (Blade/PHP) | TypeScript penuh |
| **Component reusability** | Terbatas di Laravel | Bisa share dengan Next.js |
| **Mobile API reuse** | Tidak langsung | Langsung (service layer) |
| **Ecosystem** | Laravel-centric | React universal |

### Kenapa React, Bukan Vue/Nuxt?

1. **Market dominance** — React paling banyak dipakai → lebih mudah cari referensi, library, hiring
2. **InertiaJS first-class support** — InertiaJS dibuat oleh creator Laravel, dukungan React setara dengan Vue
3. **Mobile pathway** — React Native adalah pilihan mobile yang paling natural dari React
4. **Tim preference** — Sandikodev dan Azis lebih familiar React daripada Vue

### Kenapa TypeScript dari Awal?

1. **Type safety** — Mencegah error runtime yang umum di JS (undefined is not a function, wrong prop types)
2. **IDE support** — Autocomplete, refactoring, type checking di VS Code
3. **Learning investment** — Fathan & Ihsan belajar TypeScript sejak awal, bukan migrasi nanti
4. **Next.js readiness** — Next.js berbasis TypeScript secara default

## Consequences

### Pros
- Zero rewrite ketika porting ke Next.js / React Native — reuse komponen React
- Service layer bisa dipakai oleh API routes dan Inertia controller
- TypeScript memberikan safety net untuk junior developer
- Vite 8 memberikan HDR (Hot Data Replacement) untuk React

### Cons
- Learning curve lebih tinggi untuk Fathan & Ihsan (harus belajar React + TS + Inertia)
- InertiaJS menambah satu layer abstraksi (dibanding Livewire langsung Blade)
- Development lebih lambat di awal karena learning phase

### Mitigation
- Azis sebagai Learning Mentor akan melakukan pair programming dengan Fathan & Ihsan
- Sprint 1 difokuskan untuk setup dan learning, bukan feature building
- Learning path disesuaikan: React hooks dulu, Inertia nanti

---

**Last Updated:** 2026-06-30
