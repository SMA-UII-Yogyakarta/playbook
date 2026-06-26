# Trello Workflow — Product Management

> Panduan menggunakan Trello untuk product management SMART Absen SMA UII.

---

## 🎯 Purpose

Trello adalah **Source of Truth untuk Product Management**:
- Product roadmap
- Sprint planning
- Requirement tracking
- Stakeholder feedback

**GitHub Project** adalah **Source of Truth untuk Engineering**:
- Technical task
- Code implementation
- PR tracking
- Release management

---

## 📋 Board Structure

### Board 1: Product Roadmap

**URL:** [`https://trello.com/b/BHXA6ZcR/smart-absen-smauii`](https://trello.com/b/BHXA6ZcR/smart-absen-smauii) (invite-only)

**Kolom:**

```
📌 Q2 2026 (Planned)
📌 Next Sprint
🚧 In Development
✅ Released
```

**Level:** Epic / Feature (bukan task teknis)

**Contoh Card:**

```
┌─────────────────────────────────────┐
│ Presensi Siswa                      │
├─────────────────────────────────────┤
│ • Presensi dengan geolokasi         │
│ • Swafoto kamera                    │
│ • Validasi triple-layer             │
│ • Riwayat presensi                  │
└─────────────────────────────────────┘
```

**Card Detail:**
```markdown
## Description
Fitur presensi untuk siswa dengan validasi lokasi dan swafoto.

## Business Value
- Memudahkan monitoring kehadiran siswa
- Mencegah absensi titip
- Real-time tracking

## Acceptance Criteria
- Siswa dapat presensi via web
- Validasi geolokasi (radius 50m dari sekolah)
- Swafoto wajib dengan face detection
- Presensi hanya 1x per hari

## Dependencies
- SSO (Authentication)
- Geolocation API
- Camera API

## Stakeholder
Pak Mahfud (SMA UII)

## Timeline
Target: Sprint 2 (Minggu 3-4)
```

---

### Board 2: Sprint Board

**URL:** [`https://trello.com/b/BHXA6ZcR/smart-absen-smauii`](https://trello.com/b/BHXA6ZcR/smart-absen-smauii) (invite-only)

**Kolom:**

```
📋 Product Backlog
✅ Ready for Dev
🚧 In Progress
👀 Code Review
🧪 UAT / Testing
✅ Done
```

**Level:** Task per Sprint (2 minggu)

**Contoh Card:**

```
┌─────────────────────────────────────┐
│ [FE-01] Halaman Login               │
├─────────────────────────────────────┤
│ Assignee: Fathan                    │
│ Sprint: 1                           │
│ Story Points: 3                     │
└─────────────────────────────────────┘
```

---

## 🏷️ Labels

### Priority Labels

| Label | Color | Meaning |
|---|---|---|
| `🔥 Critical` | Red | Harus selesai sprint ini |
| `⚠️ High` | Orange | Prioritas tinggi |
| `📌 Medium` | Yellow | Normal priority |
| `🐌 Low` | Green | Dapat ditunda |

### Type Labels

| Label | Color | Meaning |
|---|---|---|
| `📱 Frontend` | Blue | Task frontend |
| `⚙️ Backend` | Purple | Task backend |
| `🎨 UI/UX` | Pink | Design task |
| `📄 Docs` | Gray | Dokumentasi |
| `🐛 Bug` | Red | Bug fix |

### Sprint Labels

| Label | Color | Meaning |
|---|---|---|
| `Sprint 1` | Blue | Minggu 1-2 |
| `Sprint 2` | Green | Minggu 3-4 |
| `Sprint 3` | Orange | Minggu 5-6 |
| `Sprint 4` | Purple | Minggu 7-8 |

---

## 📝 Card Workflow

### 1. Card Dibuat (Ahmad Hanif)

**PIC:** Ahmad Hanif

**Aktivitas:**
- Riset requirement
- Tulis user story
- Define acceptance criteria
- Add ke kolom `Product Backlog`

**Checklist:**
```markdown
## Requirement Checklist
- [ ] User story jelas
- [ ] Acceptance criteria testable
- [ ] Business value terdefinisi
- [ ] Stakeholder approved
```

---

### 2. Card di-Review (Sandikodev)

**PIC:** Sandikodev

**Aktivitas:**
- Review requirement clarity
- Breakdown jadi technical task
- Estimate effort (Story Points)
- Move ke `Ready for Dev` jika siap

**Checklist:**
```markdown
## Technical Review
- [ ] Requirement jelas (tidak ambigu)
- [ ] Acceptance criteria testable
- [ ] Technical feasibility confirmed
- [ ] Dependencies identified
- [ ] Story points assigned
```

---

### 3. Developer Ambil Task (Fathan/Ihsan)

**PIC:** Developer (Fathan/Ihsan)

**Aktivitas:**
- Assign nama ke card
- Move ke `In Progress`
- Buat GitHub Issue (link di card)
- Mulai coding

**Checklist:**
```markdown
## Development Checklist
- [ ] GitHub Issue dibuat
- [ ] Branch dibuat
- [ ] Coding in progress
- [ ] Self-test done
- [ ] PR dibuat
```

**Update Card:**
```markdown
## Development
- GitHub Issue: #12
- Branch: feature/12-login
- PR: #34
- Status: In Progress
```

---

### 4. Code Review (Sandikodev)

**PIC:** Sandikodev

**Aktivitas:**
- Review PR di GitHub
- Approve atau request changes
- Move card ke `UAT / Testing` jika PR merged

**Checklist:**
```markdown
## Code Review
- [ ] Code quality OK
- [ ] Test coverage OK
- [ ] Security check OK
- [ ] Performance OK
- [ ] PR merged
```

---

### 5. UAT / Testing (Ahmad Hanif)

**PIC:** Ahmad Hanif

**Aktivitas:**
- Test di staging environment
- Validasi acceptance criteria
- Approve atau report bug
- Move ke `Done` jika approved

**Checklist:**
```markdown
## UAT Checklist
- [ ] Semua acceptance criteria terpenuhi
- [ ] No critical bug
- [ ] UI/UX sesuai ekspektasi
- [ ] Tested di staging
- [ ] Stakeholder demo (jika perlu)
```

---

### 6. Card Done

**PIC:** Sandikodev

**Aktivitas:**
- Update Trello card
- Add ke Release Notes (jika sprint end)
- Deploy ke production (jika scheduled)

---

## 📊 Definition of Ready (DoR)

Card boleh pindah dari `Backlog` → `Ready for Dev` jika:

```markdown
## Definition of Ready

✅ User Story format lengkap:
   - "Sebagai [role]..."
   - "Saya ingin [fitur]..."
   - "Agar [manfaat]..."

✅ Acceptance Criteria jelas:
   - Specific
   - Measurable
   - Testable

✅ Business value terdefinisi

✅ Dependencies identified

✅ Technical feasibility confirmed

✅ Story points assigned (1, 2, 3, 5, 8)
```

---

## 📊 Definition of Done (DoD)

Card boleh pindah dari `Testing` → `Done` jika:

```markdown
## Definition of Done

✅ Code complete

✅ Unit test hijau (>70% coverage)

✅ Code review approved (minimal 1)

✅ PR merged ke main

✅ UAT passed (Ahmad Hanif)

✅ No critical/open bugs

✅ Dokumentasi updated (jika perlu)

✅ Deployed ke staging

✅ Stakeholder demo (jika required)
```

---

## 🔄 Sprint Cycle

### Sprint Duration: 2 Minggu

```
Week 1          Week 2
Mon Tue Wed Thu Fri Mon Tue Wed Thu Fri
│               │               │
├─ Sprint       ├─ Development  ├─ Sprint
│  Planning     │               │  Review
│               │               │  & Retro
```

### Sprint Timeline

**Day 1 (Monday Week 1): Sprint Planning**
- Review backlog
- Commit ke sprint goal
- Assign task
- Estimate story points

**Day 1-8: Development**
- Daily standup (15 menit, WhatsApp)
- Update Trello card progress
- PR & code review

**Day 9 (Friday Week 2): Testing**
- UAT oleh Ahmad Hanif
- Bug fixing

**Day 10 (Monday Week 3): Sprint Review & Retrospective**
- Demo ke stakeholder (Pak Mahfud)
- Retrospective: What went well, what to improve
- Sprint 2 planning

---

## 📈 Velocity Tracking

### Story Points

**Fibonacci Scale:**
```
1 — Tiny (1-2 jam)
2 — Small (0.5 hari)
3 — Medium (1 hari)
5 — Large (2-3 hari)
8 — XL (1 sprint)
```

**Velocity Calculation:**
```
Sprint 1: 13 points completed
Sprint 2: 15 points completed
Sprint 3: 12 points completed

Average Velocity: 13.3 points/sprint
```

**Capacity Planning:**
```
Sprint 4 capacity: 13 points

Task breakdown:
- Login: 3 points
- Dashboard: 5 points
- Presensi: 5 points
Total: 13 points ✅
```

---

## 🔗 Trello ↔ GitHub Integration

### Link Trello Card ↔ GitHub Issue

**Di Trello Card:**
```markdown
## Links
- GitHub Issue: https://github.com/SMA-UII-Yogyakarta/core/issues/12
- PR: https://github.com/SMA-UII-Yogyakarta/core/pull/34
```

**Di GitHub Issue:**
```markdown
## Context
Trello: https://trello.com/c/ABC123
```

### Automation (Power-Ups)

**GitHub Power-Up:**
- Link GitHub repo ke Trello
- Attach PR ke card
- Auto-update status

**Card Mapping:**
```
Trello: In Progress  →  GitHub: In Progress
Trello: Code Review  →  GitHub: PR Open
Trello: Done         →  GitHub: Closed/Merged
```

---

## 💡 Best Practices

### Do's ✅

- Update card status real-time
- Comment progress di card
- Link GitHub Issue di card
- Move card segera setelah status berubah
- Checklist detail untuk task kompleks

### Don'ts ❌

- Jangan biarkan card stuck > 2 hari tanpa update
- Jangan skip DoR/DoD checklist
- Jangan gabungkan multiple fitur di 1 card
- Jangan vague acceptance criteria
- Jangan lupa move card ke Done setelah deploy

---

## 📱 Mobile Access

**Trello Mobile App:**
- iOS: [Download](https://apps.apple.com/app/trello/id461504587)
- Android: [Download](https://play.google.com/store/apps/details?id=com.trello)

**Quick Actions:**
- Update card status
- Add comment
- Check/uncheck checklist
- Assign member
- Add attachment (screenshot bug)

---

## 🆘 Troubleshooting

### Issue: Card tidak jelas requirement

**Solusi:**
1. Comment di card: "@Ahmad Hanif mohon clarify requirement untuk..."
2. Wait clarification
3. Update card setelah jelas

### Issue: Task blocker > 2 jam

**Solusi:**
1. Add label `🚫 Blocked` ke card
2. Comment di card: "Blocker: [deskripsi masalah]"
3. Tag Sandikodev: "@Sandikodev butuh help untuk..."
4. Escalate di WhatsApp Group

### Issue: Card stuck di Code Review

**Solusi:**
1. Tag reviewer: "@Sandikodev mohon review untuk PR #..."
2. Wait max 24 jam
3. Jika tidak ada response, ping di WhatsApp

---

## 📚 Resources

- [Trello Guide](https://trello.com/guide)
- [Agile with Trello](https://trello.com/agile)
- [Power-Ups](https://trello.com/power-ups)

---

**Next:** [`communication.md`](communication.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Ahmad Hanif