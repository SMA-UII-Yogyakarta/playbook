# Sprint 1 Plan — Authentication & SSO

> Sprint 1 (Minggu 1-2): Authentication & Authorization System

---

## 📋 Sprint Overview

**Duration:** 2 minggu  
**Start Date:** 24 Juni 2026  
**End Date:** 5 Juli 2026  
**Sprint Goal:** Login, Logout, Role Management berfungsi penuh

**Theme:** "Foundation & Security"

---

## 🎯 Sprint Goal

**Objective:**
Selesaikan sistem authentication dengan Laravel Sanctum untuk SSO (Single Sign-On) yang akan digunakan di semua modul SMART Absen.

**Key Results:**
- [ ] Login dengan email & password berfungsi
- [ ] Logout berfungsi
- [ ] Role-based access control (RBAC) berfungsi
- [ ] Session management OK
- [ ] Middleware protection untuk route
- [ ] UAT passed
- [ ] Deploy staging

---

## 📊 Capacity

**Team:**
- Fathan (Frontend): 10 days → 7 story points
- Ihsan (Backend): 10 days → 7 story points
- **Total Capacity:** 14 story points

**Committed:** 13 story points  
**Buffer:** 1 story point

---

## 📦 User Stories

### US-001: Login dengan Email & Password (5 pts)

**Trello:** [Link ke card](...)

**User Story:**
```
Sebagai guru atau staff SMA UII
Saya ingin login dengan email dan password
Agar saya dapat mengakses sistem SMART Absen
```

**Acceptance Criteria:**
```gherkin
Scenario: Login dengan credentials valid
  Given user ada di halaman login
  When user input email valid
  And user input password valid
  Then user di-redirect ke dashboard
  And user melihat welcome message

Scenario: Login dengan credentials invalid
  Given user ada di halaman login
  When user input email atau password salah
  Then user melihat error "Email atau password salah"
  And user tetap di halaman login
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #1: Setup Laravel Sanctum
- [ ] Issue #2: Buat User model dengan role
- [ ] Issue #3: Login API endpoint (POST /api/login)
- [ ] Issue #4: Logout API endpoint (POST /api/logout)
- [ ] Issue #5: Unit test untuk authentication

Frontend (Fathan):
- [ ] Issue #6: Login page (Blade + Livewire)
- [ ] Issue #7: Form validation
- [ ] Issue #8: Error handling
- [ ] Issue #9: Redirect setelah login
- [ ] Issue #10: Responsive design
```

**Dependencies:** None  
**Priority:** 🔥 Critical

---

### US-002: Logout (3 pts)

**Trello:** [Link ke card](...)

**User Story:**
```
Sebagai user yang sudah login
Saya ingin logout dari sistem
Agar sesi saya berakhir dan aman
```

**Acceptance Criteria:**
```gherkin
Scenario: Logout berhasil
  Given user sudah login
  When user klik tombol "Logout"
  Then sesi user di-destroy
  And user di-redirect ke halaman login
  And user melihat message "Anda telah logout"
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #11: Revoke Sanctum token di logout
- [ ] Issue #12: Clear session

Frontend (Fathan):
- [ ] Issue #13: Logout button di navbar
- [ ] Issue #14: Confirmation modal (optional)
- [ ] Issue #15: Redirect setelah logout
```

**Dependencies:** US-001 ✅  
**Priority:** 🔥 Critical

---

### US-003: Role-Based Access Control (5 pts)

**Trello:** [Link ke card](...)

**User Story:**
```
Sebagai system administrator
Saya ingin membatasi akses berdasarkan role user
Agar setiap user hanya dapat mengakses fitur yang sesuai
```

**Acceptance Criteria:**
```gherkin
Scenario: Admin dapat akses admin panel
  Given user dengan role "admin" sudah login
  When user akses route "/admin"
  Then user dapat akses halaman admin

Scenario: Siswa tidak dapat akses admin panel
  Given user dengan role "siswa" sudah login
  When user akses route "/admin"
  Then user mendapat error 403 Forbidden
```

**Roles:**
```
admin  → Full access
guru   → Dashboard guru, presensi sendiri, jadwal mengajar
siswa  → Dashboard siswa, presensi sendiri, riwayat
staff  → Dashboard staff, laporan
```

**Tasks:**
```
Backend (Ihsan):
- [ ] Issue #16: Role enum di User model
- [ ] Issue #17: Middleware untuk role check
- [ ] Issue #18: Policy untuk setiap resource
- [ ] Issue #19: Unit test untuk role access

Frontend (Fathan):
- [ ] Issue #20: Hide/show menu berdasarkan role
- [ ] Issue #21: 403 page (Blade view)
```

**Dependencies:** US-001 ✅  
**Priority:** ⚠️ High

---

## 📅 Sprint Schedule

### Week 1

```
Monday (Day 1):
├─ 09:00-10:30 → Sprint Planning Meeting
├─ 10:30-12:00 → Setup environment & Sanctum (Ihsan)
├─ 13:00-15:00 → Login page design (Fathan)
├─ 15:00-17:00 → User model + role (Ihsan)

Tuesday (Day 2):
├─ 09:00-12:00 → Login API endpoint (Ihsan)
├─ 13:00-17:00 → Login form Livewire (Fathan)

Wednesday (Day 3):
├─ 09:00-12:00 → Login form validation (Fathan)
├─ 13:00-17:00 → Login integration test (Ihsan + Fathan)

Thursday (Day 4):
├─ 09:00-12:00 → Logout endpoint (Ihsan)
├─ 13:00-17:00 → Logout button + integration (Fathan)

Friday (Day 5):
├─ 09:00-12:00 → Role middleware (Ihsan)
├─ 13:00-17:00 → Code review PR #1-10
```

### Week 2

```
Monday (Day 6):
├─ 09:00-12:00 → Role policy (Ihsan)
├─ 13:00-17:00 → Menu role-based (Fathan)

Tuesday (Day 7):
├─ 09:00-12:00 → Unit test authentication (Ihsan)
├─ 13:00-17:00 → Responsive testing (Fathan)

Wednesday (Day 8):
├─ 09:00-12:00 → Bug fixing
├─ 13:00-17:00 → Bug fixing

Thursday (Day 9):
├─ 09:00-12:00 → UAT preparation (Ahmad)
├─ 13:00-17:00 → Deploy staging

Friday (Day 10):
├─ 09:00-12:00 → UAT testing (Ahmad)
├─ 13:00-15:00 → Sprint Review & Demo
├─ 15:00-16:00 → Sprint Retrospective
├─ 16:00-17:00 → Sprint 2 Planning
```

---

## 🧪 Testing Plan

### Unit Tests (Ihsan)

```php
// AuthenticationTest.php
- test_user_can_login
- test_user_cannot_login_with_invalid_credentials
- test_user_can_logout
- test_session_destroyed_after_logout

// RoleTest.php
- test_admin_can_access_admin_panel
- test_siswa_cannot_access_admin_panel
- test_guru_can_access_guru_dashboard
```

### Feature Tests (Fathan + Ihsan)

```php
// LoginFlowTest.php
- test_login_page_loads
- test_login_form_validation
- test_login_success_redirects_to_dashboard
- test_logout_redirects_to_login

// RoleBasedAccessTest.php
- test_menu_shows_based_on_role
- test_403_for_unauthorized_access
```

### UAT Checklist (Ahmad Hanif)

```markdown
## UAT Checklist — Authentication

### Login
- [ ] Login page loads (< 2 detik)
- [ ] Form validation (email required, password required)
- [ ] Login dengan valid credentials → dashboard
- [ ] Login dengan invalid credentials → error message
- [ ] Responsive di mobile

### Logout
- [ ] Logout button visible setelah login
- [ ] Klik logout → redirect ke login
- [ ] Session destroyed (tidak bisa akses dashboard tanpa login)

### Role Access
- [ ] Admin dapat akses /admin
- [ ] Siswa tidak dapat akses /admin (403)
- [ ] Menu sesuai role
```

---

## 📊 Definition of Ready

```markdown
✅ User story lengkap
✅ Acceptance criteria jelas & testable
✅ Technical breakdown done
✅ Dependencies resolved
✅ Story points assigned
```

---

## 📊 Definition of Done

```markdown
✅ Code complete (semua task selesai)
✅ Unit test written (>70% coverage)
✅ Feature test written
✅ Code review approved (Sandikodev)
✅ PR merged ke main
✅ UAT passed (Ahmad Hanif)
✅ Deploy staging
✅ No critical/open bugs
✅ Documentation updated
```

---

## 🚫 Risks & Mitigation

| Risk | Impact | Probability | Mitigation |
|---|---|---|---|
| Sanctum setup complex | Medium | Low | Sandikodev pair programming |
| Role logic bug | High | Medium | Unit test comprehensive |
| UI tidak responsive | Medium | Low | Early testing di multiple devices |
| UAT finding critical bug | High | Low | Early UAT (Day 8) |

---

## 📈 Success Criteria

**Sprint Success:**
```
✅ Semua user story completed (13/13 pts)
✅ UAT passed (no critical bugs)
✅ Deploy staging successful
✅ Velocity tracked untuk Sprint 2
```

**Individual Success:**
```
Fathan:
✅ Livewire component mastery
✅ Form validation OK
✅ Responsive design OK

Ihsan:
✅ Sanctum authentication OK
✅ Role middleware OK
✅ Unit test OK
```

---

## 📞 Daily Standup Schedule

**Time:** 09:00 WIB (setiap hari)  
**Duration:** 15 menit  
**Channel:** WhatsApp Group

**Format:**
```
📅 Daily Standup — Day [X]
👤 [Nama]

✅ Kemarin:
- Task 1
- Task 2

🎯 Hari ini:
- Task 1
- Task 2

🚫 Blocker:
- [Deskripsi atau "None"]
```

---

## 🔗 Related Links

- [GitHub Project](https://github.com/orgs/SMA-UII-Yogyakarta/projects/1)
- [Trello Board](https://trello.com/b/...)
- [GitHub Issues](https://github.com/SMA-UII-Yogyakarta/core/issues?q=is%3Aissue+milestone%3A%22Sprint+1%22)
- [User Story Template](../04-templates/user-story.md)

---

**Next:** [`sprint-2-plan.md`](sprint-2-plan.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev