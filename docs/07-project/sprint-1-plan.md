# Sprint 1 Plan — Authentication & SSO

> Sprint 1 (Minggu 1-2): Setup & Authentication Foundation

---

## 📋 Sprint Overview

**Duration:** 2 minggu  
**Start Date:** 30 Juni 2026  
**End Date:** 11 Juli 2026  
**Sprint Goal:** Stack ter-install & running, Learning path berjalan, Auth dasar berfungsi

**Theme:** "Reset & Foundation"

---

## 🎯 Sprint Goal

**Objective:**
Setup foundation: install stack baru (Bun, PostgreSQL/NeonDB, Sanctum, Spatie), sinkronisasi dokumentasi, dan membangun auth dasar.

**Key Results:**
- [ ] Semua dokumentasi (playbook, aksesekolah, core) sinkron dengan stack aktual
- [ ] Bun, Vite 8, InertiaJS + React berjalan di local
- [ ] PostgreSQL/NeonDB terhubung
- [ ] Laravel Sanctum + Spatie Permission ter-install
- [ ] Login dengan email & password berfungsi (Inertia + React)
- [ ] Logout berfungsi
- [ ] Role-based access control (RBAC) berfungsi
- [ ] Fathan & Ihsan paham dasar React/TypeScript
- [ ] Azis onboarding completed

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
- [ ] Issue #1: Setup Laravel Sanctum + Spatie Permission
- [ ] Issue #2: Buat User model + migration (PostgreSQL)
- [ ] Issue #3: Buat AuthService (login, register, logout — Service Layer)
- [ ] Issue #4: Login Web controller (Controllers/Web/AuthController)
- [ ] Issue #5: Unit test untuk authentication

Frontend (Fathan):
- [ ] Issue #6: Login page (React + Inertia + Tailwind)
- [ ] Issue #7: TypeScript types untuk auth (User, LoginPayload, AuthResponse)
- [ ] Issue #8: Form validation + error display
- [ ] Issue #9: Redirect setelah login (Inertia router)
- [ ] Issue #10: Responsive design (mobile-first)

Learning Mentor (Azis):
- [ ] Issue #L1: Fasilitasi setup environment Fathan & Ihsan
- [ ] Issue #L2: Pair programming React dasar + TypeScript untuk Fathan
- [ ] Issue #L3: Pair programming Service Layer + Sanctum untuk Ihsan
```

**Dependencies:** Setup environment (Bun, PostgreSQL, Vite)  
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
- [ ] Issue #11: Tambah method logout di AuthService
- [ ] Issue #12: Clear session + revoke token (Sanctum)

Frontend (Fathan):
- [ ] Issue #13: Logout button di navbar (React component)
- [ ] Issue #14: Confirmation modal (optional)
- [ ] Issue #15: Redirect setelah logout via Inertia
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
- [ ] Issue #16: Setup Spatie Permission — seeder role & permission
- [ ] Issue #17: Middleware role + permission (Spatie middleware)
- [ ] Issue #18: Policy untuk setiap resource
- [ ] Issue #19: Unit test untuk role access

Frontend (Fathan):
- [ ] Issue #20: Hide/show menu berdasarkan role (Inertia shared data)
- [ ] Issue #21: 403 page (React component)
```

**Dependencies:** US-001 ✅  
**Priority:** ⚠️ High

---

## 📅 Sprint Schedule

> **Catatan:** Sprint 1 difokuskan pada setup stack baru dan learning. Fathan & Ihsan perlu waktu untuk adaptasi ke React/TypeScript/PostgreSQL.

### Week 1 — Setup & Learning

```
Monday (Day 1):
├─ 09:00-10:30 → Sprint Planning Meeting (semua)
├─ 10:30-12:00 → Install Bun, setup Vite + Inertia + React (Fathan + Azis)
├─ 13:00-15:00 → Setup PostgreSQL + NeonDB + Sanctum + Spatie (Ihsan + Azis)
├─ 15:00-17:00 → Learning: React hooks + TypeScript (Fathan + Azis)

Tuesday (Day 2):
├─ 09:00-12:00 → Learning: Service Layer + Eloquent PostgreSQL (Ihsan + Azis)
├─ 13:00-17:00 → Learning: React component + Tailwind (Fathan + Azis)

Wednesday (Day 3):
├─ 09:00-12:00 → AuthService + Sanctum setup (Ihsan)
├─ 13:00-17:00 → Login page wireframe → React component (Fathan)

Thursday (Day 4):
├─ 09:00-12:00 → Login API + Web controller (Ihsan)
├─ 13:00-17:00 → Login form + validation (Fathan)

Friday (Day 5):
├─ 09:00-12:00 → Code review minggu 1
├─ 13:00-17:00 → Sinkronisasi dokumentasi (Sandikodev)
```

### Week 2 — Auth Core

```
Monday (Day 6):
├─ 09:00-12:00 → Spatie Permission seeder + middleware (Ihsan)
├─ 13:00-17:00 → Navbar + logout button (Fathan), testing login flow

Tuesday (Day 7):
├─ 09:00-12:00 → Logout endpoint + revoke token (Ihsan)
├─ 13:00-17:00 → Responsive design + integration (Fathan)

Wednesday (Day 8):
├─ 09:00-12:00 → Unit test authentication (Ihsan + Azis)
├─ 13:00-17:00 → Bug fixing + role-based menu (Fathan)

Thursday (Day 9):
├─ 09:00-12:00 → UAT preparation (Ahmad)
├─ 13:00-17:00 → Deploy staging + test

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
✅ React component mastery
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

## 🧑‍🏫 Learning Support — OpenKB Integration

Sprint 1 berjalan paralel dengan learning journey tim junior. **Learning Mentor (Azis)** memfasilitasi proses belajar.

### Learning Path Sprint 1

| Developer | Fase OpenKB | Topik | Link ke Dokumen |
|-----------|-------------|-------|-----------------|
| **Ihsan** (Backend) | FASE-06 | Laravel Deep Dive | [`journey/FASE-06-LARAVEL-DEEP-DIVE/`](https://github.com/konxc/openkb-for-junior/tree/main/journey/FASE-06-LARAVEL-DEEP-DIVE) |
|  | 06-03 | Routing Web PHP | [06-03-routing-web-php.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-06-LARAVEL-DEEP-DIVE/06-03-routing-web-php.md) |
|  | 06-04 | Controller & Request | [06-04-controller-dan-request.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-06-LARAVEL-DEEP-DIVE/06-04-controller-dan-request.md) |
|  | 06-05 | Model & Eloquent ORM | [06-05-model-dan-eloquent-orm.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-06-LARAVEL-DEEP-DIVE/06-05-model-dan-eloquent-orm.md) |
|  | 06-07 | Middleware & Auth | [06-07-middleware-dan-auth.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-06-LARAVEL-DEEP-DIVE/06-07-middleware-dan-auth.md) |
| **Fathan** (Frontend) | FASE-06 | Laravel Deep Dive | [`journey/FASE-06-LARAVEL-DEEP-DIVE/`](https://github.com/konxc/openkb-for-junior/tree/main/journey/FASE-06-LARAVEL-DEEP-DIVE) |
|  | 06-06 | Blade Template (email/notification only) | [06-06-blade-template-engine.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-06-LARAVEL-DEEP-DIVE/06-06-blade-template-engine.md) |
|  | FASE-12 | React + TypeScript + Inertia | [`journey/FASE-12-REACT-TS-INERTIA/`](https://github.com/konxc/openkb-for-junior/tree/main/journey/FASE-12-REACT-TS-INERTIA) |
|  | 12-01 | React Fundamentals + Hooks | [12-01-react-hooks.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-12-REACT-TS-INERTIA/12-01-react-hooks.md) |
|  | 12-02 | TypeScript untuk React | [12-02-typescript-react.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-12-REACT-TS-INERTIA/12-02-typescript-react.md) |
|  | 12-03 | InertiaJS + React Setup | [12-03-inertia-react.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-12-REACT-TS-INERTIA/12-03-inertia-react.md) |
|  | 12-04 | Tailwind CSS 4 + Vite 8 | [12-04-tailwind-vite.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-12-REACT-TS-INERTIA/12-04-tailwind-vite.md) |
| **Azis** (Mentor) | FASE-10 | Infrastruktur | [`journey/FASE-10-INFRASTRUKTUR-DAN-DEPLOYMENT/`](https://github.com/konxc/openkb-for-junior/tree/main/journey/FASE-10-INFRASTRUKTUR-DAN-DEPLOYMENT) |
|  | 10-03 | Laragon di Windows | [10-03-laragon-di-windows.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-10-INFRASTRUKTUR-DAN-DEPLOYMENT/10-03-laragon-di-windows.md) |
|  | FASE-11 | Tools & Workflow | [`journey/FASE-11-TOOLS-DAN-WORKFLOW/`](https://github.com/konxc/openkb-for-junior/tree/main/journey/FASE-11-TOOLS-DAN-WORKFLOW) |
|  | 11-04 | Artisan CLI | [11-04-artisan-cli.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-11-TOOLS-DAN-WORKFLOW/11-04-artisan-cli.md) |
|  | 11-05 | Tinker & REPL | [11-05-tinker-dan-repl.md](https://github.com/konxc/openkb-for-junior/blob/main/journey/FASE-11-TOOLS-DAN-WORKFLOW/11-05-tinker-dan-repl.md) |

### Mentor Support Schedule

| Session | Waktu | Topik | Led by |
|---------|-------|-------|--------|
| **Environment Setup** | Day 1 | Laragon, database, Git, SSH | Azis |
| **Laravel Lifecycle** | Day 2 | Request flow, MVC, middleware | Azis |
| **Debugging 101** | Day 3 | Telescope, Tinker, log reading | Azis |
| **Code Review Session** | Day 4 | PR workflow, best practices | Sandikodev |
| **Q&A Open Session** | Day 5 | Free discussion, blocker resolution | Azis + Sandikodev |

### Escalation Path

```
Junior (Fathan/Ihsan)
    │
    ├── Environment/Setup issue
    │   └── → Azis (Learning Mentor)
    │
    ├── Concept/Logic question
    │   └── → Azis (Learning Mentor)
    │
    ├── Architecture/Decision
    │   └── → Sandikodev (PM/Senior)
    │
    └── Blocker > 1 hari
        └── → Sandikodev (PM/Senior)
```

### Resources

- **Full curriculum:** [openkb-for-junior](https://github.com/konxc/openkb-for-junior)
- **Learning path detail:** [`learning-resources.md`](../01-getting-started/learning-resources.md)
- **Mentor role:** [`learning-mentor.md`](../../ROLES/learning-mentor.md)

---

## 🔗 Related Links

- [GitHub Project](https://github.com/orgs/SMA-UII-Yogyakarta/projects/1)
- [SMART ABSEN SMAUII Board](https://trello.com/b/BHXA6ZcR/smart-absen-smauii)
- [GitHub Issues](https://github.com/SMA-UII-Yogyakarta/core/issues?q=is%3Aissue+milestone%3A%22Sprint+1%22)
- [User Story Template](../04-templates/user-story.md)

---

**Next:** [`sprint-2-plan.md`](sprint-2-plan.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev