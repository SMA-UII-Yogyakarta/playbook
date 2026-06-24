# Junior Developer Learning Path

> Roadmap 8 minggu untuk Fathan & Ihsan menjadi mandiri.

---

## 🎯 Goal

Setelah 8 minggu:
- ✅ Fathan mampu develop fitur Livewire/React secara mandiri
- ✅ Ihsan mampu develop fitur Laravel API secara mandiri
- ✅ Code quality sesuai standard (PSR-12, Laravel conventions)
- ✅ Proactive communication
- ✅ Self-debugging capability

---

## 📊 Assessment Timeline

```
Week 0 → Baseline assessment
Week 4 → Mid-term assessment
Week 8 → Final assessment
```

---

## 📅 Week 1-2: Git & GitHub Fundamentals

### Topics

```
✅ Git basics (clone, add, commit, push, pull)
✅ Branching strategy
✅ Pull Request workflow
✅ Code review process
✅ Conventional commits
```

### Tasks

```
- Clone repository core
- Buat branch pertama: `feature/learning-git`
- Commit pertama: Update README
- Buat Pull Request pertama
- Fix berdasarkan review
- Merge PR pertama
```

### Resources

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)

### Assessment

```markdown
## Week 2 Assessment

**Fathan:**
- [ ] Dapat clone repository
- [ ] Dapat buat branch
- [ ] Commit message sesuai conventional commit
- [ ] Dapat buat PR
- [ ] Respond feedback review

**Ihsan:**
- [ ] Sama dengan Fathan
```

---

## 📅 Week 3-4: Laravel Fundamentals

### Topics

```
✅ MVC Architecture
✅ Routing (web.php, api.php)
✅ Eloquent ORM
✅ Migration & Seeder
✅ Validation (Form Request)
✅ Blade templating
```

### Tasks (Ihsan — Backend Focus)

```
- Buat migration: `create_books_table`
- Buat Model: `Book`
- Buat Seeder: `BookSeeder`
- Buat Controller: `BookController`
- Implementasi CRUD:
  - GET /books (index)
  - POST /books (store)
  - GET /books/{id} (show)
  - PUT /books/{id} (update)
  - DELETE /books/{id} (destroy)
- Validation di Form Request
- Unit test untuk Model
```

### Tasks (Fathan — Frontend Focus)

```
- Buat Blade layout
- Buat view untuk CRUD books
- Implementasi form validation
- Responsive design dengan Tailwind
- Livewire component untuk search
```

### Resources

- [Laravel Documentation](https://laravel.com/docs)
- [Laravel from Scratch](https://laracasts.com/series/laravel-from-scratch)
- [`environment-setup.md`](../01-getting-started/environment-setup.md)

### Assessment

```markdown
## Week 4 Assessment (Mid-term)

**Ihsan:**
- [ ] Paham MVC architecture
- [ ] Dapat buat migration & seeder
- [ ] Dapat buat Eloquent model dengan relation
- [ ] Dapat buat Form Request validation
- [ ] Dapat buat CRUD API endpoint
- [ ] Dapat buat unit test

**Fathan:**
- [ ] Paham MVC architecture
- [ ] Dapat buat Blade view
- [ ] Dapat buat Livewire component
- [ ] Dapat styling dengan Tailwind
- [ ] Paham form validation
```

---

## 📅 Week 5-6: Livewire & Tailwind CSS

### Topics

```
✅ Livewire 3 components
✅ Alpine.js basics
✅ Tailwind CSS utility classes
✅ Vite build system
✅ Responsive design
```

### Tasks (Fathan)

```
- Buat Livewire component: `AttendanceForm`
- Implementasi camera preview
- Geolocation handling
- Form submission dengan validation
- Responsive design (mobile-first)
- Loading states & error handling
```

### Tasks (Ihsan)

```
- Support Fathan di Livewire
- Focus ke backend API
- API endpoint untuk attendance
- Geolocation validation
- Photo upload handling
- Unit test untuk API
```

### Resources

- [Livewire Documentation](https://livewire.laravel.com/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [Alpine.js Documentation](https://alpinejs.dev/)

### Assessment

```markdown
## Week 6 Assessment

**Fathan:**
- [ ] Dapat buat Livewire component
- [ ] Dapat handle form submission
- [ ] Dapat styling dengan Tailwind
- [ ] Responsive design OK
- [ ] Loading & error states OK

**Ihsan:**
- [ ] Dapat buat API endpoint
- [ ] Validation logic OK
- [ ] Unit test OK
- [ ] Basic Livewire paham
```

---

## 📅 Week 7-8: API & Sanctum

### Topics

```
✅ REST API design
✅ Laravel Sanctum authentication
✅ API testing (Postman/Insomnia)
✅ Rate limiting
✅ API documentation
```

### Tasks (Ihsan)

```
- Setup Sanctum authentication
- Buat API endpoint: `POST /api/attendance`
- Implementasi rate limiting
- API documentation (Postman)
- Unit test untuk API endpoint
- Integration test (API + database)
```

### Tasks (Fathan)

```
- Support Ihsan di API testing
- Focus ke React fundamentals
- React component basics
- State management basics
- API integration dengan fetch/axios
```

### Resources

- [Laravel Sanctum](https://laravel.com/docs/sanctum)
- [REST API Best Practices](https://restfulapi.net/)
- [React Documentation](https://react.dev/)

### Assessment

```markdown
## Week 8 Assessment (Final)

**Ihsan:**
- [ ] Dapat buat REST API endpoint
- [ ] Sanctum authentication OK
- [ ] API validation OK
- [ ] Unit test OK
- [ ] Integration test OK
- [ ] API documentation OK
- [ ] MANDIRI: Dapat develop fitur tanpa supervision ketat

**Fathan:**
- [ ] Livewire mastery
- [ ] React basics OK
- [ ] API integration OK
- [ ] Tailwind mastery
- [ ] Responsive design OK
- [ ] MANDIRI: Dapat develop fitur tanpa supervision ketat
```

---

## 🎓 Learning Methods

### 1. Pair Programming (2x/minggu)

**Schedule:**
- Selasa 14:00 — Ihsan + Sandikodev
- Kamis 14:00 — Fathan + Sandikodev

**Format:**
- Sandikodev drive (share screen)
- Developer navigate (observe, tanya)
- Swap setelah 30 menit

---

### 2. Code Review as Learning

**Setiap PR:**
- Reviewer (Sandikodev) explain "kenapa", bukan hanya "apa"
- Link dokumentasi
- Example code snippet
- Developer fix dengan paham

---

### 3. Weekly Knowledge Sharing

**Schedule:** Jumat 16:00-17:00  
**Format:**
- Minggu 1: Sandikodev (Laravel Best Practices)
- Minggu 2: Fathan (Share learning Livewire)
- Minggu 3: Ihsan (Share learning API)
- Minggu 4: External resource (Laracasts video)

---

### 4. Learning Journal

**Setiap developer wajib:**
```markdown
## Week [X] Learning Journal

**Nama:** [Fathan/Ihsan]

### What I Learned
- Topic 1
- Topic 2

### Challenges
- Challenge 1 + how I solved it
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

**Template:**

```markdown
## Week [X] Check-in

**Developer:** [Fathan/Ihsan]

### Skill Assessment (1-5)

| Skill | Week 0 | Week X | Target Week 8 |
|---|---|---|---|
| Git & GitHub | 2 | 3 | 5 |
| Laravel | 2 | 3 | 5 |
| Livewire | 1 | 3 | 4 |
| Tailwind | 2 | 4 | 5 |
| Testing | 1 | 2 | 4 |
| Communication | 3 | 3 | 5 |

### Progress
✅ On track
⚠️ Need improvement
❌ Behind

### Notes
[Catatan Sandikodev]
```

---

## 🏆 Final Assessment Criteria

### Week 8 — Independence Level

**Level 1: Dependent**
- Perlu instruction detail
- Code quality rendah
- Banyak bug
- Communication kurang

**Level 2: Guided**
- Perlu guidance untuk task kompleks
- Code quality OK
- Minor bugs
- Communication OK

**Level 3: Independent** ✅ TARGET
- Dapat develop fitur standar mandiri
- Code quality sesuai standard
- Minimal bugs
- Proactive communication

**Level 4: Advanced**
- Dapat develop fitur kompleks mandiri
- Code quality excellent
- Zero bugs
- Help other developers

---

## 📚 Recommended Resources

### Books

- "Clean Code" — Robert C. Martin
- "The Pragmatic Programmer" — Andrew Hunt
- "Laravel Up & Running" — Matt Stauffer

### Online Courses

- [Laravel from Scratch](https://laracasts.com/series/laravel-from-scratch)
- [Testing Laravel](https://testing-laravel.com/)
- [Livewire 3 Bootcamp](https://laracasts.com/series/livewire-3-bootcamp)

### Documentation

- [Laravel Documentation](https://laravel.com/docs)
- [Livewire Documentation](https://livewire.laravel.com/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

---

**Next:** [`laravel-fundamentals.md`](laravel-fundamentals.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev