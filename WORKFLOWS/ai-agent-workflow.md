# AI Agent Workflow — TACO Protocol

> Standar workflow penggunaan AI Agent (Opencode, Claude Code, Claw Code, Cursor)
> untuk seluruh anggota tim PT Koneksi Jaringan Indonesia.

---

## 🎯 TACO Protocol

TACO = **Trello → AI → Commit → Output**

Empat langkah yang mengintegrasikan perencanaan (Trello) dengan eksekusi (AI Agent):

```
┌──────────────────────────────────────────────────────────────────┐
│  T — Trello: Task diambil dari board, status → "In Progress"     │
│  A — AI: Buka AI Agent dengan konteks role & project             │
│  C — Commit: Kode selesai → commit dengan conventional commit    │
│  O — Output: PR dibuat, Trello diupdate, knowledge dicatat       │
└──────────────────────────────────────────────────────────────────┘
```

---

## 📋 Workflow Detail

### Step 1: Trello — Ambil Task

**Siapa:** Fathan / Ihsan (Developer)

**Aksi:**
1. Buka Trello Sprint Board
2. Pilih task dari kolom "Ready"
3. Assign card ke diri sendiri
4. Pindahkan ke "In Progress"
5. Catat Issue ID: `ISSUE-12` (link dari card description)

**Output:** Task terassign, Issue ID tercatat.

---

### Step 2: AI — Persiapan Agent

**Siapa:** Developer

**Aksi:**
```bash
# Contoh dengan Opencode:
opencode --task "Kerjakan ISSUE-12: Attendance Validation"

# Contoh dengan Claude Code:
claude -p "Kerjakan Issue #12 tentang attendance validation"

# Contoh dengan Cursor IDE:
# Buka project → Ctrl+Shift+P → "AI: Start Task" → paste Issue URL
```

**Yang AI baca otomatis:**
| Sumber | Isi |
|---|---|
| `.opencode/SHARED/project-context.md` | Stack, arsitektur, tim |
| `.opencode/SHARED/agent-rules.md` | Aturan main, coding standard |
| `~/.openkb/PERSONAL/<user>/profile.md` | Siapa saya, skill, preferensi |
| `~/.openkb/ROLES/<role>.md` | Tanggung jawab & AI instructions per role |
| `playbook/ROLES/<role>.md` | Role definition & ekspektasi |
| Issue #12 di GitHub | Requirement & acceptance criteria |

**Output:** AI Agent siap dengan konteks lengkap.

---

### Step 3: Commit — Eksekusi Kode

**Siapa:** Developer + AI Agent

**Alur:**
```
1. AI pelajari Issue & acceptance criteria
2. AI baca kode existing yang relevan
3. AI tulis kode baru / modifikasi
4. Developer review output AI
5. AI running test: composer test / bun run test
6. Developer self-review
7. Commit: feat(attendance): implementasi validasi presensi
```

**Branch naming:**
```
feature/ISSUE-12-attendance-validation
```

**Conventional Commit:**
```
feat(attendance): implementasi validasi triple-layer
fix(attendance): perbaiki bug radius geolokasi
chore(deps): update laravel/framework
```

**Output:** Code committed dan siap di-PR.

---

### Step 4: Output — PR & Update

**Siapa:** Developer

**Aksi:**
```bash
git push origin feature/ISSUE-12-attendance-validation
gh pr create --title "feat(attendance): validasi presensi" --body "Fixes #12"
```

**PR body:**
```markdown
## Related Issue
Fixes #12

## Changes
- [BE] Tripe-layer validation logic
- [DB] Migration: add presensi table
- [Test] Unit test attendance validation

## Self-Checklist
- [ ] Acceptance criteria terpenuhi
- [ ] Unit test coverage > 70%
- [ ] Security: no SQL injection, no XSS
- [ ] Performance: no N+1 query
- [ ] Coding standard: PSR-12

## Trello Card
SMART-21 → pindah ke "Review"

## Notes for Reviewer
- Perhatikan validasi radius geolokasi
- Edge case: siswa di batas radius
```

**Setelah PR:**
1. Update Trello → pindah card ke "Review"
2. Catat di `.openkb/PERSONAL/<user>/sessions/YYYY-MM-DD.md`
3. Notifikasi Sandikodev via WhatsApp

**Output:** PR siap direview.

---

## 🧠 Workflow Per Role

### Developer (Fathan / Ihsan)

```
Harian:
1. Cek Trello "In Progress" → lanjutkan task
2. Buka AI Agent → "Lanjutkan task yang tadi"
3. Coding dengan bantuan AI
4. Self-review
5. Kalau stuck > 30 menit → tanya di WhatsApp

Selesai Task:
1. PR → "Ready for Review"
2. Trello → "Review"
3. Ambil task baru dari "Ready"
```

### Product Analyst (Ahmad Hanif)

```
Harian:
1. Cek feedback dari stakeholder
2. Update requirement di Trello jika perlu
3. Test fitur yang masuk "Testing" column

Selesai UAT:
1. Approve → pindah ke "Done"
2. Reject → pindah ke "Ready" + komentar
```

### Tech Lead (Sandikodev)

```
Harian:
1. Review PR yang masuk (target < 24 jam)
2. Cek Trello "Review" column
3. Unblock developer yang stuck

Sprint:
1. Planning & retrospective
2. Update ADR jika ada keputusan baru
```

### Stakeholder (Pak Mahfud)

```
Per Sprint:
1. Review demo di akhir sprint
2. Approve / feedback via Trello
3. Keputusan prioritas jika ada perubahan scope
```

---

## 🛡️ Keamanan AI Agent

### Yang Boleh
- AI baca file `.md`, `.php`, `.js`, `.blade.php`, `.json`
- AI tulis kode di branch fitur
- AI running `composer test`, `bun run build`
- AI akses Trello via MCP (baca card, update status)

### Yang Tidak Boleh
- ❌ AI commit langsung ke `main` atau `develop`
- ❌ AI akses `.env`, credentials, API keys
- ❌ AI running `php artisan migrate` di production
- ❌ AI delete data di database
- ❌ AI push tanpa PR (kecuali hotfix dengan approval Sandikodev)

### Environment Variable Setup
```bash
# Buat file env terpisah untuk AI
notepad $HOME/.config/opencode/secrets.env
# Isi: TRELLO_API_KEY=xxx, TRELLO_TOKEN=xxx

# Referensi di opencode.json
# "env": "~/.config/opencode/secrets.env"
```

---

## 🔄 Integrasi Multi-Tool

### Tool Matrix

| Tool | Use Case | Cocok Untuk |
|---|---|---|
| **Opencode CLI** | Task kompleks, code generation, refactor | Semua developer |
| **Cursor IDE** | Daily coding, inline AI, debugging | Developer yang suka GUI |
| **Claude Code** | Alternatif Opencode (vendor diversity) | Semua developer |
| **Claw Code** | Open-source Claude alternatif | Evaluasi (anti vendor lock-in) |

### Switching Antar Tool
```bash
# Semua tool membaca konfigurasi yang sama:
# .opencode/SHARED/* → project context
# ~/.openkb/PERSONAL/<user>/* → personal context
# ~/.openkb/ROLES/<role>.md → role instructions

# Jadi bebas ganti tool tanpa kehilangan konteks.
```

---

## 📚 Contoh Sesi AI Agent

### Sesi 1: Ihsan mengerjakan backend task

```
User:  "Kerjakan Issue #12 tentang attendance validation"
AI:    "Baik, saya sudah baca Issue #12. Requirement:
        - Validasi kalender akademik (hari libur/tidak)
        - Validasi hari aktif (jadwal piket)
        - Validasi rentang jam presensi
        - Geolokasi (radius 50m dari sekolah)
        
        Saya akan mulai dengan migration dulu."
       
       *Menulis migration, model, controller*
       
       "Migration sudah siap. Jalankan? (y/n)"
```

### Sesi 2: Hanif menulis user story

```
User:  "Bantu saya tulis user story untuk fitur laporan presensi"
AI:    "Tentu. Siapa yang akan menggunakan fitur ini?"
User:  "Wali kelas"
AI:    "Apa yang wali kelas ingin lihat?"
User:  "Rekap kehadiran siswa per bulan"
AI:    "Baik, ini draft user story:
        
        Sebagai wali kelas
        Saya ingin melihat rekap kehadiran siswa per bulan dalam bentuk tabel
        Agar saya dapat memantau kehadiran siswa di kelas saya
        
        Acceptance Criteria:
        1. Filter: bulan, tahun, kelas
        2. Kolom: nama, total hadir, sakit, izin, alfa
        3. Export Excel
        
        Ada yang ingin ditambahkan?"
```

---

## 📈 Metrics & Tracking

| Metric | Target | Cara Ukur |
|---|---|---|
| Cycle time (Ready → Done) | < 3 hari | Trello / GitHub |
| PR review time | < 24 jam | GitHub |
| Code review iteration | < 3x per PR | GitHub |
| AI session productivity | Task selesai per hari | Trello velocity |
| Tool adoption | Semua developer pakai AI | Survey bulanan |

---

*Dokumen ini adalah bagian dari [playbook Koneksi](../../README.md).*
