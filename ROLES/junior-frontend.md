# Junior Frontend Developer

> Role untuk Fathan — fokus pada InertiaJS 3 + React 19 + TypeScript 5.7 + Tailwind CSS 4 + Vite 8.
> Learning path: 8 minggu menuju kemandirian.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `junior-frontend` |
| **Dibuat** | 2026-06-25 (revisi 2026-06-30) |
| **Maintainer** | Sandikodev |
| **Level** | Junior |

---

## Ringkasan

Junior Frontend Developer bertanggung jawab mengimplementasikan UI/UX menggunakan InertiaJS 3, React 19, TypeScript, Tailwind CSS 4, dan Vite 8. Semua kode frontend ditulis dalam **TypeScript** (`.tsx`). Bekerja di bawah supervisi Sandikodev dengan pendampingan harian dari Azis (Learning Mentor). Target mandiri di akhir minggu ke-8.

---

## Tanggung Jawab

### 1. Frontend Development (60%)
- InertiaJS pages — menggunakan `Inertia::render()` dari Laravel controller
- React 19 functional components dengan hooks (useState, useEffect, useCallback, custom hooks)
- TypeScript — type safety untuk props, state, events, API responses
- Tailwind CSS 4 styling — responsive, mobile-first
- Vite 8 — hot module replacement, build optimization
- Form handling — Inertia form helper, validation display
- Loading states, empty states, error states untuk setiap komponen

### 2. Bug Fixing & Maintenance (20%)
- Fix UI bugs (cross-browser, responsive)
- TypeScript type errors
- Performance optimization (React.memo, lazy loading, code splitting via Vite)
- Aksesibilitas (WCAG basic — ARIA labels, keyboard navigation)

### 3. Testing & Documentation (10%)
- Unit test dengan Jest + React Testing Library
- Self-testing sebelum submit PR (TypeScript compile check, lint)
- Dokumentasi component (props interface, usage examples)

### 4. Learning & Growth (10%)
- Ikuti learning path 8 minggu (dengan Azis sebagai discussion partner)
- Pair programming 2x/minggu (bergantian dengan Azis dan Sandikodev)
- Code review feedback implementation

---

## AI Instructions

### Konteks Role
Saya adalah **Junior Frontend Developer** di PT Koneksi Jaringan Indonesia. Saya bekerja dengan InertiaJS 3, React 19, TypeScript 5.7, Tailwind CSS 4, dan Vite 8. Saya perlu AI untuk membantu saya menulis kode frontend yang type-safe, clean, responsive, dan accessible.

### Cara AI Harus Membantu
1. **Tulis komponen React idiomatis** — Functional component dengan hooks. Hindari class component. Gunakan TypeScript interface untuk props.
2. **TypeScript strict** — Setiap fungsi, variable, props harus memiliki tipe. Jangan gunakan `any` kecuali darurat.
3. **Mobile-first responsive** — Setiap komponen harus dimulai dari mobile layout dulu, lalu scale up ke desktop dengan Tailwind breakpoints (`sm:`, `md:`, `lg:`, `xl:`).
4. **Jelaskan sebelum kode** — Saat memberi solusi, jelaskan dulu konsepnya secara singkat, baru kode. Saya sedang belajar.
5. **UX awareness** — Ingatkan tentang loading state, empty state, error state, dan success state untuk setiap komponen.
6. **Inertia best practices** — Gunakan `useForm`, `usePage`, `Link`, `router` dari Inertia. Jangan fetch manual kecuali untuk API external.
7. **Self-review prompt** — Setelah kode selesai, AI harus tanya: "TypeScript sudah aman? Loading state? Error handling? Responsive sudah?"

### Constraints
- Jangan commit `console.log()` atau `debugger` — hapus sebelum commit
- Jangan hardcode warna, spacing, font — gunakan Tailwind utility classes atau theme variables
- Jangan skip responsive testing (mobile first)
- Jangan copy-paste komponen tanpa memahami cara kerjanya
- Jangan gunakan `any` di TypeScript — buat interface/type yang proper
- Jangan gunakan jQuery — pakai React state + hooks

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (core.git) | write (branch) | Frontend ada di `resources/js/` (Inertia + React) |
| GitHub (aksesekolah.git) | read-only | Dokumentasi & monorepo |
| GitHub Issues | create, comment | Assign sendiri issue |
| Trello (Sprint Board) | view, comment | Update status card |
| Environment (local) | full | Laragon, Bun, Vite, PostgreSQL |
| Environment (staging) | view, operate | Test hasil deploy |

---

## Output yang Diharapkan

- Halaman/komponen React sesuai wireframe & acceptance criteria
- TypeScript strict — zero `any` type
- Responsive di mobile, tablet, desktop (mobile-first)
- Loading state, empty state, error state terhandle
- PR dengan self-review checklist tercentang (termasuk TypeScript compile check)
- Learning journal di `.openkb/PERSONAL/fathan/sessions/`

---

## Learning Path

```
Week 1-2: Git, GitHub, TypeScript dasar (tipe, interface, generic), React hooks (useState, useEffect)
Week 3-4: InertiaJS (routing, form, shared data), Tailwind CSS 4, responsive design
Week 5-6: React advanced (context, useReducer, custom hooks), state management, API integration
Week 7-8: Testing (Jest + RTL), performance optimization, deployment preview
```

Target: Level 3 "Independent Developer" di akhir minggu ke-8.

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Junior Frontend | - |
| Next (Month 3) | Mid Frontend | Inertia + React mastery, TypeScript advanced, testing, state management |
| Next (Year 1) | Senior Frontend | Architecture, design system, mentoring junior |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Junior Backend (Ihsan) | API contract & integration via Inertia |
| Learning Mentor (Azis) | Diskusi teknis, debugging, pair programming |
| Project Manager (Sandikodev) | UI/UX review, code review final |
| Product Analyst (Hanif) | Wireframe review, UAT support |

---

## Contoh Penggunaan di opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/fathan/profile.md",
    "~/.openkb/ROLES/junior-frontend.md"
  ]
}
```

---

*Adapted from [team-roles.md](../docs/01-getting-started/team-roles.md).*
