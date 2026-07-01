# Junior Developer Learning Path

> Roadmap 8 minggu untuk Fathan (Frontend) & Ihsan (Backend) menjadi mandiri.
> Azis (Learning Mentor) sebagai discussion partner, debugging buddy, dan concept explainer.

---

## 🎯 Goal

Setelah 8 minggu:
- ✅ **Fathan** mampu develop fitur Inertia+React secara mandiri (TypeScript, hooks, state management, testing)
- ✅ **Ihsan** mampu develop fitur Laravel API secara mandiri (Service Layer, Sanctum, Spatie, PostgreSQL)
- ✅ Code quality sesuai standard (PSR-12, TypeScript strict, Laravel conventions)
- ✅ Proactive communication — tanya Azis dulu, eskalasi ke Sandikodev jika perlu
- ✅ Self-debugging capability — baca error message, cari solusi, tanya jika stuck > 30 menit

---

## 📊 Assessment Timeline

```
Week 0 → Baseline assessment (skill survey)
Week 4 → Mid-term assessment
Week 8 → Final assessment (independence level)
```

---

## 📅 Week 1-2: Git & TypeScript / Laravel Fundamentals

### Topics

#### Fathan — Frontend Track
```
✅ Git basics (clone, add, commit, push, pull, branch)
✅ Pull Request workflow + conventional commits
✅ TypeScript dasar: tipe data, interface, type alias, generic sederhana
✅ React hooks: useState, useEffect, props & state
✅ Functional component dengan TypeScript (props interface)
✅ JSX + Tailwind CSS 4 utility classes
```

#### Ihsan — Backend Track
```
✅ Git basics (clone, add, commit, push, pull, branch)
✅ Pull Request workflow + conventional commits
✅ Laravel fundamentals: routing, controller, request lifecycle
✅ Service Layer pattern: apa, kenapa, bagaimana
✅ Eloquent ORM: model, migration, seeder
✅ PostgreSQL basics: connect via Laragon, buat database, running migration
```

### Tasks

#### Fathan
```
- Clone repository core, setup Bun + Vite
- Buat branch: `feature/learning-frontend`
- Buat komponen React sederhana: Counter, Todo List (TypeScript)
- Implementasi Tailwind responsive (mobile-first)
- Commit & PR pertama
- Fix berdasarkan review (Azis → Sandikodev)
```

#### Ihsan
```
- Clone repository core, setup PostgreSQL + Laragon
- Buat branch: `feature/learning-backend`
- Buat migration: `create_books_table` (PostgreSQL syntax)
- Buat Model: `Book` + Seeder
- Buat Service: `BookService` → panggil dari controller
- CRUD: GET/POST/PUT/DELETE via web.php (Inertia)
- Commit & PR pertama
```

### Assessment

```markdown
## Week 2 Assessment

**Fathan:**
- [ ] Dapat clone + setup environment (Bun, Vite, Laragon)
- [ ] Paham Git workflow (branch, commit, PR)
- [ ] Dapat buat komponen React + TypeScript sederhana
- [ ] Paham useState, useEffect
- [ ] Dapat styling dengan Tailwind utility classes

**Ihsan:**
- [ ] Dapat clone + setup PostgreSQL di Laragon
- [ ] Paham Git workflow (branch, commit, PR)
- [ ] Dapat buat migration & seeder
- [ ] Paham Service Layer pattern
- [ ] Dapat buat CRUD dengan Eloquent
```

---

## 📅 Week 3-4: InertiaJS / Auth & RBAC

### Topics

#### Fathan — Frontend Track
```
✅ InertiaJS: Inertia::render, Link, useForm, usePage
✅ React hooks lanjutan: useCallback, useMemo, custom hooks
✅ TypeScript: generic, union type, type narrowing
✅ Form handling + validation display (error messages dari Laravel)
✅ Shared data via Inertia (app name, user, permissions)
```

#### Ihsan — Backend Track
```
✅ Laravel Sanctum: install, konfigurasi, token management
✅ Spatie Laravel Permission: install, role & permission seeder
✅ Form Request validation
✅ Middleware: auth:sanctum, role, permission
✅ PostgreSQL: JSONB untuk metadata, indexing, query optimization
```

### Tasks

#### Fathan
```
- Setup InertiaJS di core (resources/js/Pages/)
- Buat halaman Login (React + Inertia + Tailwind)
- Buat halaman Dashboard setelah login
- Implementasi form validation display
- Buat layout component (sidebar, navbar, content area)
- Responsive: mobile sidebar → desktop sidebar
```

#### Ihsan
```
- Install & setup Sanctum
- Install & setup Spatie Permission
- Buat migration users + roles + permissions
- Buat AuthService: login, register, logout
- Buat API + Web controller untuk auth
- Buat middleware: role:admin, permission:view-dashboard
- Unit test untuk auth endpoint
```

### Assessment

```markdown
## Week 4 Assessment (Mid-term)

**Fathan:**
- [ ] Paham InertiaJS: routing, form, shared data
- [ ] Dapat buat halaman login + dashboard
- [ ] Form validation display OK
- [ ] Responsive layout OK
- [ ] TypeScript type-safe

**Ihsan:**
- [ ] Sanctum login/register/logout working
- [ ] Spatie RBAC terintegrasi
- [ ] Service Layer pattern konsisten
- [ ] Form Request validation
- [ ] Unit test > 50% coverage
```

---

## 📅 Week 5-6: Presensi Module

### Topics

#### Fathan — Frontend Track
```
✅ React advanced: context API, useReducer, custom hooks
✅ Camera API: getUserMedia untuk swafoto
✅ Geolocation API: getCurrentPosition, watchPosition
✅ Image upload + preview
✅ Loading & error states pattern
✅ TypeScript: handling API response types
```

#### Ihsan — Backend Track
```
✅ API endpoint design untuk presensi
✅ Geolocation validation (latitude, longitude, radius)
✅ File upload handling (S3 Wasabi/MinIO)
✅ Rate limiting (throttle)
✅ Feature test untuk API
✅ PostgreSQL: JSONB untuk metadata presensi
```

### Tasks

#### Fathan
```
- Buat halaman Presensi (check-in form)
- Implementasi camera preview (swafoto)
- Implementasi geolocation (latitude, longitude)
- Form submission via Inertia
- Loading state, error state, success state
- Buat halaman Riwayat Presensi (table)
```

#### Ihsan
```
- Buat migration presensi (PostgreSQL)
- Buat PresensiService: check-in, riwayat, rekap
- Validasi geolokasi (radius dari sekolah)
- Upload swafoto ke S3 / Wasabi
- Rate limiting: 1x per hari per siswa
- Feature test untuk presensi endpoint
```

### Assessment

```markdown
## Week 6 Assessment

**Fathan:**
- [ ] Camera preview working
- [ ] Geolocation working
- [ ] Loading/error/success states OK
- [ ] TypeScript type-safe
- [ ] Responsive design OK

**Ihsan:**
- [ ] Presensi API endpoint working
- [ ] Geolocation validation OK
- [ ] File upload OK
- [ ] Rate limiting OK
- [ ] Service Layer pattern konsisten
- [ ] Feature test > 70% coverage
```

---

## 📅 Week 7-8: Laporan & Finalisasi

### Topics

#### Fathan — Frontend Track
```
✅ React: table dengan sorting, filtering, pagination
✅ Export: download laporan (Excel/PDF)
✅ Testing: Jest + React Testing Library
✅ Performance: React.memo, lazy loading
✅ Final project: halaman admin panel
```

#### Ihsan — Backend Track
```
✅ Laporan: export Excel (maatwebsite/Laravel Excel)
✅ Laporan: export PDF (barryvdh/laravel-dompdf)
✅ Queue & Job untuk export besar
✅ Integration test (API + database)
✅ Performance optimization (query, indexing)
✅ NeonDB: branch untuk deployment preview
```

### Tasks

#### Fathan
```
- Halaman Laporan (table + filter + export button)
- Halaman Admin Panel (manage siswa, guru, kelas)
- Integration test dengan Inertia pages
- Final responsive polish
- Self-review: TypeScript strict, zero console.log
```

#### Ihsan
```
- Export Excel: laporan presensi bulanan
- Export PDF: rekap presensi per siswa
- Queue job untuk export besar
- Integration test
- API documentation (Postman / Stoplight)
- Final security review
```

### Assessment

```markdown
## Week 8 Assessment (Final)

**Fathan:**
- [ ] Inertia+React mastery
- [ ] TypeScript strict (zero any)
- [ ] Responsive design OK semua halaman
- [ ] Testing OK
- [ ] MANDIRI: dapat develop fitur tanpa supervision ketat

**Ihsan:**
- [ ] Service Layer pattern konsisten
- [ ] Sanctum + Spatie OK
- [ ] PostgreSQL optimization OK
- [ ] Testing > 70% coverage
- [ ] API documentation lengkap
- [ ] MANDIRI: dapat develop fitur tanpa supervision ketat
```

---

## 🎓 Learning Methods

### 1. Pair Programming (2x/minggu)

**Schedule:**
- Selasa 14:00 — Ihsan + Azis (backend focus)
- Kamis 14:00 — Fathan + Azis (frontend focus)
- Jumat 14:00 — Review & Q&A dengan Sandikodev

**Format:**
- Azis atau Sandikodev drive (share screen)
- Developer navigate (observe, tanya, coba sendiri)
- Swap setelah 30 menit

### 2. Code Review as Learning

**Tahapan review:**
1. Developer self-review (ceklist)
2. Azis review awal — cari typo, N+1, logical error
3. Sandikodev review final — arsitektur, best practices

**Reviewer wajib:**
- Explain "kenapa", bukan hanya "apa"
- Link dokumentasi
- Example code snippet
- Developer fix dengan paham

### 3. Weekly Knowledge Sharing

**Schedule:** Jumat 16:00-17:00
**Format:**
- Minggu 1: Sandikodev (Arsitektur SMART Absen + Tech Stack)
- Minggu 2: Azis (Service Layer Pattern + TypeScript tips)
- Minggu 3: Fathan (Share learning React/Inertia)
- Minggu 4: Ihsan (Share learning Sanctum/Spatie/PostgreSQL)
- Minggu 5+: Bergantian presentasi progress

### 4. Learning Journal

Setiap developer wajib maintain `.openkb/PERSONAL/<nama>/sessions/`:

```markdown
## Week [X] Learning Journal

**Nama:** [Fathan/Ihsan]

### What I Learned
- Topic 1
- Topic 2

### Challenges
- Challenge 1 + how I solved it (dengan/tanpa Azis)
- Challenge 2

### Questions for Next Week
- Question 1
- Question 2

### Goals for Next Week
- Goal 1
- Goal 2
```

---

## 📊 Progress Tracking

### Weekly Check-in (Jumat 15:00)

Azis maintain Trello card `📚 Learning Path` untuk tracking:

**Skill Assessment (1-5):**

| Skill | Week 0 | Week X | Target Week 8 |
|---|---|---|---|
| **Fathan:** Git & GitHub | - | - | 5 |
| React + TypeScript | - | - | 5 |
| InertiaJS | - | - | 4 |
| Tailwind CSS | - | - | 5 |
| Testing | - | - | 4 |
| **Ihsan:** Git & GitHub | - | - | 5 |
| Laravel | - | - | 5 |
| PostgreSQL | - | - | 4 |
| Sanctum + Spatie | - | - | 5 |
| Service Layer | - | - | 5 |
| Testing | - | - | 4 |

**Notes:**
[Catatan Azis tentang progress, blocker, adjustment]

---

## 🏆 Final Assessment Criteria

### Week 8 — Independence Level

**Level 1: Dependent**
- Perlu instruction detail langkah demi langkah
- Code quality rendah (banyak TypeScript error, logical bug)
- Tidak bisa debug sendiri
- Communication kurang

**Level 2: Guided**
- Perlu guidance untuk task kompleks
- Code quality OK (minor TypeScript error)
- Bisa debug sederhana dengan bantuan Azis
- Communication OK

**Level 3: Independent** ✅ TARGET
- Dapat develop fitur standar mandiri
- TypeScript strict, code quality sesuai standard
- Bisa debug sendiri (baca error, cari solusi)
- Proactive communication — tanya Azis jika perlu, eskalasi ke Sandikodev jika urgent

**Level 4: Advanced**
- Dapat develop fitur kompleks mandiri
- Code quality excellent
- Bisa bantu developer lain
- Zero supervision needed

---

## 📚 Recommended Resources

### Frontend (Fathan)

- [React 19 Documentation](https://react.dev/)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/)
- [InertiaJS Documentation](https://inertiajs.com/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro)

### Backend (Ihsan)

- [Laravel Documentation](https://laravel.com/docs)
- [Laravel Sanctum](https://laravel.com/docs/sanctum)
- [Spatie Laravel Permission](https://spatie.be/docs/laravel-permission)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [NeonDB Documentation](https://neon.tech/docs)
- [Laracasts: Laravel from Scratch](https://laracasts.com/series/laravel-from-scratch)

### Bersama

- "Clean Code" — Robert C. Martin
- "The Pragmatic Programmer" — Andrew Hunt
- [OpenKB for Junior](https://github.com/konxc/openkb-for-junior)

---

**Last Updated:** 2026-06-30
**Maintained by:** Sandikodev & Azis
