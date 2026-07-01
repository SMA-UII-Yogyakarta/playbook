# MVP Scope Definition

> MVP Definition for SMART Absen SMA UII Yogyakarta.

---

## 🎯 MVP Goal

**Target:** End of Sprint 3 (~July 18, 2026)

**Objective:**
SMART Absen can be used for student & teacher attendance with basic validation (geolocation, selfie), role-based dashboards, and simple reports.

> **Note:** MVP target shifted from week 4 to week 6 due to stack reset (Livewire/MySQL → Inertia+React/PostgreSQL) and learning path adjustments. Weeks 1-2 focused on documentation synchronization, new stack installation, and basic React/TypeScript/PostgreSQL learning.

---

## ✅ MVP Features

### 1. Authentication (Mandatory)
- [x] Login with email & password
- [x] Logout
- [x] Role-based access (Admin, Teacher, Student, Staff)
- [x] Session management

**Priority:** 🔥 Critical  
**Sprint:** 1

---

### 2. Student Attendance (Mandatory)
- [x] Attendance form with geolocation
- [x] Camera selfie mandatory
- [x] Radius validation (50m from school)
- [x] Time validation (06:00 - 07:30 WIB)
- [x] Duplicate prevention (1x per day)
- [x] Status: On Time, Late
- [x] Attendance history (table view)

**Priority:** 🔥 Critical  
**Sprint:** 2

---

### 3. Teacher Attendance (Mandatory)
- [x] Teacher attendance form (without selfie)
- [x] Radius validation
- [x] Time validation
- [x] Duplicate prevention
- [x] Attendance history

**Priority:** ⚠️ High  
**Sprint:** 2

---

### 4. Dashboard (Mandatory)
- [x] Admin Dashboard
  - Statistics: Total students, teachers, staff
  - Today's attendance
  - Simple charts
   
- Teacher Dashboard
  - Today's teaching schedule
  - Own attendance
  - Attendance history
   
- Student Dashboard
  - Today's attendance
  - Monthly attendance history
  - Total present, sick, permission, absent

**Priority:** ⚠️ High  
**Sprint:** 2

---

### 5. Simple Reports (Mandatory)
- [x] Export attendance per class (Excel)
  - Filter: Class, Month
  - Columns: Name, Date, Status, Time
   
- [x] Export attendance per student (PDF)
  - Filter: Student, Period
  - Summary: Total present, sick, permission, absent

**Priority:** 📌 Medium  
**Sprint:** 3

---

## ❌ NOT in MVP (Post-MVP)

### Sprint 4+
```
❌ Leave Application (sick, permission, absent)
❌ Homeroom teacher approval
❌ WhatsApp Notification
❌ Duty Schedule
❌ Academic Calendar
❌ Face recognition
❌ Offline mode
❌ Mobile app (Flutter)
❌ API documentation public
```

### Backlog
```
❌ SIAD Integration (Academic Information System)
❌ QR Code attendance
❌ Geofencing polygon (not radius)
❌ Multiple school support
❌ Parent notification
```

---

## 📊 MVP Success Criteria

### Functional Criteria

```markdown
✅ Authentication
- User can login/logout
- Role access works
- Session secure

✅ Attendance
- Student can submit attendance
- Geolocation validated
- Selfie captured
- Duplicate prevented

✅ Dashboard
- Dashboard loads for all roles
- Statistics correct
- Responsive on mobile

✅ Reports
- Export Excel works
- Export PDF works
- Data correct
```

---

### Non-Functional Criteria

```markdown
✅ Performance
- Login page load < 2 seconds
- Attendance submit < 3 seconds
- Dashboard load < 3 seconds
- Export generate < 10 seconds

✅ Security
- Password hashed (bcrypt)
- CSRF protection active
- SQL injection prevented
- XSS prevented

✅ Reliability
- Uptime > 95% (staging)
- No data loss
- Error handling adequate

✅ Usability
- Responsive on mobile
- User-friendly UI
- Clear error messages
```

---

## 🧪 MVP Testing Criteria

### Unit Test Coverage

```
Minimum: 70%
Target: 80%

Critical modules:
- Authentication: 90%
- Attendance: 85%
- Reports: 70%
```

---

### UAT Criteria

**Tester:** Ahmad Hanif + Pak Mahfud

```markdown
## UAT Sign-off

**Date:** [Date]

**Test Scenarios:**
- [ ] Login (valid & invalid)
- [ ] Logout
- [ ] Student attendance (geolocation + selfie)
- [ ] Teacher attendance
- [ ] Dashboard (all roles)
- [ ] Export reports

**Issues Found:**
- Critical: 0 (required)
- Major: < 3 (acceptable)
- Minor: < 10 (acceptable)

**Decision:**
- [ ] MVP APPROVED for production
- [ ] MVP REJECTED — Fix critical issues

**Signed:**
Ahmad Hanif (Product Analyst)
Pak Mahfud (Stakeholder)
Sandikodev (Project Manager)
```

---

## 🚀 MVP Deployment

### Staging Deployment

```
Date: Week 4, Day 8
URL: staging.smauiiyk.sch.id
Purpose: UAT + Stakeholder demo
```

### Production Deployment

```
Date: Week 4, Day 10
URL: smauiiyk.sch.id
Purpose: MVP release
Timing: Weekend (Saturday/Sunday)
Duration: 30 minutes (estimated)
```

---

## 📈 Post-MVP Roadmap

### Week 5-6 (Sprint 3)
```
✅ Admin Panel Enhancement
✅ Advanced Reports
✅ Bug fixing from MVP feedback
✅ Performance optimization
```

### Week 7-8 (Sprint 4)
```
✅ Production Audit
✅ Security audit
✅ Performance tuning
✅ Documentation finalization
✅ Training SMA UII staff
✅ Production deployment
```

---

## 🎯 MVP vs Full Product

| Feature | MVP (Week 4) | Full Product (Week 8) |
|---|---|---|
| **Authentication** | ✅ Basic login | ✅ + Reset password, 2FA |
| **Student Attendance** | ✅ Geolocation + selfie | ✅ + Face recognition (optional) |
| **Teacher Attendance** | ✅ Basic | ✅ + Teaching schedule validation |
| **Dashboard** | ✅ Basic stats | ✅ + Advanced analytics |
| **Reports** | ✅ Excel + PDF basic | ✅ + Custom template, email |
| **Leave Application** | ❌ | ✅ |
| **WA Notification** | ❌ | ✅ (optional) |
| **Duty Schedule** | ❌ | ✅ |
| **Mobile App** | ❌ | ❌ (Backlog) |

---

## 📞 MVP Timeline Summary

```
Week 1-2 → Sprint 1: Authentication
Week 3-4 → Sprint 2: Attendance + Dashboard → MVP Ready 🎉
Week 5-6 → Sprint 3: Reports + Enhancement
Week 7-8 → Sprint 4: Production Ready 🚀
```

---

## ⚠️ MVP Risks

| Risk | Impact | Mitigation |
|---|---|---|
| Geolocation inaccurate | High | Manual override option |
| Camera not accessible | Medium | Fallback: Upload photo |
| Export timeout (large data) | Medium | Pagination, chunking |
| UAT finding critical bug | High | Early UAT (Day 8) |

---

**Next:** —  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
