# Sprint 2 Plan — Attendance Module

> Sprint 2 (Weeks 3-4): Student & Teacher Attendance Module

---

## 📋 Sprint Overview

**Duration:** 2 weeks  
**Start Date:** July 14, 2026  
**End Date:** July 25, 2026  
**Sprint Goal:** Student & Teacher Attendance fully working with geolocation & selfie

**Theme:** "Core Features — Inertia + React"

---

## 🎯 Sprint Goal

**Objective:**
Complete the attendance module for students (with geolocation & selfie) and teachers, along with dashboards to display attendance statistics and history.

**Key Results:**
- [ ] Student attendance with geolocation working
- [ ] Camera selfie working
- [ ] Radius & time validation OK
- [ ] Teacher attendance working
- [ ] All role dashboards working
- [ ] UAT passed
- [ ] Deploy staging → MVP Ready

---

## 📊 Capacity

**Team:**
- Fathan (Frontend): 10 days → 7 story points
- Ihsan (Backend): 10 days → 7 story points
- **Total Capacity:** 14 story points

**Committed:** 14 story points  
**Buffer:** 0 story points

---

## 📦 User Stories

### US-004: Student Attendance with Geolocation (8 pts)

**Trello:** [Link to card](...)

**User Story:**
```
As a SMA UII student
I want to do attendance with geolocation and selfie
So that my attendance is recorded validly
```

**Acceptance Criteria:**
```gherkin
Scenario: Attendance successful within radius
  Given student is on the attendance page
  And geolocation within 50m radius from school
  When student submits attendance
  Then attendance is saved successfully
  And status "On Time" or "Late"

Scenario: Attendance rejected outside radius
  Given student is on the attendance page
  And geolocation outside 50m radius
  When student submits attendance
  Then attendance is rejected
  And error message "You are outside the school area"
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #22: Attendance model + migration (PostgreSQL)
- [ ] Issue #23: PresensiService (geolocation validation)
- [ ] Issue #24: Duplicate check logic (Service Layer)
- [ ] Issue #25: Status calculation (On Time/Late)
- [ ] Issue #26: Photo upload to S3 (Wasabi/MinIO)
- [ ] Issue #27: Unit test validation

Frontend (Fathan):
- [ ] Issue #28: Attendance form (React + Inertia)
- [ ] Issue #29: Camera preview + capture (getUserMedia)
- [ ] Issue #30: Geolocation detection (navigator.geolocation)
- [ ] Issue #31: Loading states (React state)
- [ ] Issue #32: Error handling (TypeScript union type)
- [ ] Issue #33: Success feedback

Learning Mentor (Azis):
- [ ] Issue #L4: Debugging camera & geolocation integration
- [ ] Issue #L5: Pair programming photo upload S3
```

**Dependencies:** US-001 (Authentication) ✅, Spatie RBAC ✅  
**Priority:** 🔥 Critical

---

### US-005: Teacher Attendance (5 pts)

**Trello:** [Link to card](...)

**User Story:**
```
As a SMA UII teacher
I want to record my attendance
So that my attendance record is logged
```

**Acceptance Criteria:**
```gherkin
Scenario: Teacher attendance successful
  Given teacher is on the attendance page
  And geolocation valid
  When teacher submits attendance
  Then attendance is successful
  And status calculated
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #34: Teacher attendance endpoint
- [ ] Issue #35: Reuse geolocation service
- [ ] Issue #36: Unit test

Frontend (Fathan):
- [ ] Issue #37: Teacher attendance form
- [ ] Issue #38: Simplified UI (no camera optional)
```

**Dependencies:** US-001 ✅  
**Priority:** ⚠️ High

---

### US-006: Dashboard All Roles (6 pts)

**Trello:** [Link to card](...)

**User Story:**
```
As an admin/teacher/student
I want to see a dashboard with attendance statistics
So that I can view attendance summary
```

**Acceptance Criteria:**
```gherkin
Scenario: Admin dashboard
  Given admin login
  When admin accesses dashboard
  Then admin sees:
    - Total students, teachers, staff
    - Today's attendance
    - Attendance chart

Scenario: Student dashboard
  Given student login
  When student accesses dashboard
  Then student sees:
    - Today's attendance
    - Monthly history
    - Total present, sick, permission, absent
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #39: Dashboard API via Inertia shared data
- [ ] Issue #40: Attendance history API endpoint
- [ ] Issue #41: Chart data (JSON) from Service Layer

Frontend (Fathan):
- [ ] Issue #42: Admin dashboard (React + Inertia page)
- [ ] Issue #43: Student dashboard (React + Tailwind)
- [ ] Issue #44: Teacher dashboard
- [ ] Issue #45: Chart component (Recharts / Chart.js + React)
```

**Dependencies:** US-001 ✅, US-004 ✅  
**Priority:** ⚠️ High

---

## 📅 Sprint Schedule

### Week 3 — Attendance Core

```
Monday (Day 1):
├─ 09:00-10:30 → Sprint Planning Meeting
├─ 10:30-12:00 → Attendance model + migration PostgreSQL (Ihsan + Azis)
├─ 13:00-17:00 → Attendance form design React (Fathan + Azis)

Tuesday (Day 2):
├─ 09:00-12:00 → PresensiService geolocation validation (Ihsan)
├─ 13:00-17:00 → Camera preview + capture (Fathan)

Wednesday (Day 3):
├─ 09:00-12:00 → Duplicate check + status calculation (Ihsan)
├─ 13:00-17:00 → Geolocation detection + form integration (Fathan)

Thursday (Day 4):
├─ 09:00-12:00 → Photo upload to S3 (Ihsan + Azis)
├─ 13:00-17:00 → Full form submission integration (Fathan + Ihsan)

Friday (Day 5):
├─ 09:00-12:00 → Teacher attendance endpoint (Ihsan)
├─ 13:00-17:00 → Code review + testing (Azis → Sandikodev)
```

### Week 4 — Dashboard & MVP Demo

```
Monday (Day 6):
├─ 09:00-12:00 → Dashboard API + Inertia shared data (Ihsan)
├─ 13:00-17:00 → Admin dashboard React view (Fathan)

Tuesday (Day 7):
├─ 09:00-12:00 → Student/Teacher dashboard API (Ihsan)
├─ 13:00-17:00 → Dashboard views + chart component (Fathan)

Wednesday (Day 8):
├─ 09:00-12:00 → Unit test + feature test (Ihsan + Azis)
├─ 13:00-17:00 → Responsive testing + TypeScript fixes (Fathan + Azis)

Thursday (Day 9):
├─ 09:00-12:00 → Bug fixing
├─ 13:00-17:00 → Deploy staging + integration test

Friday (Day 10):
├─ 09:00-12:00 → UAT testing (Ahmad + Pak Mahfud)
├─ 13:00-15:00 → Sprint Review & Demo (MVP Demo!)
├─ 15:00-16:00 → Sprint Retrospective
├─ 16:00-17:00 → Sprint 3 Planning
```

---

## 🎯 MVP Demo (Day 10)

**Attendees:**
- Engineering Team
- Pak Mahfud (Stakeholder)
- SMA UII Representatives (optional)

**Agenda:**
```
13:00-13:15 → Opening (Sandikodev)
13:15-13:45 → Live Demo:
               - Login
               - Student Attendance
               - Teacher Attendance
               - Dashboard
13:45-14:15 → Feedback Session
14:15-14:30 → Next Steps (Sprint 3-4)
14:30-15:00 → Q&A
```

---

## 🧪 Testing Plan

### Unit Tests (Ihsan)

```php
// AttendanceTest.php
- test_student_can_submit_attendance
- test_duplicate_attendance_prevented
- test_attendance_outside_radius_rejected
- test_attendance_status_calculation

// GeolocationTest.php
- test_coordinates_within_radius
- test_coordinates_outside_radius
```

### Feature Tests

```php
// AttendanceFlowTest.php
- test_attendance_form_loads
- test_attendance_submission_success
- test_attendance_submission_outside_radius
```

### UAT Checklist (Ahmad Hanif)

```markdown
## UAT Checklist — Attendance Module

### Student Attendance
- [ ] Form loads with camera preview
- [ ] Geolocation detected
- [ ] Submit within radius → success
- [ ] Submit outside radius → error
- [ ] Selfie captured
- [ ] Duplicate prevented
- [ ] History displayed

### Teacher Attendance
- [ ] Form loads
- [ ] Submit successful
- [ ] Duplicate prevented

### Dashboard
- [ ] Admin dashboard loads
- [ ] Student dashboard loads
- [ ] Teacher dashboard loads
- [ ] Statistics correct
- [ ] Responsive on mobile
```

---

## ✅ Definition of Done

```markdown
✅ Code complete (all tasks completed)
✅ Unit test written (>70% coverage)
✅ Feature test written
✅ Code review approved
✅ PR merged to main
✅ UAT passed
✅ Deploy staging
✅ MVP Demo successful
✅ No critical/open bugs
```

---

## 🎉 MVP Success Criteria

**Functional:**
```
✅ Login/Logout working
✅ Student Attendance working
✅ Teacher Attendance working
✅ All role dashboards working
✅ Basic report export working
```

**Non-Functional:**
```
✅ Performance OK (< 3 seconds)
✅ Security OK (no critical vulnerability)
✅ Responsive on mobile
✅ Uptime > 95% (staging)
```

**Business:**
```
✅ Stakeholder demo successful
✅ Pak Mahfud approved
✅ Ready for production deployment (Sprint 4)
```

---

## 🔗 Related Links

- [GitHub Project](https://github.com/orgs/SMA-UII-Yogyakarta/projects/1)
- [GitHub Issues Sprint 2](https://github.com/SMA-UII-Yogyakarta/core/issues?q=is%3Aissue+milestone%3A%22Sprint+2%22)
- [Sprint 1 Plan](sprint-1-plan.md)
- [MVP Scope](mvp-scope.md)

---

**Next:** *Sprint 3 — not yet available*  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
