# Team Roles & Responsibilities

> Details of roles, responsibilities, and expectations for each SMA UII engineering team member.

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
- Code review with constructive feedback
- Pair programming for complex tasks
- Knowledge sharing session (weekly)
- Career growth tracking for junior developers

#### 3. Code Review & Quality Assurance (20%)
- Review all Pull Requests before merge
- Ensure coding standard (PSR-12, Laravel conventions)
- Check security best practices
- Performance optimization

#### 4. Sprint Planning & Project Management (10%)
- Sprint planning meeting (every 2 weeks)
- Backlog refinement
- Task estimation & assignment
- Stakeholder communication (Pak Mahfud, SMA UII)

#### 5. Hands-on Development (10%)
- Critical features (SSO, authentication core)
- Production bug fixing
- Performance bottleneck resolution
- **Does not** take simple CRUD tasks (delegate to juniors)

### Time Allocation

```
30% ██████████████████████████████ Architecture
30% ██████████████████████████████ Mentoring
20% ████████████████████ Code Review
10% ██████████ Planning
10% ██████████ Coding
```

### Key Metrics
- PR review time < 24 hours
- Sprint velocity consistency
- Junior developer progress (skill assessment per sprint)
- Zero critical production bugs after deployment

### Do's
- ✅ Delegate tasks as soon as possible
- ✅ Document every architecture decision
- ✅ Specific & actionable feedback in PR
- ✅ Escalate issues to stakeholders early

### Don'ts
- ❌ Don't spend > 40% time coding (bottleneck risk)
- ❌ Don't merge PR without review
- ❌ Don't assume juniors know (explain context)
- ❌ Don't skip sprint retrospective

---

## 📝 Ahmad Hanif — Product Analyst

**GitHub:** [@Rosyiii](https://github.com/Rosyiii)

### Primary Responsibilities

#### 1. Requirement Gathering & Analysis (40%)
- Interview stakeholders (Pak Mahfud, SMA UII staff)
- Translate business needs into user stories
- Define clear acceptance criteria
- Prioritize features based on business value

#### 2. User Story & Documentation (30%)
- Write user stories in the format:
  ```
  As a [role]
  I want [feature]
  So that [benefit]
  ```
- Maintain product backlog in Trello
- Update requirement documentation
- Create flow diagrams (draw.io / Excalidraw)

#### 3. UAT & Quality Validation (20%)
- Test features in staging environment
- Validate acceptance criteria
- Report bugs with detailed reproduction steps
- Sign-off before production deploy

#### 4. Stakeholder Communication (10%)
- Update progress to Pak Mahfud
- Manage client expectations
- Feedback loop from users

### Key Metrics
- Requirement clarity (few revisions from developers)
- UAT pass rate > 90%
- Stakeholder satisfaction
- Bug detection in staging (not production)

### Do's
- ✅ Ask "why" before "what" (understand the business problem)
- ✅ Specific & testable acceptance criteria
- ✅ Update Trello cards in real-time
- ✅ Test in staging before production

### Don'ts
- ❌ Don't assume technical implementation
- ❌ Don't skip UAT
- ❌ Don't promise timelines to clients without consulting Sandikodev
- ❌ Don't use vague acceptance criteria ("must be good" ❌)

### Example User Story Quality

**Bad:**
```
As an admin
I want to export reports
So that I can download
```

**Good:**
```
As an administrative staff
I want to export monthly attendance reports in Excel format
So that I can print and distribute them to homeroom teachers

Acceptance Criteria:
- Export period of 1 month (month & year dropdown)
- File format: .xlsx
- Columns: student name, class, total present, sick, leave, absent
- Filter by class (all / specific)
- Max 1000 rows per export
```

---

## 💻 Fathan Mubina — Junior Developer (Frontend)

**GitHub:** [@Hans02-Neo](https://github.com/Hans02-Neo)

### Primary Responsibilities

#### 1. Frontend Development (60%)
- InertiaJS pages + React 19 components
- TypeScript — all frontend code must be .tsx
- Tailwind CSS 4 styling (responsive, mobile-first)
- Vite 8 asset bundling
- API integration via Inertia (form submission, data fetching)
- React hooks, state management, component lifecycle

#### 2. Bug Fixing & Maintenance (20%)
- Fix UI bugs
- Responsive testing (mobile, tablet, desktop)
- Cross-browser testing (Chrome, Firefox, Edge)
- Performance optimization (lazy loading, code splitting)

#### 3. Testing & Documentation (10%)
- Frontend unit test (Jest + React Testing Library)
- Self-testing before PR
- Component usage documentation (props, state, events)

#### 4. Learning & Growth (10%)
- Follow learning path (8 weeks)
- Pair programming with Azis (Learning Mentor)
- Code review feedback implementation

### Learning Path (8 Weeks)

```
Week 1-2: Git, GitHub, TypeScript basics, React hooks
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
- ✅ Self-review before submitting PR (check TypeScript errors, unused imports, console.log)
- ✅ Test on multiple browsers (Chrome, Firefox, Edge)
- ✅ Responsive testing (mobile, tablet, desktop)
- ✅ Ask Azis if stuck > 30 minutes, escalate to Sandikodev if > 2 hours
- ✅ Use TypeScript strict — avoid `any`

### Don'ts
- ❌ Don't commit console.log() or debugger
- ❌ Don't hardcode values (colors, spacing, fonts — use Tailwind utilities)
- ❌ Don't skip responsive testing
- ❌ Don't copy-paste StackOverflow without understanding
- ❌ Don't use `any` in TypeScript without a clear reason

---

## 💻 Ihsan — Junior Developer (Backend)

**GitHub:** [@Odauna](https://github.com/Odauna)

### Primary Responsibilities

#### 1. Backend Development (60%)
- Laravel API endpoints (Inertia controller + API controller)
- Service Layer pattern — logic in `app/Services/`, thin controller
- Eloquent model & relationship (PostgreSQL syntax)
- Database migration & seeder (PostgreSQL/NeonDB)
- Validation & Form Request
- Sanctum token management
- Spatie Laravel Permission (RBAC)

#### 2. Database Management (20%)
- PostgreSQL query optimization (eager loading, chunk, cursor)
- Indexing for frequent queries (PostgreSQL)
- Data integrity & constraints (CHECK, FK, unique)
- NeonDB branching for testing

#### 3. Testing & Documentation (10%)
- Unit test (PHPUnit) — minimum 70% coverage
- API documentation (Postman/Insomnia/Stoplight)
- Self-testing before PR

#### 4. Learning & Growth (10%)
- Follow learning path (8 weeks)
- Pair programming with Azis (Learning Mentor)
- Code review feedback implementation

### Learning Path (8 Weeks)

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
- ✅ Service Layer pattern — logic in Service, controller only calls service
- ✅ Use Eloquent (raw query only if necessary)
- ✅ Eager loading (`with()`) to prevent N+1
- ✅ Validation in Form Request class
- ✅ Write test before/after code
- ✅ PostgreSQL-native features (JSONB, array, window functions)

### Don'ts
- ❌ Don't commit `.env` or credentials
- ❌ Don't skip validation
- ❌ Don't use N+1 queries in production
- ❌ Don't hardcode credentials
- ❌ Don't put business logic in controllers (must be in Service Layer)

---

## 🎓 Azis — Learning Mentor

**GitHub:** (to be added)

### Primary Responsibilities

Azis is a **Learning Mentor** — not a junior developer working on feature tasks, but rather a **discussion partner, debugging buddy, and concept explainer** for Fathan & Ihsan.

#### 1. Discussion Partner (30%)
- Technical discussion partner for Fathan & Ihsan
- Help resolve technical blockers directly (instead of escalating to Sandikodev)
- Pair programming for tasks that Fathan/Ihsan find difficult

#### 2. Concept Explainer (25%)
- Explain Laravel, React, TypeScript, Inertia, PostgreSQL concepts
- Explain architecture — Service Layer, Sanctum, Spatie RBAC
- Create analogies and examples relevant to the project

#### 3. Code Review Prep (25%)
- Initial review before PR is sent to Sandikodev
- Check for: typos, N+1 queries, logical errors, TypeScript type issues
- Ensure self-checklist is completed

#### 4. Learning Tracker (20%)
- Help maintain learning path progress in Trello tracker
- Facilitate environment setup (Laragon, Bun, PostgreSQL, NeonDB)
- Document common issues & solutions

### Boundaries (What Azis does NOT do)
- ❌ **Does not** make architecture decisions — that is Sandikodev's domain
- ❌ **Does not** perform final code review / approve PR — that is Sandikodev's domain
- ❌ **Does not** manage sprint / backlog — that is Sandikodev & Hanif's domain
- ❌ **Does not** handle stakeholder communication — that is Sandikodev & Hanif's domain

### Key Metrics
- Blocker resolution time for Fathan/Ihsan < 4 hours
- Learning path progress on target
- Fathan & Ihsan becoming more independent (target: independent by the end of Sprint 4)
- Code review iteration < 3x per PR when it reaches Sandikodev

### Do's
- ✅ Pair programming — sit together with Fathan/Ihsan, not just chat
- ✅ Document common issues — create notes in playbook or openkb
- ✅ Ask "what do you think?" before giving answers
- ✅ Escalate to Sandikodev if blocker > 1 day

### Don'ts
- ❌ Don't take feature tasks — not the Learning Mentor's responsibility
- ❌ Don't be a "walking encyclopedia" — teach how to find answers, not give answers
- ❌ Don't bypass Sandikodev for architecture decisions
- ❌ Don't let Fathan/Ihsan become dependent — end goal is independence

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

### Sprint-based Assessment (Every 2 Weeks)

**Criteria:**
1. **Task Completion** (% tasks completed on time)
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
- Able to develop standard features without tight supervision
- Code quality meets standards
- Proactive communication
- Self-debugging capability

---

## 🆘 Escalation Path

```
Problem Level 0 (Quick question / stuck < 30 minutes)
→ Ask Azis (Learning Mentor) — WhatsApp / Discord

Problem Level 1 (Task blocker 30 minutes - 2 hours)
→ Azis helps debugging + discussion

Problem Level 2 (Task blocker > 2 hours)
→ Escalate to Sandikodev via WhatsApp Group

Problem Level 3 (Critical production bug)
→ Escalate to Sandikodev + Pak Mahfud

Problem Level 4 (Requirement ambiguity)
→ Escalate to Ahmad Hanif + Sandikodev
```

---

## 📞 Contact & Availability

| Role | WhatsApp | Email | Working Hours |
|---|---|---|---|
| Sandikodev | [Link](https://wa.me/...) | sandiko@koneksi.id | 09:00 - 18:00 |
| Ahmad Hanif | [Link](https://wa.me/...) | ahmad.hanif@smauiiyk.sch.id | 08:00 - 16:00 (onsite SMA UII) |
| Fathan | [Link](https://wa.me/...) | fathan@koneksi.id | 09:00 - 18:00 |
| Ihsan | [Link](https://wa.me/...) | ihsan@koneksi.id | 09:00 - 18:00 |
| Azis | [Link](https://wa.me/...) | azis@koneksi.id | 09:00 - 18:00 |

**Emergency Contact:**
- Critical production bug: WhatsApp Group + Call Sandikodev
- Server down: Call Sandikodev → Pak Mahfud

---

**Last Updated:** June 2026  
**Maintained by:** Sandikodev
