# Sprint Planning Template

> Template untuk Sprint Planning meeting setiap 2 minggu.

---

## 📋 Pre-Planning Preparation

### Product Analyst (Ahmad Hanif)

**Deadline:** H-1 Sprint Planning

```markdown
## Backlog Ready Checklist

- [ ] User story untuk Sprint berikutnya sudah ditulis
- [ ] Acceptance criteria jelas & testable
- [ ] Priority assigned (Critical, High, Medium, Low)
- [ ] Dependencies identified
- [ ] Trello card updated
- [ ] Stakeholder alignment (Pak Mahfud)
```

---

### Tech Lead (Sandikodev)

**Deadline:** H-1 Sprint Planning

```markdown
## Technical Breakdown Checklist

- [ ] User story di-breakdown jadi technical task
- [ ] GitHub Issue dibuat untuk setiap task
- [ ] Technical feasibility confirmed
- [ ] Architecture decision documented (jika perlu)
- [ ] Risk identified
```

---

## 📅 Sprint Planning Agenda

**Duration:** 60-90 menit  
**Attendees:** Sandikodev, Ahmad Hanif, Fathan, Ihsan  
**Facilitator:** Sandikodev

---

### 1. Review Previous Sprint (15 menit)

**Template:**

```markdown
## Sprint [X] Review

### Metrics

| Metric | Target | Actual | Status |
|---|---|---|---|
| Velocity | 13 pts | 11 pts | ⚠️ |
| Completed Tasks | 8 | 7 | ⚠️ |
| Bug Count | < 3 | 2 | ✅ |
| PR Review Time | < 24h | 18h | ✅ |

### Completed

✅ Task 1 (Issue #12)  
✅ Task 2 (Issue #15)  
✅ Task 3 (Issue #18)

### Incomplete

❌ Task 4 (Issue #20) — Blocker: API documentation belum ready  
❌ Task 5 (Issue #22) — Developer sick leave

### Learnings

😊 Went Well:
- Code review lebih cepat
- Communication lancar

🤔 To Improve:
- Task estimation meleset
- Blocker lama tidak di-escalate
```

---

### 2. Present Sprint Goal (10 menit)

**Template:**

```markdown
## Sprint [X+1] Goal

**Theme:** [Sprint theme, e.g., "Presensi Module"]

**Objective:**
Selesaikan fitur presensi siswa dengan geolokasi & swafoto

**Key Results:**
- [ ] API presensi selesai
- [ ] Frontend form presensi selesai
- [ ] UAT passed
- [ ] Deploy staging
```

---

### 3. Backlog Review (15 menit)

**Presenter:** Ahmad Hanif

```markdown
## Backlog Items

### Priority 1 (Critical)
- SMART-012: Presensi Siswa dengan Geolokasi (8 story points)
- SMART-013: Presensi Guru (5 story points)

### Priority 2 (High)
- SMART-014: Dashboard Admin (5 story points)
- SMART-015: Export Laporan (3 story points)

### Priority 3 (Medium)
- SMART-016: Notifikasi WhatsApp (8 story points) — Defer to Sprint 3
```

---

### 4. Estimation (30 menit)

**Planning Poker:**

```
1 — Tiny (1-2 jam)
2 — Small (0.5 hari)
3 — Medium (1 hari)
5 — Large (2-3 hari)
8 — XL (1 sprint)
13 — Too big, break down
```

**Template:**

```markdown
## Estimation Sheet

| Task | Fathan | Ihsan | Sandikodev | Final |
|---|---|---|---|---|
| API Presensi | 5 | 5 | 5 | 5 |
| Form Presensi | 3 | 5 | 3 | 3 |
| Geolocation | 3 | 3 | 3 | 3 |
| Camera Integration | 3 | - | 3 | 3 |
| **Total** | | | | **14 pts** |
```

---

### 5. Capacity Planning (10 menit)

**Template:**

```markdown
## Capacity

### Team Capacity

| Developer | Available Days | Capacity (pts) |
|---|---|---|
| Fathan | 10 days | 7 pts |
| Ihsan | 10 days | 7 pts |
| **Total** | | **14 pts** |

### Sprint Commitment

Total capacity: 14 points  
Committed: 14 points  
Buffer: 0 points

✅ Capacity OK
```

---

### 6. Task Assignment (10 menit)

**Template:**

```markdown
## Task Assignment

### Fathan (Frontend)
- [ ] Issue #34: Form Presensi React + Inertia (3 pts)
- [ ] Issue #35: Camera Integration (3 pts)
- [ ] Issue #36: Responsive Design (1 pt)

### Ihsan (Backend)
- [ ] Issue #30: API Presensi (5 pts)
- [ ] Issue #31: Geolocation Validation (3 pts)
- [ ] Issue #32: Duplicate Prevention (2 pts)

### Ahmad Hanif (UAT)
- [ ] UAT Presensi Siswa
- [ ] UAT Presensi Guru
- [ ] Documentation update
```

---

## 📊 Sprint Backlog

**Final Template:**

```markdown
# Sprint [X] Backlog

**Sprint Goal:** [Goal]

**Duration:** [Start Date] - [End Date]

**Team Capacity:** [X] story points

---

## User Stories

### SMART-012: Presensi Siswa (8 pts)

**Issues:**
- #30: API Presensi (Backend - Ihsan)
- #31: Geolocation Validation (Backend - Ihsan)
- #34: Form Presensi React + Inertia (Frontend - Fathan)
- #35: Camera Integration (Frontend - Fathan)

**Acceptance Criteria:**
- [ ] Siswa dapat submit presensi
- [ ] Geolokasi validated
- [ ] Swafoto wajib
- [ ] Duplicate prevented

---

## Definition of Ready

- [ ] Semua user story jelas
- [ ] Acceptance criteria defined
- [ ] Technical approach confirmed
- [ ] Dependencies resolved

---

## Definition of Done

- [ ] Semua task completed
- [ ] UAT passed
- [ ] Deploy staging
- [ ] Sprint review scheduled

---

## Risks & Mitigation

| Risk | Impact | Probability | Mitigation |
|---|---|---|---|
| API documentation delay | High | Medium | Sandikodev review early |
| Camera API browser compatibility | Medium | Low | Test di multiple browser |
```

---

## 🎯 Sprint Commitment

**Template:**

```markdown
## Team Commitment

Kami, tim engineering SMART Absen, berkomitmen untuk menyelesaikan Sprint [X] dengan target:

**Velocity:** [X] story points  
**Quality:** Bug count < 3  
**Timeline:** [Start] - [End]

**Signed:**
- [ ] Sandikodev
- [ ] Ahmad Hanif
- [ ] Fathan Mubina
- [ ] Ihsan

**Date:** [Date]
```

---

## 📱 Post-Planning Actions

### Sandikodev

```markdown
- [ ] Update GitHub Project board
- [ ] Assign Issues ke developer
- [ ] Move card Trello ke "In Development"
- [ ] Setup sprint milestone di GitHub
```

---

### Developer (Fathan/Ihsan)

```markdown
- [ ] Review Issue yang di-assign
- [ ] Buat branch untuk task pertama
- [ ] Start development
- [ ] Update WhatsApp: "Sprint [X] started, working on Issue #..."
```

---

### Ahmad Hanif

```markdown
- [ ] Update Trello card status
- [ ] Prepare UAT checklist
- [ ] Schedule stakeholder demo (end of sprint)
```

---

## 📊 Sprint Tracking

### Daily Standup Update

```markdown
## Daily Standup — Day [X]

**Sprint Progress:**
- Completed: 3/14 tasks (21%)
- In Progress: 2 tasks
- Blocker: None

**Burndown:**
Day 1: 14 pts → 14 pts  
Day 2: 14 pts → 11 pts  
Day 3: 14 pts → 8 pts
```

---

### Mid-Sprint Check (Day 5)

```markdown
## Mid-Sprint Check

**On Track:**
- ✅ API Presensi (Ihsan)
- ✅ Form Presensi (Fathan)

**At Risk:**
- ⚠️ Camera Integration (Fathan) — 50% complete, need 2 more days

**Action:**
- Sandikodev pair programming dengan Fathan (Day 6)
```

---

**Next:** Sprint Execution (Daily Standup, Development, Code Review)

---

**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev