# Junior Developer Learning Path

> 8-week roadmap for Fathan (Frontend) & Ihsan (Backend) to become independent.
> Azis (Learning Mentor) as discussion partner, debugging buddy, and concept explainer.

---

## 🎯 Goal

After 8 weeks:
- ✅ **Fathan** able to develop Inertia+React features independently (TypeScript, hooks, state management, testing)
- ✅ **Ihsan** able to develop Laravel API features independently (Service Layer, Sanctum, Spatie, PostgreSQL)
- ✅ Code quality according to standards (PSR-12, TypeScript strict, Laravel conventions)
- ✅ Proactive communication — ask Azis first, escalate to Sandikodev if needed
- ✅ Self-debugging capability — read error messages, find solutions, ask if stuck > 30 minutes

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
✅ TypeScript basics: data types, interface, type alias, simple generics
✅ React hooks: useState, useEffect, props & state
✅ Functional component with TypeScript (props interface)
✅ JSX + Tailwind CSS 4 utility classes
```

#### Ihsan — Backend Track
```
✅ Git basics (clone, add, commit, push, pull, branch)
✅ Pull Request workflow + conventional commits
✅ Laravel fundamentals: routing, controller, request lifecycle
✅ Service Layer pattern: what, why, how
✅ Eloquent ORM: model, migration, seeder
✅ PostgreSQL basics: connect via Laragon, create database, run migration
```

### Tasks

#### Fathan
```
- Clone repository core, setup Bun + Vite
- Create branch: `feature/learning-frontend`
- Create simple React components: Counter, Todo List (TypeScript)
- Implement Tailwind responsive (mobile-first)
- First commit & PR
- Fix based on review (Azis → Sandikodev)
```

#### Ihsan
```
- Clone repository core, setup PostgreSQL + Laragon
- Create branch: `feature/learning-backend`
- Create migration: `create_books_table` (PostgreSQL syntax)
- Create Model: `Book` + Seeder
- Create Service: `BookService` → call from controller
- CRUD: GET/POST/PUT/DELETE via web.php (Inertia)
- First commit & PR
```

### Assessment

```markdown
## Week 2 Assessment

**Fathan:**
- [ ] Can clone + setup environment (Bun, Vite, Laragon)
- [ ] Understands Git workflow (branch, commit, PR)
- [ ] Can create simple React + TypeScript components
- [ ] Understands useState, useEffect
- [ ] Can style with Tailwind utility classes

**Ihsan:**
- [ ] Can clone + setup PostgreSQL in Laragon
- [ ] Understands Git workflow (branch, commit, PR)
- [ ] Can create migration & seeder
- [ ] Understands Service Layer pattern
- [ ] Can create CRUD with Eloquent
```

---

## 📅 Week 3-4: InertiaJS / Auth & RBAC

### Topics

#### Fathan — Frontend Track
```
✅ InertiaJS: Inertia::render, Link, useForm, usePage
✅ React advanced hooks: useCallback, useMemo, custom hooks
✅ TypeScript: generic, union type, type narrowing
✅ Form handling + validation display (error messages from Laravel)
✅ Shared data via Inertia (app name, user, permissions)
```

#### Ihsan — Backend Track
```
✅ Laravel Sanctum: install, configuration, token management
✅ Spatie Laravel Permission: install, role & permission seeder
✅ Form Request validation
✅ Middleware: auth:sanctum, role, permission
✅ PostgreSQL: JSONB for metadata, indexing, query optimization
```

### Tasks

#### Fathan
```
- Setup InertiaJS in core (resources/js/Pages/)
- Create Login page (React + Inertia + Tailwind)
- Create Dashboard page after login
- Implement form validation display
- Create layout component (sidebar, navbar, content area)
- Responsive: mobile sidebar → desktop sidebar
```

#### Ihsan
```
- Install & setup Sanctum
- Install & setup Spatie Permission
- Create migration users + roles + permissions
- Create AuthService: login, register, logout
- Create API + Web controller for auth
- Create middleware: role:admin, permission:view-dashboard
- Unit test for auth endpoint
```

### Assessment

```markdown
## Week 4 Assessment (Mid-term)

**Fathan:**
- [ ] Understands InertiaJS: routing, form, shared data
- [ ] Can create login page + dashboard
- [ ] Form validation display OK
- [ ] Responsive layout OK
- [ ] TypeScript type-safe

**Ihsan:**
- [ ] Sanctum login/register/logout working
- [ ] Spatie RBAC integrated
- [ ] Service Layer pattern consistent
- [ ] Form Request validation
- [ ] Unit test > 50% coverage
```

---

## 📅 Week 5-6: Presensi Module

### Topics

#### Fathan — Frontend Track
```
✅ React advanced: context API, useReducer, custom hooks
✅ Camera API: getUserMedia for selfie
✅ Geolocation API: getCurrentPosition, watchPosition
✅ Image upload + preview
✅ Loading & error states pattern
✅ TypeScript: handling API response types
```

#### Ihsan — Backend Track
```
✅ API endpoint design for attendance
✅ Geolocation validation (latitude, longitude, radius)
✅ File upload handling (S3 Wasabi/MinIO)
✅ Rate limiting (throttle)
✅ Feature test for API
✅ PostgreSQL: JSONB for attendance metadata
```

### Tasks

#### Fathan
```
- Create Attendance page (check-in form)
- Implement camera preview (selfie)
- Implement geolocation (latitude, longitude)
- Form submission via Inertia
- Loading state, error state, success state
- Create Attendance History page (table)
```

#### Ihsan
```
- Create attendance migration (PostgreSQL)
- Create PresensiService: check-in, history, recap
- Geolocation validation (radius from school)
- Upload selfie to S3 / Wasabi
- Rate limiting: 1x per day per student
- Feature test for attendance endpoint
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
- [ ] Attendance API endpoint working
- [ ] Geolocation validation OK
- [ ] File upload OK
- [ ] Rate limiting OK
- [ ] Service Layer pattern consistent
- [ ] Feature test > 70% coverage
```

---

## 📅 Week 7-8: Reports & Finalization

### Topics

#### Fathan — Frontend Track
```
✅ React: table with sorting, filtering, pagination
✅ Export: download reports (Excel/PDF)
✅ Testing: Jest + React Testing Library
✅ Performance: React.memo, lazy loading
✅ Final project: admin panel page
```

#### Ihsan — Backend Track
```
✅ Reports: export Excel (maatwebsite/Laravel Excel)
✅ Reports: export PDF (barryvdh/laravel-dompdf)
✅ Queue & Job for large exports
✅ Integration test (API + database)
✅ Performance optimization (query, indexing)
✅ NeonDB: branch for deployment preview
```

### Tasks

#### Fathan
```
- Reports page (table + filter + export button)
- Admin Panel page (manage students, teachers, classes)
- Integration test with Inertia pages
- Final responsive polish
- Self-review: TypeScript strict, zero console.log
```

#### Ihsan
```
- Export Excel: monthly attendance report
- Export PDF: attendance recap per student
- Queue job for large exports
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
- [ ] Responsive design OK all pages
- [ ] Testing OK
- [ ] INDEPENDENT: can develop features without tight supervision

**Ihsan:**
- [ ] Service Layer pattern consistent
- [ ] Sanctum + Spatie OK
- [ ] PostgreSQL optimization OK
- [ ] Testing > 70% coverage
- [ ] API documentation complete
- [ ] INDEPENDENT: can develop features without tight supervision
```

---

## 🎓 Learning Methods

### 1. Pair Programming (2x/week)

**Schedule:**
- Tuesday 14:00 — Ihsan + Azis (backend focus)
- Thursday 14:00 — Fathan + Azis (frontend focus)
- Friday 14:00 — Review & Q&A with Sandikodev

**Format:**
- Azis or Sandikodev drives (share screen)
- Developer navigates (observe, ask, try themselves)
- Swap after 30 minutes

### 2. Code Review as Learning

**Review stages:**
1. Developer self-review (checklist)
2. Azis initial review — find typos, N+1, logical errors
3. Sandikodev final review — architecture, best practices

**Reviewer must:**
- Explain "why", not just "what"
- Link documentation
- Example code snippet
- Developer fixes with understanding

### 3. Weekly Knowledge Sharing

**Schedule:** Friday 16:00-17:00
**Format:**
- Week 1: Sandikodev (SMART Absen Architecture + Tech Stack)
- Week 2: Azis (Service Layer Pattern + TypeScript tips)
- Week 3: Fathan (Share learning React/Inertia)
- Week 4: Ihsan (Share learning Sanctum/Spatie/PostgreSQL)
- Week 5+: Alternate progress presentations

### 4. Learning Journal

Every developer must maintain `.openkb/PERSONAL/<name>/sessions/`:

```markdown
## Week [X] Learning Journal

**Name:** [Fathan/Ihsan]

### What I Learned
- Topic 1
- Topic 2

### Challenges
- Challenge 1 + how I solved it (with/without Azis)
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

### Weekly Check-in (Friday 15:00)

Azis maintains Trello card `📚 Learning Path` for tracking:

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
[Azis's notes on progress, blockers, adjustments]

---

## 🏆 Final Assessment Criteria

### Week 8 — Independence Level

**Level 1: Dependent**
- Needs detailed step-by-step instructions
- Low code quality (many TypeScript errors, logical bugs)
- Cannot debug independently
- Poor communication

**Level 2: Guided**
- Needs guidance for complex tasks
- Code quality OK (minor TypeScript error)
- Can do simple debugging with Azis's help
- Communication OK

**Level 3: Independent** ✅ TARGET
- Can develop standard features independently
- TypeScript strict, code quality according to standards
- Can debug independently (read errors, find solutions)
- Proactive communication — ask Azis if needed, escalate to Sandikodev if urgent

**Level 4: Advanced**
- Can develop complex features independently
- Code quality excellent
- Can help other developers
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

### Together

- "Clean Code" — Robert C. Martin
- "The Pragmatic Programmer" — Andrew Hunt
- [OpenKB for Junior](https://github.com/konxc/openkb-for-junior)

---

**Last Updated:** 2026-06-30
**Maintained by:** Sandikodev & Azis
