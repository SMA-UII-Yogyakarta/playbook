# Team Roles & Responsibilities

> Detail peran, tanggung jawab, dan ekspektasi untuk setiap anggota tim engineering SMA UII.

---

## 📊 Organization Structure

```
PT Koneksi Jaringan Indonesia
│
└── SMA UII Yogyakarta Project
    │
    ├── Sandikodev (Project Manager, Architect, Tech Lead)
    │
    ├── Ahmad Hanif (Product Analyst)
    │
    ├── Fathan Mubina (Junior Developer — Frontend: Inertia+React)
    │
    ├── Ihsan (Junior Developer — Backend: Laravel API, PostgreSQL)
    │
    └── Azis (Learning Mentor — discussion partner, debugging buddy)
```

---

## 👨‍💼 Sandikodev — Project Manager, Architect, Tech Lead

**GitHub:** [@Sandikodev](https://github.com/Sandikodev)

### Primary Responsibilities

#### 1. Architecture & Technical Design (30%)
- System architecture (monorepo, API design, database schema)
- Technology stack decisions
- Security & scalability planning
- Infrastructure & deployment strategy

#### 2. Mentoring & Team Development (30%)
- Code review dengan feedback konstruktif
- Pair programming untuk task kompleks
- Knowledge sharing session (mingguan)
- Career growth tracking untuk junior developer

#### 3. Code Review & Quality Assurance (20%)
- Review semua Pull Request sebelum merge
- Ensure coding standard (PSR-12, Laravel conventions)
- Check security best practices
- Performance optimization

#### 4. Sprint Planning & Project Management (10%)
- Sprint planning meeting (setiap 2 minggu)
- Backlog refinement
- Task estimation & assignment
- Stakeholder communication (Pak Mahfud, SMA UII)

#### 5. Hands-on Development (10%)
- Critical features (SSO, authentication core)
- Bug fixing production
- Performance bottleneck resolution
- **Tidak** mengambil task CRUD sederhana (delegate ke junior)

### Time Allocation

```
30% ██████████████████████████████ Architecture
30% ██████████████████████████████ Mentoring
20% ████████████████████ Code Review
10% ██████████ Planning
10% ██████████ Coding
```

### Key Metrics
- PR review time < 24 jam
- Sprint velocity consistency
- Junior developer progress (skill assessment per sprint)
- Zero critical bug production setelah deployment

### Do's
- ✅ Delegate task secepat mungkin
- ✅ Dokumentasi setiap architecture decision
- ✅ Feedback spesifik & actionable di PR
- ✅ Escalate issue ke stakeholder early

### Don'ts
- ❌ Jangan coding > 40% waktu (bottleneck risk)
- ❌ Jangan merge PR tanpa review
- ❌ Jangan asumsikan junior tahu (explain context)
- ❌ Jangan skip sprint retrospective

---

## 📝 Ahmad Hanif — Product Analyst

**GitHub:** [@Rosyiii](https://github.com/Rosyiii)

### Primary Responsibilities

#### 1. Requirement Gathering & Analysis (40%)
- Interview stakeholder (Pak Mahfud, SMA UII staff)
- Translate business needs ke user story
- Define acceptance criteria yang jelas
- Prioritize features berdasarkan business value

#### 2. User Story & Documentation (30%)
- Tulis user story format:
  ```
  Sebagai [role]
  Saya ingin [fitur]
  Agar [manfaat]
  ```
- Maintain product backlog di Trello
- Update dokumentasi requirement
- Create flow diagram (draw.io / Excalidraw)

#### 3. UAT & Quality Validation (20%)
- Test fitur di staging environment
- Validasi acceptance criteria
- Report bug dengan detail reproduksi
- Sign-off sebelum production deploy

#### 4. Stakeholder Communication (10%)
- Update progress ke Pak Mahfud
- Manage ekspektasi client
- Feedback loop dari user

### Key Metrics
- Requirement clarity (sedikit revisi dari developer)
- UAT pass rate > 90%
- Stakeholder satisfaction
- Bug detection di staging (bukan production)

### Do's
- ✅ Tanya "kenapa" sebelum "apa" (pahami business problem)
- ✅ Acceptance criteria spesifik & testable
- ✅ Update Trello card real-time
- ✅ Test di staging sebelum production

### Don'ts
- ❌ Jangan asumsikan technical implementation
- ❌ Jangan skip UAT
- ❌ Jangan janjikan timeline ke client tanpa konsultasi Sandikodev
- ❌ Jangan vague acceptance criteria ("harus bagus" ❌)

### Example User Story Quality

**Buruk:**
```
Sebagai admin
Saya ingin export laporan
Agar bisa download
```

**Baik:**
```
Sebagai admin tata usaha
Saya ingin export laporan presensi bulanan dalam format Excel
Agar dapat mencetak dan mendistribusikan ke wali kelas

Acceptance Criteria:
- Export periode 1 bulan (dropdown bulan & tahun)
- Format file: .xlsx
- Kolom: nama siswa, kelas, total hadir, sakit, izin, alfa
- Filter per kelas (all / spesifik)
- Max 1000 baris per export
```

---

## 💻 Fathan Mubina — Junior Developer (Frontend)

**GitHub:** [@Hans02-Neo](https://github.com/Hans02-Neo)

### Primary Responsibilities

#### 1. Frontend Development (60%)
- InertiaJS pages + React 19 components
- TypeScript — semua kode frontend wajib .tsx
- Tailwind CSS 4 styling (responsive, mobile-first)
- Vite 8 asset bundling
- API integration via Inertia (form submission, data fetching)
- React hooks, state management, component lifecycle

#### 2. Bug Fixing & Maintenance (20%)
- Fix UI bug
- Responsive testing (mobile, tablet, desktop)
- Cross-browser testing (Chrome, Firefox, Edge)
- Performance optimization (lazy loading, code splitting)

#### 3. Testing & Documentation (10%)
- Unit test frontend (Jest + React Testing Library)
- Self-testing sebelum PR
- Dokumentasi component usage (props, state, events)

#### 4. Learning & Growth (10%)
- Ikuti learning path (8 minggu)
- Pair programming dengan Azis (Learning Mentor)
- Code review feedback implementation

### Learning Path (8 Minggu)

```
Week 1-2: Git, GitHub, TypeScript dasar, React hooks
Week 3-4: InertiaJS, Tailwind CSS 4, responsive design
Week 5-6: React advanced (context, custom hooks, state management)
Week 7-8: API integration, testing, deployment
```

### Key Metrics
- Task completion rate > 80%
- Code review iteration < 3x per PR
- Bug recurrence rate < 10%
- Learning path progress

### Do's
- ✅ Self-review sebelum submit PR (cek TypeScript error, unused import, console.log)
- ✅ Test di multiple browser (Chrome, Firefox, Edge)
- ✅ Responsive testing (mobile, tablet, desktop)
- ✅ Tanya Azis jika stuck > 30 menit, eskalasi ke Sandikodev jika > 2 jam
- ✅ Gunakan TypeScript strict — hindari `any`

### Don'ts
- ❌ Jangan commit console.log() atau debugger
- ❌ Jangan hardcode value (warna, spacing, font — pakai Tailwind utility)
- ❌ Jangan skip responsive testing
- ❌ Jangan copy-paste StackOverflow tanpa paham
- ❌ Jangan gunakan `any` di TypeScript tanpa alasan jelas

---

## 💻 Ihsan — Junior Developer (Backend)

**GitHub:** [@Odauna](https://github.com/Odauna)

### Primary Responsibilities

#### 1. Backend Development (60%)
- Laravel API endpoint (Inertia controller + API controller)
- Service Layer pattern — logic di `app/Services/`, controller tipis
- Eloquent model & relationship (PostgreSQL syntax)
- Database migration & seeder (PostgreSQL/NeonDB)
- Validation & Form Request
- Sanctum token management
- Spatie Laravel Permission (RBAC)

#### 2. Database Management (20%)
- PostgreSQL query optimization (eager loading, chunk, cursor)
- Indexing untuk query sering (PostgreSQL)
- Data integrity & constraint (CHECK, FK, unique)
- NeonDB branching untuk testing

#### 3. Testing & Documentation (10%)
- Unit test (PHPUnit) — minimal 70% coverage
- API documentation (Postman/Insomnia/Stoplight)
- Self-testing sebelum PR

#### 4. Learning & Growth (10%)
- Ikuti learning path (8 minggu)
- Pair programming dengan Azis (Learning Mentor)
- Code review feedback implementation

### Learning Path (8 Minggu)

```
Week 1-2: Git, GitHub, Laravel fundamentals, Service Layer concept
Week 3-4: Eloquent, Migration, Seeder, PostgreSQL specific
Week 5-6: API Design, Sanctum, Spatie Permission, Testing
Week 7-8: Advanced — Queue, Event, Job, NeonDB deployment
```

### Key Metrics
- API endpoint performance < 200ms
- Test coverage > 70%
- Code review iteration < 3x per PR
- Zero SQL injection vulnerability

### Do's
- ✅ Service Layer pattern — logic di Service, controller hanya panggil service
- ✅ Use Eloquent (raw query hanya jika necessary)
- ✅ Eager loading (`with()`) untuk cegah N+1
- ✅ Validation di Form Request class
- ✅ Write test sebelum/sesudah code
- ✅ PostgreSQL-native features (JSONB, array, window functions)

### Don'ts
- ❌ Jangan commit `.env` atau credentials
- ❌ Jangan skip validation
- ❌ Jangan N+1 query di production
- ❌ Jangan hardcode credentials
- ❌ Jangan letakkan business logic di controller (harus di Service Layer)

---

## 🎓 Azis — Learning Mentor

**GitHub:** (akan ditambahkan)

### Primary Responsibilities

Azis adalah **Learning Mentor** — bukan junior developer yang mengerjakan task fitur, melainkan **teman diskusi, debugging buddy, dan concept explainer** untuk Fathan & Ihsan.

#### 1. Discussion Partner (30%)
- Teman diskusi teknis untuk Fathan & Ihsan
- Bantu resolve blocker teknis langsung (bukan eskalasi ke Sandikodev)
- Pair programming untuk task yang Fathan/Ihsan anggap sulit

#### 2. Concept Explainer (25%)
- Jelasin konsep Laravel, React, TypeScript, Inertia, PostgreSQL
- Jelaskan arsitektur — Service Layer, Sanctum, Spatie RBAC
- Buat analogi dan contoh yang relevan dengan project

#### 3. Code Review Prep (25%)
- Review awal sebelum PR dikirim ke Sandikodev
- Cari: typo, N+1 query, logical error, TypeScript type issue
- Pastikan self-checklist tercentang

#### 4. Learning Tracker (20%)
- Bantu maintain progress learning path di Trello tracker
- Fasilitasi environment setup (Laragon, Bun, PostgreSQL, NeonDB)
- Dokumentasi common issues & solusi

### Batasan (Apa yang Azis TIDAK lakukan)
- ❌ **Tidak** membuat keputusan arsitektur — itu ranah Sandikodev
- ❌ **Tidak** melakukan final code review / approve PR — itu ranah Sandikodev
- ❌ **Tidak** manage sprint / backlog — itu ranah Sandikodev & Hanif
- ❌ **Tidak** handle komunikasi stakeholder — itu ranah Sandikodev & Hanif

### Key Metrics
- Blocker resolution time untuk Fathan/Ihsan < 4 jam
- Learning path progress sesuai target
- Fathan & Ihsan semakin mandiri (target: independen di akhir Sprint 4)
- Code review iteration < 3x per PR saat sampai ke Sandikodev

### Do's
- ✅ Pair programming — duduk bareng Fathan/Ihsan, bukan cuma chat
- ✅ Document common issues — buat catatan di playbook atau openkb
- ✅ Tanya "menurut kamu bagaimana?" sebelum kasih jawaban
- ✅ Eskalasi ke Sandikodev jika blocker > 1 hari

### Don'ts
- ❌ Jangan ambil task fitur — bukan tanggung jawab Learning Mentor
- ❌ Jangan jadi "walking encyclopedia" — ajarin cara cari jawaban, bukan kasih jawaban
- ❌ Jangan bypass Sandikodev untuk keputusan arsitektur
- ❌ Jangan biarkan Fathan/Ihsan bergantung — target akhir mereka mandiri

---

## 🤝 Collaboration Matrix

| Activity | Sandikodev | Ahmad Hanif | Fathan | Ihsan | Azis |
|---|---|---|---|---|---|
| **Sprint Planning** | Lead | Co-lead | Participant | Participant | Observer |
| **Daily Standup** | Facilitator | Participant | Participant | Participant | Participant |
| **Requirement Review** | Reviewer | Author | Reviewer | Reviewer | - |
| **Code Review** | Final Reviewer | - | Author | Author | Initial Reviewer |
| **UAT** | Support | Lead | Support | Support | - |
| **Deployment** | Lead | - | Support | Support | - |
| **Retrospective** | Facilitator | Participant | Participant | Participant | Participant |

---

## 📈 Performance Review

### Sprint-based Assessment (Setiap 2 Minggu)

**Criteria:**
1. **Task Completion** (% task selesai tepat waktu)
2. **Code Quality** (review iteration count)
3. **Communication** (responsiveness, clarity)
4. **Learning Progress** (skill improvement)
5. **Teamwork** (helpfulness, collaboration)

**Rating Scale:**
- 1 — Need Improvement
- 2 — Developing
- 3 — Meeting Expectations
- 4 — Exceeding Expectations
- 5 — Outstanding

### 8-Week Goal Assessment

**Fathan & Ihsan:**
- Week 4: Mid-term assessment
- Week 8: Final assessment (independence level)

**Target Week 8:**
- Mampu develop fitur standar tanpa supervision ketat
- Code quality sesuai standard
- Proactive communication
- Self-debugging capability

---

## 🆘 Escalation Path

```
Problem Level 0 (Quick question / stuck < 30 menit)
→ Tanya Azis (Learning Mentor) — WhatsApp / Discord

Problem Level 1 (Task blocker 30 menit - 2 jam)
→ Azis bantu debugging + discussion

Problem Level 2 (Task blocker > 2 jam)
→ Escalate ke Sandikodev via WhatsApp Group

Problem Level 3 (Critical bug production)
→ Escalate ke Sandikodev + Pak Mahfud

Problem Level 4 (Requirement ambiguity)
→ Escalate ke Ahmad Hanif + Sandikodev
```

---

## 📞 Contact & Availability

| Role | WhatsApp | Email | Working Hours |
|---|---|---|---|---|
| Sandikodev | [Link](https://wa.me/...) | sandiko@koneksi.id | 09:00 - 18:00 |
| Ahmad Hanif | [Link](https://wa.me/...) | ahmad.hanif@smauiiyk.sch.id | 08:00 - 16:00 (onsite SMA UII) |
| Fathan | [Link](https://wa.me/...) | fathan@koneksi.id | 09:00 - 18:00 |
| Ihsan | [Link](https://wa.me/...) | ihsan@koneksi.id | 09:00 - 18:00 |
| Azis | [Link](https://wa.me/...) | azis@koneksi.id | 09:00 - 18:00 |

**Emergency Contact:**
- Critical production bug: WhatsApp Group + Call Sandikodev
- Server down: Call Sandikodev → Pak Mahfud

---

**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev