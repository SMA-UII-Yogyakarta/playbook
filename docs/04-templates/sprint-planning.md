# Sprint Planning Template

> Template for Sprint Planning meeting every 2 weeks.

---

## 📋 Pre-Planning Preparation

### Product Analyst (Ahmad Hanif)

**Deadline:** H-1 Sprint Planning

```markdown
## Backlog Ready Checklist

- [ ] User story for next Sprint has been written
- [ ] Acceptance criteria clear & testable
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

- [ ] User story broken down into technical tasks
- [ ] GitHub Issue created for each task
- [ ] Technical feasibility confirmed
- [ ] Architecture decision documented (if needed)
- [ ] Risk identified
```

---

## 📅 Sprint Planning Agenda

**Duration:** 60-90 minutes  
**Attendees:** Sandikodev, Ahmad Hanif, Fathan, Ihsan  
**Facilitator:** Sandikodev

---

### 1. Review Previous Sprint (15 minutes)

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

❌ Task 4 (Issue #20) — Blocker: API documentation not ready yet  
❌ Task 5 (Issue #22) — Developer sick leave

### Learnings

😊 Went Well:
- Code review faster
- Communication smooth

🤔 To Improve:
- Task estimation off target
- Blocker not escalated early
```

---

### 2. Present Sprint Goal (10 minutes)

**Template:**

```markdown
## Sprint [X+1] Goal

**Theme:** [Sprint theme, e.g., "Presensi Module"]

**Objective:**
Complete the student attendance feature with geolocation & selfie

**Key Results:**
- [ ] Attendance API completed
- [ ] Attendance frontend form completed
- [ ] UAT passed
- [ ] Deploy staging
```

---

### 3. Backlog Review (15 minutes)

**Presenter:** Ahmad Hanif

```markdown
## Backlog Items

### Priority 1 (Critical)
- SMART-012: Student Attendance with Geolocation (8 story points)
- SMART-013: Teacher Attendance (5 story points)

### Priority 2 (High)
- SMART-014: Admin Dashboard (5 story points)
- SMART-015: Export Report (3 story points)

### Priority 3 (Medium)
- SMART-016: WhatsApp Notification (8 story points) — Defer to Sprint 3
```

---

### 4. Estimation (30 minutes)

**Planning Poker:**

```
1 — Tiny (1-2 hours)
2 — Small (0.5 day)
3 — Medium (1 day)
5 — Large (2-3 days)
8 — XL (1 sprint)
13 — Too big, break down
```

**Template:**

```markdown
## Estimation Sheet

| Task | Fathan | Ihsan | Sandikodev | Final |
|---|---|---|---|---|
| Attendance API | 5 | 5 | 5 | 5 |
| Attendance Form | 3 | 5 | 3 | 3 |
| Geolocation | 3 | 3 | 3 | 3 |
| Camera Integration | 3 | - | 3 | 3 |
| **Total** | | | | **14 pts** |
```

---

### 5. Capacity Planning (10 minutes)

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

### 6. Task Assignment (10 minutes)

**Template:**

```markdown
## Task Assignment

### Fathan (Frontend)
- [ ] Issue #34: Attendance Form React + Inertia (3 pts)
- [ ] Issue #35: Camera Integration (3 pts)
- [ ] Issue #36: Responsive Design (1 pt)

### Ihsan (Backend)
- [ ] Issue #30: Attendance API (5 pts)
- [ ] Issue #31: Geolocation Validation (3 pts)
- [ ] Issue #32: Duplicate Prevention (2 pts)

### Ahmad Hanif (UAT)
- [ ] UAT Student Attendance
- [ ] UAT Teacher Attendance
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

### SMART-012: Student Attendance (8 pts)

**Issues:**
- #30: Attendance API (Backend - Ihsan)
- #31: Geolocation Validation (Backend - Ihsan)
- #34: Attendance Form React + Inertia (Frontend - Fathan)
- #35: Camera Integration (Frontend - Fathan)

**Acceptance Criteria:**
- [ ] Student can submit attendance
- [ ] Geolocation validated
- [ ] Selfie mandatory
- [ ] Duplicate prevented

---

## Definition of Ready

- [ ] All user stories clear
- [ ] Acceptance criteria defined
- [ ] Technical approach confirmed
- [ ] Dependencies resolved

---

## Definition of Done

- [ ] All tasks completed
- [ ] UAT passed
- [ ] Deploy staging
- [ ] Sprint review scheduled

---

## Risks & Mitigation

| Risk | Impact | Probability | Mitigation |
|---|---|---|---|
| API documentation delay | High | Medium | Sandikodev review early |
| Camera API browser compatibility | Medium | Low | Test on multiple browsers |
```

---

## 🎯 Sprint Commitment

**Template:**

```markdown
## Team Commitment

We, the SMART Absen engineering team, commit to completing Sprint [X] with the target:

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
- [ ] Assign Issues to developer
- [ ] Move Trello card to "In Development"
- [ ] Setup sprint milestone in GitHub
```

---

### Developer (Fathan/Ihsan)

```markdown
- [ ] Review assigned Issues
- [ ] Create branch for first task
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
- ✅ Attendance API (Ihsan)
- ✅ Attendance Form (Fathan)

**At Risk:**
- ⚠️ Camera Integration (Fathan) — 50% complete, need 2 more days

**Action:**
- Sandikodev pair programming with Fathan (Day 6)
```

---

**Next:** Sprint Execution (Daily Standup, Development, Code Review)

---

**Last Updated:** June 2026  
**Maintained by:** Sandikodev
