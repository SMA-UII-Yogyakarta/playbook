# Learning Resources — SMART Absen SMAUII

> Panduan belajar terstruktur untuk tim development SMART Absen.

---

## 📚 Kurikulum Utama — OpenKB for Junior

Tim menggunakan **[openkb-for-junior](https://github.com/konxc/openkb-for-junior)** sebagai kurikulum belajar utama. Repo ini berisi **15 fase** pembelajaran Laravel dari nol sampai siap kerja.

### Cara Mengakses

```bash
# Clone kurikulum
git clone git@github.com:konxc/openkb-for-junior.git
cd openkb-for-junior
```

**Struktur:**
```
openkb-for-junior/
├── journey/                    ← Kurikulum utama (15 fase)
│   ├── 00-CURRICULUM.md        ← Peta belajar induk
│   ├── FASE-01-FONDASI-MUTLAK/ ← Programming dasar
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
└── PRAKTIK-CODING/             ← Latihan praktik
```

---

## 🎯 Learning Path Per Role

### Fathan — Junior Frontend Developer

**Fokus:** Frontend track dengan InertiaJS + React 19 + TypeScript

| Fase | Topik | Estimasi | Prioritas |
|------|-------|----------|-----------|
| 01 | Fondasi Mutlak | 1-2 minggu | ✅ Wajib |
| 02 | PHP Fundamental | 2-3 minggu | ✅ Wajib |
| 03 | OOP | 2-3 minggu | ✅ Wajib |
| 05 | Web Fundamental | 2 minggu | ✅ Wajib |
| 06 | Laravel Deep Dive | 4-6 minggu | ✅ Wajib |
| 09 | Frontend di Laravel | 1-2 minggu | ✅ **Fokus utama** |
| 11 | Tools & Workflow | 1-2 minggu | ✅ Wajib |

**Dokumen Kunci:**
- `FASE-09/09-01-cara-kerja-vite.md`
- `FASE-09/09-02-tailwind-css.md`
- `FASE-09/09-06-inertiajs-dan-react.md` (jika ada)
- `FASE-09/09-05-hot-reload-hmr.md`
- React + TypeScript official docs

**Tambahan Materi:**
- [React 19 Documentation](https://react.dev/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/)
- [InertiaJS Documentation](https://inertiajs.com/)
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro)

**Target Sprint 1:**
- US-005: Halaman login (React + Inertia + Tailwind)
- Integrasi dengan backend Sanctum via Inertia

---

### Ihsan — Junior Backend Developer

**Fokus:** Backend track dengan Laravel Sanctum & Database

| Fase | Topik | Estimasi | Prioritas |
|------|-------|----------|-----------|
| 01 | Fondasi Mutlak | 1-2 minggu | ✅ Wajib |
| 02 | PHP Fundamental | 2-3 minggu | ✅ Wajib |
| 03 | OOP | 2-3 minggu | ✅ Wajib |
| 05 | Web Fundamental | 2 minggu | ✅ Wajib |
| 06 | Laravel Deep Dive | 4-6 minggu | ✅ **Fokus utama** |
| 07 | Database & SQL | 2 minggu | ✅ **Fokus utama** |
| 08 | Design Pattern | 2-3 minggu | ✅ Wajib |
| 11 | Tools & Workflow | 1-2 minggu | ✅ Wajib |

**Dokumen Kunci:**
- `FASE-06/06-03-routing-web-php.md`
- `FASE-06/06-04-controller-dan-request.md`
- `FASE-06/06-05-model-dan-eloquent-orm.md`
- `FASE-06/06-07-middleware-dan-auth.md`
- `FASE-06/06-08-service-layer.md`
- `FASE-07/07-03-relationship-dan-join.md`
- `FASE-07/07-06-n-plus-one-problem.md`

**Target Sprint 1:**
- US-001: Login dengan Sanctum token
- US-002: Logout + revoke token
- US-003: RBAC middleware
- US-004: Session management

---

### Azis — Learning Mentor / Technical Guide

**Fokus:** Menguasai seluruh stack untuk mentoring

| Fase | Topik | Estimasi | Prioritas |
|------|-------|----------|-----------|
| 01-05 | Fondasi (review) | 1-2 minggu | ⚡ Review cepat |
| 06 | Laravel Deep Dive | 2-3 minggu | ✅ Wajib |
| 07 | Database & SQL | 1-2 minggu | ✅ Wajib |
| 08 | Design Pattern | 1-2 minggu | ✅ Wajib |
| 09 | Frontend di Laravel | 1 minggu | ⚡ Overview |
| 10 | Infrastruktur & Deployment | 2 minggu | ✅ **Fokus utama** |
| 11 | Tools & Workflow | 1 minggu | ✅ Wajib |
| 12 | Testing & QA | 1-2 minggu | ✅ Wajib |

**Dokumen Kunci:**
- `FASE-10/10-03-laragon-di-windows.md`
- `FASE-10/10-05-ssh-dan-terminal.md`
- `FASE-10/10-06-docker-dasar.md`
- `FASE-11/11-04-artisan-cli.md`
- `FASE-11/11-05-tinker-dan-repl.md`
- `laravel-telescope.md`
- `laragon-vs-artisan-serve.md`

**Tanggung Jawab:**
- Fasilitasi environment setup (Laragon, database, Node.js)
- Debugging session (Telescope, log reading, Tinker)
- Concept explanation (Laravel lifecycle, middleware, Eloquent)
- Code review awal sebelum submit ke PM/Senior

---

### Hanif — Product Analyst

**Fokus:** Understanding technical constraints & possibilities

| Fase | Topik | Estimasi | Prioritas |
|------|-------|----------|-----------|
| 01 | Fondasi Mutlak | 1 minggu | ⚡ Overview |
| 05 | Web Fundamental | 1 minggu | ✅ Wajib |
| 06 | Laravel Deep Dive | 2 minggu | ⚡ Overview |
| 15 | Bisnis & Industri | 1 minggu | ✅ Wajib |

**Dokumen Kunci:**
- `FASE-05/05-01-cara-kerja-web.md`
- `FASE-05/05-02-http-dan-rest.md`
- `FASE-06/06-02-arsitektur-laravel.md`
- `FASE-15/15-01-web-industri-ekosistem.md`
- `FASE-15/15-02-dari-kode-ke-produk.md`
- `FASE-15/15-03-peran-tim-pengembang.md`

**Target:**
- Memahami technical feasibility fitur
- Mapping requirement → technical implementation
- Komunikasi efektif dengan dev team

---

## 🛠️ Tools & Environment

### Development Stack (Laragon 6.0)

| Tool | Versi | Path |
|------|-------|------|
| PHP | 8.4.22 NTS | `C:\laragon\bin\php\php-8.4.22-nts-Win32-vs17-x64\` |
| Apache | 2.4.54 | `C:\laragon\bin\apache\` |
| PostgreSQL | 16 | `C:\laragon\bin\postgresql\postgresql-16.x-winx64\` |
| Node.js | 22.14.0 | `C:\laragon\bin\nodejs\` |
| **Bun** | latest | `C:\Users\<user>\.bun\bin\bun.exe` |
| Composer | latest | `C:\laragon\bin\composer\composer.phar` |
| Redis | 5.0.14.1 | `C:\laragon\bin\redis\` |

**Setup Guide:**
- [`02-lingkungan-development.md` (aksesekolah)](https://github.com/SMA-UII-Yogyakarta/aksesekolah/blob/main/docs/02-lingkungan-development.md)
- [OpenKB FASE-10: Laragon di Windows](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-10-INFRASTRUKTUR-DAN-DEPLOYMENT/10-03-laragon-di-windows.md)

---

## 📖 Cara Belajar Efektif

### Metode 1: Belajar Berurutan (Rekomendasi)

1. Buka `journey/00-CURRICULUM.md` — pahami peta belajar
2. Mulai dari `FASE-01/01-01-apa-itu-pemrograman.md`
3. Setiap dokumen punya bagian **Latihan** — kerjakan!
4. Setelah beberapa fase, buka `PRAKTIK-CODING/` untuk latihan langsung
5. Lanjut ke fase berikutnya

### Metode 2: Belajar Per Topik

| Butuh | Buka |
|-------|------|
| Paham MVC di Laravel | `FASE-08/08-02-mvc-architecture.md` |
| Cara kerja Eloquent | `FASE-06/06-05-model-dan-eloquent-orm.md` |
| Deploy ke hosting | `FASE-10/10-07-cpanel-dan-hosting.md` |
| Persiapan interview | `FASE-14/14-06-pertanyaan-interview-laravel.md` |

### Metode 3: Belajar Sambil Praktek

Setelah membaca beberapa fase, langsung praktek di `PRAKTIK-CODING/`:
- `latihan-01` — Variabel dan tipe data ⚡
- `latihan-02` — Loop dan kondisi ⚡
- `latihan-03` — Class sederhana
- `latihan-04` — Routing dan controller ⚡
- `latihan-05` — Eloquent query ⚡
- `latihan-06` — Membuat fitur CRUD ⚡
- `latihan-07` — Integrasi API payment
- `capstone` — Buat fitur sederhana ⚡

---

## 🧪 Progress Tracking

Progress belajar di-track di **Trello board** [`SMART ABSEN SMAUII`](https://trello.com/b/BHXA6ZcR/smart-absen-smauii).

**List:** `📚 Learning Path (Azis)`

Setiap anggota tim punya card dengan:
- Checklist fase yang harus diselesaikan
- Link ke dokumen openkb-for-junior
- Status progress (To Do / In Progress / Done)
- Diskusi & blocker di comments

---

## 📞 Mentor & Support

| Role | Person | Scope |
|------|--------|-------|
| **Learning Mentor** | Azis | Environment, debugging, concept explanation |
| **Project Manager** | Sandikodev | Code review final, sprint planning, merge PR |
| **Senior Developer** | Sandikodev | Architecture decision, technical guidance |

**Cara Minta Bantuan:**
1. Coba baca dokumentasi openkb-for-junior dulu
2. Jika masih stuck, tanya di Trello card (comment) atau Discord/WhatsApp
3. Untuk debugging, siapkan: error message, log, screenshot

---

## 📊 Estimasi Timeline

| Minggu | Aktivitas |
|--------|-----------|
| 1-2 | **Sprint 1 — Setup:** Sinkronisasi docs, instalasi (Bun, NeonDB, PostgreSQL), setup Sanctum & Spatie. Fathan: React dasar + TypeScript. Ihsan: Laravel Service Layer + PostgreSQL. Azis: Onboarding + fasilitasi setup |
| 3-4 | **Sprint 2 — Auth:** Login/register Sanctum, RBAC Spatie, halaman profile (React+Inertia). Fathan: InertiaJS + React hooks. Ihsan: API Sanctum, Spatie middleware |
| 5-6 | **Sprint 3 — Presensi:** Presensi dengan geolokasi, swafoto. Fathan: React advanced. Ihsan: API presensi, upload foto |
| 7-8 | **Sprint 4 — Laporan:** Laporan presensi, admin panel, UAT. Review & final assessment |

**Catatan:** Timeline fleksibel — yang penting **pahami konsep** sebelum lanjut.

---

## 🔗 Referensi Eksternal

| Resource | Deskripsi |
|----------|-----------|
| [Laravel Documentation](https://laravel.com/docs) | Official docs — always up to date |
| [Laracasts](https://laracasts.com) | Video tutorials (free + paid) |
| [PHP The Right Way](https://phptherightway.com) | Best practices PHP |
| [Stack Overflow](https://stackoverflow.com/questions/tagged/laravel) | Q&A community |

---

<p align="center">
  <b>Belajar itu proses seumur hidup — nikmati setiap langkahnya! 🚀</b><br>
  <i>"The expert in anything was once a beginner."</i>
</p>