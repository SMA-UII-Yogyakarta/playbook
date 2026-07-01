# MVP Scope Definition

> Definition of MVP untuk SMART Absen SMA UII Yogyakarta.

---

## 🎯 MVP Goal

**Target:** Akhir Sprint 3 (~18 Juli 2026)

**Objective:**
SMART Absen dapat digunakan untuk presensi siswa & guru dengan validasi dasar (geolokasi, swafoto), dashboard per role, dan laporan sederhana.

> **Catatan:** Target MVP bergeser dari minggu 4 ke minggu 6 karena reset stack (Livewire/MySQL → Inertia+React/PostgreSQL) dan penyesuaian learning path. Minggu 1-2 difokuskan pada sinkronisasi dokumentasi, instalasi stack baru, dan pembelajaran dasar React/TypeScript/PostgreSQL.

---

## ✅ MVP Features

### 1. Authentication (Wajib)
- [x] Login dengan email & password
- [x] Logout
- [x] Role-based access (Admin, Guru, Siswa, Staff)
- [x] Session management

**Priority:** 🔥 Critical  
**Sprint:** 1

---

### 2. Presensi Siswa (Wajib)
- [x] Form presensi dengan geolokasi
- [x] Swafoto kamera wajib
- [x] Validasi radius (50m dari sekolah)
- [x] Validasi waktu (06:00 - 07:30 WIB)
- [x] Duplicate prevention (1x per hari)
- [x] Status: On Time, Late
- [x] Riwayat presensi (table view)

**Priority:** 🔥 Critical  
**Sprint:** 2

---

### 3. Presensi Guru (Wajib)
- [x] Form presensi guru (tanpa swafoto)
- [x] Validasi radius
- [x] Validasi waktu
- [x] Duplicate prevention
- [x] Riwayat presensi

**Priority:** ⚠️ High  
**Sprint:** 2

---

### 4. Dashboard (Wajib)
- [x] Dashboard Admin
  - Statistik: Total siswa, guru, staff
  - Kehadiran hari ini
  - Grafik sederhana
  
- Dashboard Guru
  - Jadwal mengajar hari ini
  - Presensi sendiri
  - Riwayat presensi
  
- Dashboard Siswa
  - Presensi hari ini
  - Riwayat presensi bulan ini
  - Total hadir, sakit, izin, alfa

**Priority:** ⚠️ High  
**Sprint:** 2

---

### 5. Laporan Sederhana (Wajib)
- [x] Export presensi per kelas (Excel)
  - Filter: Kelas, Bulan
  - Columns: Nama, Tanggal, Status, Jam
  
- [x] Export presensi per siswa (PDF)
  - Filter: Siswa, Periode
  - Summary: Total hadir, sakit, izin, alfa

**Priority:** 📌 Medium  
**Sprint:** 3

---

## ❌ NOT in MVP (Post-MVP)

### Sprint 4+
```
❌ Pengajuan Izin (sakit, izin, alfa)
❌ Approval wali kelas
❌ Notifikasi WhatsApp
❌ Jadwal Piket
❌ Kalender Akademik
❌ Face recognition
❌ Offline mode
❌ Mobile app (Flutter)
❌ API documentation public
```

### Backlog
```
❌ Integrasi dengan SIAD (Sistem Informasi Akademik)
❌ QR Code presensi
❌ Geofencing polygon (bukan radius)
❌ Multiple school support
❌ Parent notification
```

---

## 📊 MVP Success Criteria

### Functional Criteria

```markdown
✅ Authentication
- User dapat login/logout
- Role access berfungsi
- Session secure

✅ Presensi
- Siswa dapat submit presensi
- Geolokasi validated
- Swafoto captured
- Duplicate prevented

✅ Dashboard
- Dashboard loads untuk semua role
- Statistik correct
- Responsive di mobile

✅ Laporan
- Export Excel berfungsi
- Export PDF berfungsi
- Data correct
```

---

### Non-Functional Criteria

```markdown
✅ Performance
- Login page load < 2 detik
- Presensi submit < 3 detik
- Dashboard load < 3 detik
- Export generate < 10 detik

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
- Responsive di mobile
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
- Presensi: 85%
- Laporan: 70%
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
- [ ] Presensi siswa (geolokasi + swafoto)
- [ ] Presensi guru
- [ ] Dashboard (all roles)
- [ ] Export laporan

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
Timing: Weekend (Sabtu/Minggu)
Duration: 30 menit (estimasi)
```

---

## 📈 Post-MVP Roadmap

### Week 5-6 (Sprint 3)
```
✅ Admin Panel Enhancement
✅ Laporan Advanced
✅ Bug fixing dari MVP feedback
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
| **Presensi Siswa** | ✅ Geolokasi + swafoto | ✅ + Face recognition (optional) |
| **Presensi Guru** | ✅ Basic | ✅ + Jadwal mengajar validation |
| **Dashboard** | ✅ Basic stats | ✅ + Advanced analytics |
| **Laporan** | ✅ Excel + PDF basic | ✅ + Custom template, email |
| **Pengajuan Izin** | ❌ | ✅ |
| **Notifikasi WA** | ❌ | ✅ (optional) |
| **Jadwal Piket** | ❌ | ✅ |
| **Mobile App** | ❌ | ❌ (Backlog) |

---

## 📞 MVP Timeline Summary

```
Week 1-2 → Sprint 1: Authentication
Week 3-4 → Sprint 2: Presensi + Dashboard → MVP Ready 🎉
Week 5-6 → Sprint 3: Laporan + Enhancement
Week 7-8 → Sprint 4: Production Ready 🚀
```

---

## ⚠️ MVP Risks

| Risk | Impact | Mitigation |
|---|---|---|
| Geolocation tidak akurat | High | Manual override option |
| Camera tidak accessible | Medium | Fallback: Upload foto |
| Export timeout (data banyak) | Medium | Pagination, chunking |
| UAT finding critical bug | High | Early UAT (Day 8) |

---

**Next:** —  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev