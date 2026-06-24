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
    ├── Fathan Mubina (Junior Developer - Frontend)
    │
    └── Ihsan (Junior Developer - Backend)
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
- Livewire components
- Blade templates
- Tailwind CSS styling
- Alpine.js interactivity
- React/Next.js (setelah MVP)

#### 2. Bug Fixing & Maintenance (20%)
- Fix UI bug
- Responsive testing
- Cross-browser testing
- Performance optimization (lazy loading, caching)

#### 3. Testing & Documentation (10%)
- Unit test frontend (Jest untuk React)
- Self-testing sebelum PR
- Dokumentasi component usage

#### 4. Learning & Growth (10%)
- Ikuti learning path (8 minggu)
- Pair programming dengan Sandikodev
- Code review feedback implementation

### Learning Path (8 Minggu)

```
Week 1-2: Git, GitHub, Livewire basics
Week 3-4: Tailwind CSS, Alpine.js, Vite
Week 5-6: React fundamentals
Week 7-8: Next.js routing, API integration
```

### Key Metrics
- Task completion rate > 80%
- Code review iteration < 3x per PR
- Bug recurrence rate < 10%
- Learning path progress

### Do's
- ✅ Self-review sebelum submit PR
- ✅ Test di multiple browser (Chrome, Firefox, Edge)
- ✅ Responsive testing (mobile, tablet, desktop)
- ✅ Tanya jika stuck > 30 menit

### Don'ts
- ❌ Jangan commit console.log()
- ❌ Jangan hardcode value
- ❌ Jangan skip testing responsive
- ❌ Jangan copy-paste StackOverflow tanpa paham

---

## 💻 Ihsan — Junior Developer (Backend)

**GitHub:** [@Odauna](https://github.com/Odauna)

### Primary Responsibilities

#### 1. Backend Development (60%)
- Laravel API endpoint
- Eloquent model & relationship
- Database migration & seeder
- Validation & Form Request
- Policy & authorization

#### 2. Database Management (20%)
- Query optimization
- Indexing
- Data integrity
- Backup & restore testing

#### 3. Testing & Documentation (10%)
- Unit test (PHPUnit)
- API documentation (Postman/Insomnia)
- Self-testing sebelum PR

#### 4. Learning & Growth (10%)
- Ikuti learning path (8 minggu)
- Pair programming dengan Sandikodev
- Code review feedback implementation

### Learning Path (8 Minggu)

```
Week 1-2: Git, GitHub, Laravel fundamentals
Week 3-4: Eloquent, Migration, Seeder
Week 5-6: API Design, Sanctum, Testing
Week 7-8: Advanced (Queue, Event, Job)
```

### Key Metrics
- API endpoint performance < 200ms
- Test coverage > 70%
- Code review iteration < 3x per PR
- Zero SQL injection vulnerability

### Do's
- ✅ Use Eloquent (raw query hanya jika necessary)
- ✅ eager loading (`with()`) untuk cegah N+1
- ✅ Validation di Form Request class
- ✅ Write test sebelum/sesudah code

### Don'ts
- ❌ Jangan commit `.env` atau credentials
- ❌ Jangan skip validation
- ❌ Jangan N+1 query di production
- ❌ Jangan hardcode credentials

---

## 🤝 Collaboration Matrix

| Activity | Sandikodev | Ahmad Hanif | Fathan | Ihsan |
|---|---|---|---|---|
| **Sprint Planning** | Lead | Co-lead | Participant | Participant |
| **Daily Standup** | Facilitator | Participant | Participant | Participant |
| **Requirement Review** | Reviewer | Author | Reviewer | Reviewer |
| **Code Review** | Reviewer | - | Author | Author |
| **UAT** | Support | Lead | Support | Support |
| **Deployment** | Lead | - | Support | Support |
| **Retrospective** | Facilitator | Participant | Participant | Participant |

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
Problem Level 1 (Task blocker < 2 jam)
→ Tanya di WhatsApp Group

Problem Level 2 (Task blocker > 2 jam)
→ Escalate ke Sandikodev

Problem Level 3 (Critical bug production)
→ Escalate ke Sandikodev + Pak Mahfud

Problem Level 4 (Requirement ambiguity)
→ Escalate ke Ahmad Hanif + Sandikodev
```

---

## 📞 Contact & Availability

| Role | WhatsApp | Email | Working Hours |
|---|---|---|---|
| Sandikodev | [Link](https://wa.me/...) | sandiko@koneksi.id | 09:00 - 18:00 |
| Ahmad Hanif | [Link](https://wa.me/...) | ahmad.hanif@smauiiyk.sch.id | 08:00 - 16:00 (onsite SMA UII) |
| Fathan | [Link](https://wa.me/...) | fathan@koneksi.id | 09:00 - 18:00 |
| Ihsan | [Link](https://wa.me/...) | ihsan@koneksi.id | 09:00 - 18:00 |

**Emergency Contact:**
- Critical production bug: WhatsApp Group + Call Sandikodev
- Server down: Call Sandikodev → Pak Mahfud

---

**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev