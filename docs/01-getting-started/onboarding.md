# Onboarding Checklist — Hari Pertama

> Checklist untuk anggota tim baru bergabung di project SMA UII Yogyakarta.

---

## ✅ Pre-Day 1 (HR/Admin)

- [ ] Diundang ke GitHub Organization `SMA-UII-Yogyakarta`
- [ ] Diundang ke Trello Board `SMART ABSEN SMAUII`
- [ ] Ditambahkan ke WhatsApp Group
- [ ] Diberikan akses ke Google Drive (jika ada)
- [ ] Diberikan laptop & equipment (jika onsite)

---

## 📅 Day 1: Welcome & Setup

### Morning (09:00 - 12:00)

#### 1. Welcome Session (30 menit)
**PIC:** Sandikodev

- Perkenalan tim
- Overview project SMART Absen
- Visi & misi PT Koneksi Jaringan Indonesia
- Ekspektasi 8 minggu (MVP + Production)

#### 2. GitHub & Git Setup (30 menit)
**PIC:** Sandikodev

- [ ] Accept invitation GitHub Organization
- [ ] Setup 2FA di GitHub
- [ ] Generate SSH Key
- [ ] Add SSH Key ke GitHub
- [ ] Test: `git clone git@github.com:SMA-UII-Yogyakarta/playbook.git`

```bash
# Generate SSH Key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Add ke GitHub
# Settings → SSH and GPG keys → New SSH Key
```

#### 3. Environment Setup (2 jam)
**PIC:** Developer masing-masing (dibantu Azis)

Ikuti panduan: [`environment-setup.md`](environment-setup.md)

- [ ] Install Laragon 6.0
- [ ] Setup PostgreSQL 16 (Laragon) atau daftar NeonDB
- [ ] Install Bun (package manager frontend)
- [ ] Install Composer
- [ ] Install VS Code + extensions
- [ ] Clone repository `core` ke `C:\laragon\www\smauii-core`
- [ ] Setup `.env` (PostgreSQL connection)
- [ ] Jalankan `composer install`
- [ ] Jalankan `bun install`
- [ ] Test: `php artisan migrate`
- [ ] Test: `bun run dev`

#### 4. Git & GitHub Workflow (1 jam)
**PIC:** Sandikodev

Baca: [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)

- [ ] Pahami branching strategy
- [ ] Pahami conventional commits
- [ ] Pahami Pull Request workflow
- [ ] Pahami code review process

---

### Afternoon (13:00 - 17:00)

#### 5. Trello & Project Management (1 jam)
**PIC:** Ahmad Hanif

Baca: [`trello-workflow.md`](../02-workflow/trello-workflow.md)

- [ ] Accept Trello invitation
- [ ] Pahami board structure
- [ ] Pahami cara baca card
- [ ] Pahami Definition of Ready (DoR)
- [ ] Pahami Definition of Done (DoD)

#### 6. Role-Specific Training (2 jam)

**Untuk Ahmad Hanif (Product Analyst):**
- Baca: [`user-story.md`](../04-templates/user-story.md)
- Latihan: Buat 3 user story untuk Sprint 1
- Setup: Template acceptance criteria

**Untuk Fathan (Junior Frontend Developer):**
- Review: TypeScript dasar (tipe, interface)
- Review: React hooks (useState, useEffect)
- Setup: VS Code extensions (Tailwind CSS, ESLint, Prettier)
- Latihan: Buat komponen React + TypeScript sederhana (Counter / Todo List)
- Pastikan Vite + Tailwind berjalan: `bun run dev`

**Untuk Ihsan (Junior Backend Developer):**
- Review: Eloquent ORM + Service Layer concept
- Review: PostgreSQL basics (connect, migration, query)
- Setup: pgAdmin / DBeaver untuk PostgreSQL
- Latihan: Buat migrasi + model + service + controller (CRUD satu tabel)

**Untuk Azis (Learning Mentor):**
- Review: Seluruh playbook (README, ADRs, team-roles, learning-resources)
- Pahami Service Layer pattern + InertiaJS + React architecture
- Pahami scope mentoring — diskusi, debugging, bukan ngoding fitur

#### 7. Q&A Session (30 menit)
**PIC:** Sandikodev

- Tanya jawab semua hal yang belum jelas
- Diskusi ekspektasi role
- Setting goals 2 minggu pertama

---

## 📅 Day 2-3: Shadowing & First Task

### Day 2

#### Morning
- [ ] Shadowing — lihat Azis atau Sandikodev ngoding
- [ ] Baca dokumentasi existing di playbook + aksesekolah/docs
- [ ] Pahami ERD database (PostgreSQL)

#### Afternoon
- [ ] Ambil first task (good first issue) dari GitHub Project
- [ ] Buat branch pertama
- [ ] Commit pertama
- [ ] Buat Pull Request pertama (dummy)

### Day 3

#### Morning
- [ ] Azis review awal PR
- [ ] Fix berdasarkan review Azis
- [ ] Sandikodev review final
- [ ] Merge PR pertama

#### Afternoon
- [ ] Mulai task Sprint 1 yang sebenarnya
- [ ] Standup meeting pertama (15 menit)

---

## 📅 Week 1 Goals

- [ ] Environment development berjalan (Bun, PostgreSQL, Vite)
- [ ] Minimal 1 PR merged ke main
- [ ] Mengerti workflow Git → PR → Review → Merge
- [ ] Mengerti cara baca user story
- [ ] Mengerti Definition of Ready & Done

---

## 📅 Week 2 Goals

- [ ] Minimal 2 task selesai di Sprint 1
- [ ] Code review quality meningkat
- [ ] Mulai mandiri (bisa tanya Azis dulu sebelum eskalasi ke Sandikodev)
- [ ] Aktif di standup meeting

---

## 📚 Resources Wajib Dibaca

### Semua Tim
- [ ] [`README.md`](../README.md) — Overview playbook
- [ ] [`team-roles.md`](team-roles.md) — Detail peran
- [ ] [`communication.md`](../02-workflow/communication.md) — Komunikasi tim

### Developer
- [ ] [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)
- [ ] [`code-review.md`](../03-sop/code-review.md)
- [ ] [`testing.md`](../03-sop/testing.md)

### Product Analyst
- [ ] [`user-story.md`](../04-templates/user-story.md)
- [ ] [`trello-workflow.md`](../02-workflow/trello-workflow.md)

---

## ✅ Onboarding Completion Checklist

Diisi oleh Sandikodev di akhir Week 1

- [ ] Environment setup ✅ (Bun, PostgreSQL, Vite, Laragon)
- [ ] Git workflow dipahami ✅
- [ ] First PR merged ✅
- [ ] Role understanding jelas ✅
- [ ] Communication lancar ✅
- [ ] Siapa Azis dan bagaimana cara minta bantuan ✅
- [ ] Ready untuk Sprint 1 ✅

**Notes:**
```
[Isi catatan performance & area improvement]
```

---

## 🆘 Jika Ada Masalah

| Masalah | Solusi | PIC |
|---|---|---|
| Git error | Re-clone, cek SSH key | Sandikodev |
| Database tidak connect | Cek `.env`, PostgreSQL service | Azis / Ihsan |
| Bun / Vite error | Cek `bun install`, restart terminal | Azis / Fathan |
| Port conflict | Cek Laragon virtual host | Sandikodev |
| Requirement tidak jelas | Tanya Ahmad Hanif | Ahmad Hanif |
| Task blocker > 30 menit | Tanya Azis dulu | Azis |
| Task blocker > 2 jam | Eskalasi ke Sandikodev | Sandikodev |

---

**Next Step:** [`environment-setup.md`](environment-setup.md)
