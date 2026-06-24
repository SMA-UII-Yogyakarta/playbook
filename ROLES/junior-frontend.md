# Junior Frontend Developer

> Role untuk Fathan — fokus pada Livewire, Blade, Tailwind CSS, dan nanti React/Next.js.
> Learning path: 8 minggu menuju kemandirian.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `junior-frontend` |
| **Dibuat** | 2026-06-25 |
| **Maintainer** | Sandikodev |
| **Level** | Junior |

---

## Ringkasan

Junior Frontend Developer bertanggung jawab mengimplementasikan UI/UX menggunakan Livewire 3, Blade, Tailwind CSS 4, Alpine.js, dan Vite. Ke depannya akan migrate ke React/Next.js. Bekerja di bawah supervisi Sandikodev dengan target mandiri di akhir minggu ke-8.

---

## Tanggung Jawab

### 1. Frontend Development (60%)
- Livewire components (full-page, nested, modal)
- Blade templates dengan layouting
- Tailwind CSS styling responsive
- Alpine.js interaktivitas client-side
- Vite asset bundling

### 2. Bug Fixing & Maintenance (20%)
- Fix UI bugs (cross-browser, responsive)
- Performance optimization (lazy loading, caching)
- Aksesibilitas (WCAG basic)
- A/B testing untuk UX improvement

### 3. Testing & Documentation (10%)
- Self-testing sebelum submit PR
- Dokumentasi component (props, slots, events)
- Responsive testing (mobile, tablet, desktop)

### 4. Learning & Growth (10%)
- Ikuti learning path 8 minggu
- Pair programming 2x/minggu
- Code review feedback implementation

---

## AI Instructions

### Konteks Role
Saya adalah **Junior Frontend Developer** di PT Koneksi Jaringan Indonesia. Saya bekerja dengan Livewire 3, Blade, Tailwind CSS 4, Alpine.js, dan Vite. Saya perlu AI untuk membantu saya menulis kode frontend yang clean, responsive, dan accessible.

### Cara AI Harus Membantu
1. **Tulis kode Livewire + Blade yang idiomatis** — Gunakan component, layout, slot. Hindari logic berat di Blade.
2. **Mobile-first responsive** — Setiap komponen harus dimulai dari mobile layout dulu, lalu scale up ke desktop.
3. **Jelaskan sebelum kode** — Saat memberi solusi, jelaskan dulu konsepnya secara singkat, baru kode. Saya sedang belajar.
4. **UX awareness** — Ingatkan tentang loading state, empty state, error state, dan success state.
5. **Bahasa campuran** — Kode dan komentar teknis dalam bahasa Inggris, penjelasan konsep dalam bahasa Indonesia
6. **Self-review prompt** — Setelah kode selesai, AI harus tanya: "Sudah responsive? Loading state? Error handling?"

### Constraints
- Jangan commit `console.log()` atau `dd()` — hapus sebelum commit
- Jangan hardcode warna, spacing, font — gunakan Tailwind utility classes atau CSS custom properties
- Jangan skip responsive testing
- Jangan copy-paste komponen tanpa memahami cara kerjanya
- Jangan gunakan jQuery — pakai Alpine.js atau Vanilla JS

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (core.git) | write (branch) | Frontend ada di core (Livewire + Blade) |
| GitHub (aksesekolah.git) | read-only | Dokumentasi & monorepo |
| GitHub Issues | create, comment | Assign sendiri issue |
| Trello (Sprint Board) | view, comment | Update status card |
| Environment (local) | full | Laragon, Node.js, Vite |
| Environment (staging) | view, operate | Test hasil deploy |

---

## Output yang Diharapkan

- Halaman/komponen sesuai wireframe & acceptance criteria
- Responsive di mobile, tablet, desktop
- Loading state, empty state, error state terhandle
- PR dengan self-review checklist tercentang
- Learning journal di `.openkb/PERSONAL/fathan/sessions/`

---

## Learning Path

```
Week 1-2: Git, GitHub, Livewire basics (component, rendering, validation)
Week 3-4: Tailwind CSS, Alpine.js, Vite, responsive design
Week 5-6: React fundamentals (JSX, state, props, hooks)
Week 7-8: Next.js routing, SSR, API integration
```

Target: Level 3 "Independent Developer" di akhir minggu ke-8.

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Junior Frontend | - |
| Next (Month 3) | Mid Frontend | React/Next.js mastery, state management, testing |
| Next (Year 1) | Senior Frontend | Architecture, design system, mentoring |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Junior Backend (Ihsan) | API integration, data flow |
| Project Manager (Sandikodev) | UI/UX review, code review |
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
