# Communication Guidelines

> Standar komunikasi tim engineering SMA UII Yogyakarta.

---

## 📱 Communication Channels

| Channel | Purpose | Response Time | Members |
|---|---|---|---|
| **WhatsApp Group** | Komunikasi cepat, daily standup, urgent issue | < 1 jam | Semua tim |
| **GitHub Issues** | Technical discussion, task tracking | < 24 jam | Developer |
| **GitHub PR Comments** | Code review discussion | < 24 jam | Developer + Reviewer |
| **Trello Card Comments** | Product discussion, requirement clarification | < 24 jam | Semua tim |
| **Email** | Formal communication, stakeholder report | < 48 jam | Semua tim |
| **Meeting (Google Meet)** | Sprint planning, retrospective, demo | Scheduled | Semua tim |

---

## 💬 WhatsApp Group

**Name:** SMART Absen Dev Team  
**Members:**
- Sandikodev (Lead)
- Ahmad Hanif (Product Analyst)
- Fathan Mubina (Developer)
- Ihsan (Developer)
- Pak Mahfud (Stakeholder)

### Etiquette

**Do's ✅**
- Standup update setiap pagi (format di bawah)
- Share progress harian
- Tanya jika stuck > 30 menit
- Share blocker segera
- Tag orang yang dituju: `@Sandikodev`
- Use thread untuk bahas topik spesifik

**Don'ts ❌**
- Jangan spam (kirim 1 pesan lengkap, bukan 10 pesan pendek)
- Jangan bahas technical detail terlalu dalam (pindah ke GitHub Issue)
- Jangan lupa tag jika butuh response
- Jangan skip standup tanpa info

### Daily Standup Format

**Waktu:** Setiap hari jam 09:00 WIB  
**Format:**

```
📅 Daily Standup — [Tanggal]
👤 [Nama]

✅ Kemarin:
- Task 1
- Task 2

🎯 Hari ini:
- Task 1
- Task 2

🚫 Blocker:
- [Deskripsi blocker, atau "None"]
```

**Contoh:**

```
📅 Daily Standup — 24 Juni 2026
👤 Fathan

✅ Kemarin:
- Login page UI (completed)
- Responsive testing (completed)

🎯 Hari ini:
- Dashboard component
- Fix bug di presensi form

🚫 Blocker:
- None
```

---

## 🐛 Escalation Matrix

### Level 1: Task Blocker (< 2 jam)

**Channel:** WhatsApp Group  
**Response:** Tim  
**Contoh:**
```
"Guys, ada yang tau cara handle timezone di Livewire?"
```

---

### Level 2: Task Blocker (> 2 jam)

**Channel:** WhatsApp Group + Tag Sandikodev  
**Response:** Sandikodev  
**Contoh:**
```
"@Sandikodev, stuck di validasi geolokasi sudah 2 jam. 
Bisa bantu pair programming siang ini?"
```

---

### Level 3: Critical Production Bug

**Channel:** WhatsApp Group + Call Sandikodev  
**Response:** Immediate  
**Contoh:**
```
🚨 CRITICAL: Login error production
User tidak bisa login sejak 10 menit lalu.
Error 500 di /auth/login.
@sandikodev checking logs now.
```

---

### Level 4: Requirement Ambiguity

**Channel:** Trello Card Comment + Tag Ahmad Hanif  
**Response:** Ahmad Hanif  
**Contoh:**
```
"@Ahmad Hanif, untuk user story 'export laporan', 
perlu clarify: format export apa? Excel atau PDF?
Dan periode export per bulan atau custom date range?"
```

---

### Level 5: Stakeholder Decision

**Channel:** Email + WhatsApp (urgent)  
**Response:** Pak Mahfud + Sandikodev  
**Contoh:**
```
"Pak Mahfud, untuk fitur presensi, ada 2 opsi:
1. Presensi sekali per hari (simple)
2. Presensi masuk & pulang (lebih detail)

Rekomendasi kami opsi 1 untuk MVP. 
Mohon keputusannya agar tim bisa lanjut development."
```

---

## 📧 Email Templates

### Sprint Report (Ke Stakeholder)

**To:** Pak Mahfud  
**CC:** Tim  
**Subject:** Sprint [X] Report — SMART Absen — [Tanggal]

```
Assalamu'alaikum Pak Mahfud,

Berikut laporan Sprint [X] development SMART Absen:

✅ COMPLETED (Sprint [X])
- Fitur 1
- Fitur 2
- Fitur 3

🚧 IN PROGRESS
- Task 1 (50%)
- Task 2 (30%)

📊 METRICS
- Velocity: [X] story points
- Bug count: [X] (critical: 0)
- Sprint completion: [X]%

📅 NEXT SPRINT
- Fitur 1
- Fitur 2

🚫 BLOCKER
- [Deskripsi blocker, atau "None"]

Mohon feedback dan arahannya.

Terima kasih.

Best regards,
Sandikodev
PT Koneksi Jaringan Indonesia
```

---

### Production Deployment Notice

**To:** Pak Mahfud, SMA UII Staff  
**CC:** Tim  
**Subject:** Production Deployment — SMART Absen v1.0 — [Tanggal]

```
Assalamu'alaikum,

Kami informasikan akan ada deployment SMART Absen versi 1.0:

📅 Tanggal: [Hari, Tanggal]
⏰ Waktu: [Jam] WIB
⏱️ Durasi: [X] jam (estimasi)
🔧 Impact: [Downtime / No downtime]

FITUR BARU
- Fitur 1
- Fitur 2

BUG FIX
- Fix issue 1
- Fix issue 2

Mohon informasikan ke pengguna jika ada downtime.

Terima kasih.

Best regards,
Sandikodev
```

---

## 🎯 Meeting Guidelines

### Sprint Planning Meeting

**Frequency:** Setiap 2 minggu (Senin pagi Week 1)  
**Duration:** 60-90 menit  
**Attendees:** Semua tim  
**Agenda:**
1. Review sprint sebelumnya (15 menit)
2. Presentasi backlog untuk sprint berikutnya (15 menit)
3. Estimasi story points (30 menit)
4. Commit sprint goal (15 menit)
5. Assign task (15 menit)

**Preparation:**
- Ahmad: Backlog ready di Trello
- Sandikodev: Technical breakdown ready
- Developer: Review backlog sebelum meeting

---

### Sprint Review & Demo

**Frequency:** Setiap 2 minggu (Senin pagi Week 3)  
**Duration:** 60 menit  
**Attendees:** Semua tim + Pak Mahfud  
**Agenda:**
1. Demo fitur yang selesai (30 menit)
2. Feedback stakeholder (15 menit)
3. Q&A (15 menit)

**Preparation:**
- Developer: Demo environment ready
- Ahmad: Feedback form ready

---

### Sprint Retrospective

**Frequency:** Setiap 2 minggu (setelah Sprint Review)  
**Duration:** 45-60 menit  
**Attendees:** Tim internal (tanpa stakeholder)  
**Agenda:**
1. What went well? (15 menit)
2. What could be improved? (15 menit)
3. Action items untuk sprint berikutnya (15 menit)

**Format:**
```
😊 Went Well
- Code review lebih cepat
- Communication lancar

🤔 To Improve
- Task estimation meleset
- Blocker lama tidak di-escalate

✅ Action Items
- Sandikodev: Daily check-in blocker
- Fathan: Update status Trello lebih rajin
```

---

### Daily Standup (Async)

**Frequency:** Setiap hari (Senin-Jumat) jam 09:00  
**Duration:** 15 menit (sync) atau async di WhatsApp  
**Attendees:** Developer + Sandikodev  
**Format:** Lihat "Daily Standup Format" di atas

**Note:**
- Sync meeting hanya jika ada diskusi kompleks
- Default: async di WhatsApp

---

## 📝 Documentation Communication

### GitHub Issue Discussion

**When:** Technical discussion untuk task spesifik  
**Format:**

```markdown
## Question
[Deskripsi pertanyaan]

## Context
[Link code, screenshot, error log]

## Proposed Solution
[Usulan solusi]

## Question for Reviewer
@Sandikodev apakah approach ini sudah tepat?
```

---

### Pull Request Discussion

**When:** Code review feedback  
**Format:**

```markdown
## Review Comment
[Feedback spesifik dengan line reference]

## Suggestion
```php
// Before
$user = User::find($id);

// After
$user = User::with('roles')->findOrFail($id);
```

## Question
@Hans02-Neo apakah ada pertimbangan performance untuk query ini?
```

---

### Trello Card Discussion

**When:** Requirement clarification  
**Format:**

```markdown
@Ahmad Hanif

Need clarification untuk acceptance criteria:

"Export laporan maksimal 1000 baris"

Pertanyaan:
1. Apa yang terjadi jika data > 1000 baris?
   - Error?
   - Paginate?
   - Truncate?

2. Apakah ada filter periode untuk limit 1000 baris ini?

Mohon bantuannya.
```

---

## 🌐 Async Communication Best Practices

### Context is King

**Buruk:**
```
"Error nih, gimana fixnya?"
```

**Baik:**
```
"Error 500 di endpoint POST /api/attendance.
Sudah coba debug, ternyata null pointer di line 45 AttendanceController.php.
Stack trace: [paste error]
Sudah coba: null check, tetap error.
Ada ide?"
```

---

### One Message, Complete Info

**Buruk:**
```
Pesan 1: "Guys"
Pesan 2: "ada yang bisa Java?"
Pesan 3: "urgent"
```

**Baik:**
```
"Guys, ada yang experienced dengan Laravel Sanctum?
Need help untuk implement multi-device auth.
Urgent untuk sprint ini.
@Sandikodev bisa bantu siang ini?"
```

---

### Tag the Right Person

```
General question → WhatsApp Group
Technical bug → @Sandikodev
Requirement → @Ahmad Hanif
Frontend → @Fathan
Backend → @Ihsan
Stakeholder decision → @Pak Mahfud
```

---

## 🕐 Response Time SLA

| Channel | Priority | Expected Response |
|---|---|---|
| WhatsApp (urgent) | Critical | < 15 menit |
| WhatsApp (general) | High | < 1 jam |
| GitHub Issue | Medium | < 24 jam |
| GitHub PR Review | High | < 24 jam |
| Trello Comment | Medium | < 24 jam |
| Email | Low | < 48 jam |

---

## 🚨 Crisis Communication

### Production Outage

**Step 1:** WhatsApp Group + Call Sandikodev
```
🚨 CRITICAL: Production down
Error: [deskripsi]
Impact: [jumlah user affected]
Started: [jam]
```

**Step 2:** Sandikodev investigating
```
Checking logs...
ETA fix: 30 menit
```

**Step 3:** Update berkala (setiap 15 menit)
```
Update 1: Root cause identified (database connection)
Update 2: Fix in progress
Update 3: Fix deployed, monitoring...
```

**Step 4:** Post-mortem (setelah fix)
```
✅ Resolved
Root cause: [deskripsi]
Fix: [deskripsi]
Prevention: [action items]
```

---

## 📊 Communication Metrics

### Team Health Check (Monthly)

**Questions:**
1. Apakah komunikasi lancar? (1-5)
2. Apakah blocker cepat di-resolve? (1-5)
3. Apakah requirement jelas? (1-5)
4. Apakah feedback constructive? (1-5)

**Target:** Average score > 4.0

---

**Next:** [`code-review.md`](../03-sop/code-review.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev