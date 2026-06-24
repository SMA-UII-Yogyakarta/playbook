# Sprint 2 Plan — Presensi Module

> Sprint 2 (Minggu 3-4): Presensi Siswa & Guru Module

---

## 📋 Sprint Overview

**Duration:** 2 minggu  
**Start Date:** 7 Juli 2026  
**End Date:** 18 Juli 2026  
**Sprint Goal:** Presensi Siswa & Guru berfungsi penuh dengan geolokasi & swafoto

**Theme:** "Core Features"

---

## 🎯 Sprint Goal

**Objective:**
Selesaikan modul presensi untuk siswa (dengan geolokasi & swafoto) dan guru, serta dashboard untuk menampilkan statistik dan riwayat presensi.

**Key Results:**
- [ ] Presensi siswa dengan geolokasi berfungsi
- [ ] Swafoto kamera berfungsi
- [ ] Validasi radius & waktu OK
- [ ] Presensi guru berfungsi
- [ ] Dashboard semua role berfungsi
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

### US-004: Presensi Siswa dengan Geolokasi (8 pts)

**Trello:** [Link ke card](...)

**User Story:**
```
Sebagai siswa SMA UII
Saya ingin melakukan presensi dengan geolokasi dan swafoto
Agar kehadiran saya tercatat dengan valid
```

**Acceptance Criteria:**
```gherkin
Scenario: Presensi berhasil dalam radius
  Given siswa ada di halaman presensi
  And geolokasi dalam radius 50m dari sekolah
  When siswa submit presensi
  Then presensi berhasil disimpan
  And status "On Time" atau "Late"

Scenario: Presensi ditolak di luar radius
  Given siswa ada di halaman presensi
  And geolokasi di luar radius 50m
  When siswa submit presensi
  Then presensi ditolak
  And error message "Anda berada di luar area sekolah"
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #22: Attendance model + migration
- [ ] Issue #23: Geolocation validation service
- [ ] Issue #24: Duplicate check logic
- [ ] Issue #25: Status calculation (On Time/Late)
- [ ] Issue #26: Photo storage (S3-compatible)
- [ ] Issue #27: Unit test validation

Frontend (Fathan):
- [ ] Issue #28: Attendance form (Livewire)
- [ ] Issue #29: Camera preview + capture
- [ ] Issue #30: Geolocation detection
- [ ] Issue #31: Loading states
- [ ] Issue #32: Error handling
- [ ] Issue #33: Success feedback
```

**Dependencies:** US-001 (Authentication) ✅  
**Priority:** 🔥 Critical

---

### US-005: Presensi Guru (5 pts)

**Trello:** [Link ke card](...)

**User Story:**
```
Sebagai guru SMA UII
Saya ingin melakukan presensi kehadiran saya
Agar rekaman kehadiran saya tercatat
```

**Acceptance Criteria:**
```gherkin
Scenario: Guru presensi berhasil
  Given guru ada di halaman presensi
  And geolokasi valid
  When guru submit presensi
  Then presensi berhasil
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

**Trello:** [Link ke card](...)

**User Story:**
```
Sebagai admin/guru/siswa
Saya ingin melihat dashboard dengan statistik presensi
Agar saya dapat melihat ringkasan kehadiran
```

**Acceptance Criteria:**
```gherkin
Scenario: Admin dashboard
  Given admin login
  When admin akses dashboard
  Then admin melihat:
    - Total siswa, guru, staff
    - Kehadiran hari ini
    - Grafik kehadiran

Scenario: Siswa dashboard
  Given siswa login
  When siswa akses dashboard
  Then siswa melihat:
    - Presensi hari ini
    - Riwayat bulan ini
    - Total hadir, sakit, izin, alfa
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #39: Dashboard API (statistics)
- [ ] Issue #40: Attendance history API
- [ ] Issue #41: Chart data API

Frontend (Fathan):
- [ ] Issue #42: Admin dashboard view
- [ ] Issue #43: Student dashboard view
- [ ] Issue #44: Teacher dashboard view
- [ ] Issue #45: Chart component (Chart.js/Alpine)
```

**Dependencies:** US-001 ✅, US-004 ✅  
**Priority:** ⚠️ High

---

## 📅 Sprint Schedule

### Week 3

```
Monday (Day 1):
├─ 09:00-10:30 → Sprint Planning Meeting
├─ 10:30-12:00 → Attendance model + migration (Ihsan)
├─ 13:00-17:00 → Attendance form design (Fathan)

Tuesday (Day 2):
├─ 09:00-12:00 → Geolocation validation (Ihsan)
├─ 13:00-17:00 → Camera integration (Fathan)

Wednesday (Day 3):
├─ 09:00-12:00 → Duplicate check logic (Ihsan)
├─ 13:00-17:00 → Geolocation detection (Fathan)

Thursday (Day 4):
├─ 09:00-12:00 → Photo storage setup (Ihsan)
├─ 13:00-17:00 → Form submission integration (Fathan + Ihsan)

Friday (Day 5):
├─ 09:00-12:00 → Teacher attendance (Ihsan)
├─ 13:00-17:00 → Code review PR #22-30
```

### Week 4

```
Monday (Day 6):
├─ 09:00-12:00 → Dashboard API (Ihsan)
├─ 13:00-17:00 → Admin dashboard view (Fathan)

Tuesday (Day 7):
├─ 09:00-12:00 → Student dashboard API (Ihsan)
├─ 13:00-17:00 → Student dashboard view (Fathan)

Wednesday (Day 8):
├─ 09:00-12:00 → Unit test (Ihsan)
├─ 13:00-17:00 → Responsive testing (Fathan)

Thursday (Day 9):
├─ 09:00-12:00 → Bug fixing
├─ 13:00-17:00 → Deploy staging

Friday (Day 10):
├─ 09:00-12:00 → UAT testing (Ahmad + Pak Mahfud)
├─ 13:00-15:00 → Sprint Review & Demo (MVP Demo!)
├─ 15:00-16:00 → Sprint Retrospective
├─ 16:00-17:00 → Sprint 3 Planning
```

---

## 🎯 MVP Demo (Day 10)

**Attendees:**
- Tim Engineering
- Pak Mahfud (Stakeholder)
- SMA UII Representatives (optional)

**Agenda:**
```
13:00-13:15 → Opening (Sandikodev)
13:15-13:45 → Live Demo:
               - Login
               - Presensi Siswa
               - Presensi Guru
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
## UAT Checklist — Presensi Module

### Presensi Siswa
- [ ] Form loads dengan camera preview
- [ ] Geolocation detected
- [ ] Submit dalam radius → success
- [ ] Submit di luar radius → error
- [ ] Swafoto captured
- [ ] Duplicate prevented
- [ ] Riwayat tampil

### Presensi Guru
- [ ] Form loads
- [ ] Submit berhasil
- [ ] Duplicate prevented

### Dashboard
- [ ] Admin dashboard loads
- [ ] Student dashboard loads
- [ ] Teacher dashboard loads
- [ ] Statistik correct
- [ ] Responsive di mobile
```

---

## ✅ Definition of Done

```markdown
✅ Code complete (semua task selesai)
✅ Unit test written (>70% coverage)
✅ Feature test written
✅ Code review approved
✅ PR merged ke main
✅ UAT passed
✅ Deploy staging
✅ MVP Demo successful
✅ No critical/open bugs
```

---

## 🎉 MVP Success Criteria

**Functional:**
```
✅ Login/Logout berfungsi
✅ Presensi Siswa berfungsi
✅ Presensi Guru berfungsi
✅ Dashboard semua role berfungsi
✅ Export laporan basic berfungsi
```

**Non-Functional:**
```
✅ Performance OK (< 3 detik)
✅ Security OK (no critical vulnerability)
✅ Responsive di mobile
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

**Next:** [`sprint-3-plan.md`](sprint-3-plan.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev