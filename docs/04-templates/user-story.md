# User Story Template

> Template untuk Product Analyst dalam menulis user story.

---

## 📝 Template

```markdown
## User Story

**ID:** SMART-001  
**Title:** [Judul singkat]  
**Priority:** High/Medium/Low  
**Sprint:** [Sprint number]

---

### Story

**Sebagai** [role/user]  
**Saya ingin** [fitur/kemampuan]  
**Agar** [manfaat/business value]

---

### Acceptance Criteria

#### Functional
- [ ] Kriteria 1 (specific, testable)
- [ ] Kriteria 2 (specific, testable)
- [ ] Kriteria 3 (specific, testable)

#### Non-Functional
- [ ] Performance: Load time < 2 detik
- [ ] Security: [security requirement]
- [ ] UX: Responsive di mobile & desktop

---

### Business Rules

1. Rule 1
2. Rule 2
3. Rule 3

---

### Edge Cases

- Scenario 1: [Handling]
- Scenario 2: [Handling]

---

### Mockup/Wireframe

[Attach link ke Figma/Excalidraw/screenshot]

---

### Dependencies

- [ ] Dependency 1 (link ke card/issue)
- [ ] Dependency 2

---

### Out of Scope

- Fitur yang TIDAK termasuk di story ini:
  - Item 1
  - Item 2
```

---

## 📖 Examples

### Example 1: Login Feature

```markdown
## User Story

**ID:** SMART-001  
**Title:** Login dengan Email & Password  
**Priority:** High  
**Sprint:** 1

---

### Story

**Sebagai** guru atau staff SMA UII  
**Saya ingin** login dengan email dan password  
**Agar** saya dapat mengakses sistem SMART Absen

---

### Acceptance Criteria

#### Functional
- [ ] User dapat login dengan email & password valid
- [ ] User mendapat error "Email atau password salah" jika credentials invalid
- [ ] User mendapat error validation jika email kosong
- [ ] User mendapat error validation jika password kosong
- [ ] User di-redirect ke dashboard setelah login sukses
- [ ] User dapat logout

#### Non-Functional
- [ ] Login page load < 2 detik
- [ ] Password di-hash di database (bcrypt)
- [ ] Session timeout setelah 2 jam tidak aktif
- [ ] Responsive di mobile & desktop

---

### Business Rules

1. Password minimal 8 karakter
2. Password harus mengandung huruf & angka
3. User dapat reset password via email
4. Login gagal 5x → account locked 15 menit

---

### Edge Cases

- Email tidak terdaftar: Show generic error "Email atau password salah"
- Password lupa: Link ke reset password page
- Session expired: Redirect ke login dengan message

---

### Mockup/Wireframe

[Link ke Figma]

---

### Dependencies

- [ ] Database schema users (Issue #1)
- [ ] Sanctum authentication setup (Issue #2)

---

### Out of Scope

- Login dengan Google SSO (Sprint 3)
- Login dengan NIP (Sprint 2)
```

---

### Example 2: Presensi Siswa

```markdown
## User Story

**ID:** SMART-012  
**Title:** Presensi Siswa dengan Geolokasi & Swafoto  
**Priority:** High  
**Sprint:** 2

---

### Story

**Sebagai** siswa SMA UII  
**Saya ingin** melakukan presensi dengan geolokasi dan swafoto  
**Agar** kehadiran saya tercatat dengan valid

---

### Acceptance Criteria

#### Functional
- [ ] Siswa dapat melihat form presensi di dashboard
- [ ] Form menampilkan preview kamera untuk swafoto
- [ ] Form auto-detect geolokasi (latitude, longitude)
- [ ] Submit presensi berhasil jika geolokasi dalam radius 50m dari sekolah
- [ ] Submit presensi gagal jika geolokasi di luar radius
- [ ] Swafoto wajib di-capture sebelum submit
- [ ] Presensi hanya dapat dilakukan 1x per hari
- [ ] Siswa dapat melihat riwayat presensi sendiri

#### Non-Functional
- [ ] Camera load < 3 detik
- [ ] Geolocation detect < 5 detik
- [ ] Submit presensi < 2 detik
- [ ] Foto disimpan di object storage (S3)
- [ ] Responsive di mobile (karena siswa pakai HP)

---

### Business Rules

1. Radius presensi: 50 meter dari koordinat sekolah (-7.7956, 110.3695)
2. Waktu presensi: 06:00 - 07:30 WIB (ontime), setelahnya late
3. Presensi duplicate: Ditolak dengan message "Anda sudah presensi hari ini"
4. Foto: Min 640x480, max 2MB, format JPG/PNG
5. Geolokasi: Wajib diaktifkan, jika tidak show error

---

### Edge Cases

- GPS tidak akurat (accuracy > 100m): Show warning "Akurasi GPS rendah, coba di tempat terbuka"
- Kamera tidak accessible: Show error "Akses kamera ditolak, mohon izinkan akses kamera di browser"
- Internet lambat: Show loading spinner dengan timeout 30 detik
- Submit gagal: Retry otomatis max 3x

---

### Mockup/Wireframe

[Link ke Figma]

---

### Dependencies

- [ ] Authentication module (SMART-001) ✅
- [ ] Geolocation API (Issue #15)
- [ ] Camera API (Issue #16)
- [ ] Object Storage setup (Issue #10)

---

### Out of Scope

- Presensi tanpa internet (offline mode) — Sprint 4
- Face recognition — Sprint 5
- Presensi via WhatsApp bot — Backlog
```

---

## 💡 Writing Tips

### Good User Story Characteristics (INVEST)

```
I - Independent (dapat dikembangkan terpisah)
N - Negotiable (dapat dinegosiasikan)
V - Valuable (bernilai bisnis)
E - Estimable (dapat diestimasi)
S - Small (dapat selesai dalam 1 sprint)
T - Testable (dapat di-test)
```

---

### Acceptance Criteria: Gherkin Format

```gherkin
Feature: Login
  Scenario: Login dengan credentials valid
    Given user ada di halaman login
    When user input email "admin@smauiiyk.sch.id"
    And user input password "Admin123!"
    And user klik tombol "Login"
    Then user di-redirect ke dashboard
    And user melihat welcome message "Selamat datang, Admin"

  Scenario: Login dengan credentials invalid
    Given user ada di halaman login
    When user input email "wrong@email.com"
    And user input password "wrongpass"
    And user klik tombol "Login"
    Then user melihat error "Email atau password salah"
    And user tetap di halaman login
```

---

### Common Mistakes

**Buruk:**
```
Sebagai user
Saya ingin login
Agar bisa pakai aplikasi
```

**Baik:**
```
Sebagai guru SMA UII
Saya ingin login dengan email & password
Agar dapat mengakses SMART Absen untuk mengelola presensi
```

---

**Next:** [`github-issue.md`](github-issue.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Ahmad Hanif