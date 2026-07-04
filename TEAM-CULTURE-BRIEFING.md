# DOKUMEN BRIEFING TIM
## PT Koneksi Jaringan Indonesia — Software House Culture

> **Versi:** 1.0  
> **Tanggal:** 2026-07-07 (Selasa Malam — *malam Rabu*)  
> **Durasi Meeting:** 18:00 - 23:00 WIB  
> **Peserta:** Sandikodev, Azis, Fathan, Ihsan, Hanif  
> **Tujuan:** Evaluasi menyeluruh + sosialisasi budaya kerja software house yang sehat, selaras tagline **TERARAH — TERAMPIL — TERUKUR**

---

## DAFTAR ISI

1. [PREAMBLE & KONTEKS](#1-preamble--konteks)
2. [IDENTITAS & VISI](#2-identitas--visi)
3. [EVALUASI TIM MENDALAM](#3-evaluasi-tim-mendalam)
4. [PERAN & EKSPEKTASI DETAIL](#4-peran--ekspektasi-detail)
5. [SISTEM KOMUNIKASI & ESKALASI](#5-sistem-komunikasi--eskalasi)
6. [WORKFLOW & SOP](#6-workflow--sop)
7. [KONSEKUENSI & AKUNTABILITAS](#7-konsekuensi--akuntabilitas)
8. [LEARNING PATH & KOMPETENSI](#8-learning-path--kompetensi)
9. [RENCANA AKSI (ACTION PLAN)](#9-rencana-aksi-action-plan)
10. [PENUTUP & KOMITMEN](#10-penutup--komitmen)

---

## 1. PREAMBLE & KONTEKS

### 1.1. Mengapa Meeting Ini Diadakan

Proyek **SMART Absen SMA UII** adalah proyek riil dengan klien nyata (Pak Mahfud — IT Manager SMA UII), budget Rp 8.500.000, dan target MVP end of Sprint 2. Ini **bukan latihan** — ini proyek produksi yang akan dipakai oleh 760+ siswa setiap hari.

Setelah Sprint 1 berjalan, ditemukan masalah sistemik yang **tidak bisa dibiarkan**:

| Masalah | Dampak |
|---------|--------|
| Sandikodev mengerjakan hampir semua | Bottleneck — tim tidak berkembang |
| Azis pasif, tidak menjalankan peran mentor | Junior tidak punya tempat bertanya |
| Fathan & Ihsan tidak escalate saat stuck | Mandek berhari-hari tanpa progress |
| Dokumen tidak dibaca | Pengetahuan tidak terserap |
| Tidak ada daily standup | Tidak ada akuntabilitas harian |
| Tidak ada rasa urgensi | Deadline terlewat, kualitas turun |

**Tujuan meeting ini:** Bukan untuk menyalahkan, tapi untuk **memperbaiki sistem**. Setiap orang punya peran, dan peran itu harus dijalankan. Kalau sistemnya yang salah, kita perbaiki sistemnya. Kalau orangnya yang tidak menjalankan, kita perlu bicara terbuka.

### 1.2. Filosofi Dasar

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│   SETIAP ORANG ADALAH PROFESIONAL                  │
│                                                     │
│   • Profesional = melakukan yang seharusnya         │
│     dilakukan, bahkan ketika tidak diawasi          │
│                                                     │
│   • Tim solid = setiap orang menjalankan perannya   │
│     dengan kesadaran penuh                          │
│                                                     │
│   • Software house = pabrik kode berkualitas,        │
│     bukan tempat nunggu perintah                    │
│                                                     │
└─────────────────────────────────────────────────────┘
```

---

## 2. IDENTITAS & VISI

### 2.1. PT Koneksi Jaringan Indonesia

PT Koneksi Jaringan Indonesia adalah **software house** — perusahaan yang menjual **solusi perangkat lunak** kepada klien. Kita tidak bekerja untuk diri sendiri; kita bekerja untuk klien yang membayar.

**Konsekuensi:**
- Klien tidak peduli masalah internal tim
- Klien hanya peduli: **apakah produk selesai?** **apakah berkualitas?**
- Deadline adalah janji — janji harus ditepati
- Setiap keterlambatan = kehilangan kepercayaan + potensi denda

### 2.2. Tagline: TERARAH — TERAMPIL — TERUKUR

Ini bukan slogan kosong. Ini adalah **tiga pilar** yang harus meresap ke setiap aspek kerja kita.

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ● TERARAH  →  Setiap orang tahu: mau ke mana, apa         │
│                  yang harus dikerjakan hari ini, apa         │
│                  target minggu ini                           │
│                                                             │
│   ● TERAMPIL →  Skill terus meningkat. Tidak ada            │
│                  alasan "saya tidak bisa" — selalu ada       │
│                  cara untuk belajar + bertanya               │
│                                                             │
│   ● TERUKUR  →  Progress bisa diukur: story points,         │
│                  test coverage, waktu respon, jumlah         │
│                  blocker yang diselesaikan                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

#### 2.2.1. TERARAH — Breakdown

| Aspek | Pertanyaan Kunci | Jawaban yang Diharapkan |
|-------|-----------------|------------------------|
| **Harian** | "Apa yang akan kamu kerjakan hari ini?" | Satu Trello card spesifik |
| **Mingguan** | "Apa target sprint ini?" | Story points yang diassign |
| **Blocker** | "Kalau stuck, apa yang kamu lakukan?" | Langsung tanya Azis, bukan diam |
| **Prioritas** | "Apa yang paling penting?" | Sesuai prioritas di Trello, bukan keinginan sendiri |

**Akar masalah saat ini:** Tim tidak terarah. Fathan membuat component tanpa mengikuti urutan card. Ihsan mulai task baru tanpa menyelesaikan task lama. Azis tidak punya daily plan karena tidak ada standup.

#### 2.2.2. TERAMPIL — Breakdown

| Aspek | Ekspektasi | Realita Saat Ini |
|-------|-----------|------------------|
| **Self-learning** | Baca dokumen yang sudah diberikan | ❌ Tidak dibaca |
| **Pair programming** | 2x seminggu dengan Azis | ❌ Tidak jalan |
| **Escalasi** | Stuck > 15 menit → tanya | ❌ Diam berhari-hari |
| **Code quality** | Tanya sebelum coding, bukan setelah error | ❌ Nunggu disalahkan baru ngomong |

**Akar masalah:** Azis tidak aktif menjemput bola. Fathan & Ihsan menunggu diperintah, bukan proaktif belajar.

#### 2.2.3. TERUKUR — Breakdown

| Metrik | Target | Cara Ukur | PIC |
|--------|--------|-----------|-----|
| **Sprint completion** | 100% task selesai | Trello Done | Sandikodev |
| **Blocker resolution** | < 4 jam | Time from first report to solved | Azis |
| **Escalation response** | < 1 jam dari Azis | WA response time | Azis |
| **Code review** | < 24 jam | PR to review | Azis → Sandikodev |
| **Test coverage** | > 70% | PHPUnit / Jest | Masing-masing |
| **Daily standup** | 100% | WA Group setiap hari | Semua |

---

## 3. EVALUASI TIM MENDALAM

### 3.1. Apa yang Sudah Berjalan Baik (✅)

1. **Backend solid (BE-001 s/d BE-011)** — 11 cards, 38 story points, selesai 100%. Ini pencapaian luar biasa dari Sandikodev.
2. **Frontend landing page & routing (FE-001 s/d FE-005)** — 6 layouts, 28 components, 17 pages. Selesai dengan commit traceable.
3. **Master plan komprehensif** — 15 sections, ~700 lines. Dokumentasi requirement lengkap.
4. **Arsitektur enterprise** — Dual Controller, Service Layer, Form Request, RBAC, Triple-Layer Validation.

### 3.2. Apa yang Tidak Berjalan (❌)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ⚠️  MASALAH #1 — ESKALASI RUSAK                          │
│                                                             │
│   Fathan stuck (Figma → TSX)       →  diam 2+ minggu        │
│   Ihsan bingung mulai dari mana   →  diam, ganti-ganti task │
│   Azis tidak check-in             →  tidak tahu kondisi     │
│                                                             │
│   AKIBAT: Sandiko baru tahu saat ditanya "kok belum         │
│   selesai?" — ini terlalu lambat.                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ⚠️  MASALAH #2 — DOKUMEN TIDAK DIBACA                    │
│                                                             │
│   Dokumen yang sudah diberikan:                             │
│   • WORKFLOW-FIGMA-FRONTEND.md     →  ❌ tidak dibaca        │
│   • PANDUAN-KONVERSI-FIGMA-KE-REACT.md → ❌ tidak dibaca    │
│   • WORKFLOW-FRONTEND-BACKEND.md   →  ❌ tidak dibaca        │
│   • development-workflow.md        →  ❌ tidak dibaca        │
│   • starter-guide.md               →  ❌ tidak dibaca        │
│   • team-playbook.md               →  ❌ tidak dibaca        │
│   • master-plan.md                 →  ❌ tidak dibaca        │
│                                                             │
│   PERTANYAAN: Kalau dokumen tidak dibaca, bagaimana         │
│   bisa terarah dan terampil?                                │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ⚠️  MASALAH #3 — AZIS TIDAK MENJALANKAN PERAN            │
│                                                             │
│   Peran Azis (dari playbook ROLES/learning-mentor.md):      │
│                                                             │
│   Tanggung Jawab               Status                       │
│   ├── Daily check-in 15 menit  ❌ Tidak pernah               │
│   ├── Pair programming 2x/mgg  ❌ Tidak pernah               │
│   ├── Debugging buddy          ❌ Tidak ada laporan blocker  │
│   ├── Code review prep         ❌ PR langsung ke Sandiko     │
│   ├── Learning tracker         ❌ Card LP tidak diurus       │
│   └── Eskalasi > 2 jam         ❌ Tidak ada                  │
│                                                             │
│   DAMPAK: Fathan & Ihsan tidak punya tempat bertanya,       │
│   akhirnya stuck dan diam.                                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ⚠️  MASALAH #4 — SAN DIKO BOTTLENECK                      │
│                                                             │
│   Playbook bilang: Sandiko coding ≤ 30% waktu               │
│   Realita: Sandiko coding ~80% waktu                        │
│                                                             │
│   Yang seharusnya:                                          │
│   • 30% Coding — hanya arsitektur & fitur kritis            │
│   • 30% Mentoring — guide junior, bukan ngerjain tugasnya   │
│   • 20% Code review — final review setelah Azis prep        │
│   • 10% Planning — sprint planning, backlog                 │
│   • 10% Stakeholder — komunikasi klien                      │
│                                                             │
│   DAMPAK: Tim tidak berkembang. Sandiko capek.              │
│   Proyek bergantung satu orang = risiko besar.              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 3.3. Diagram: ALUR KOMUNIKASI

#### ❌ ALUR SAAT INI (Rusak)

```
                    ┌──────────────────┐
                    │   SANDIKODEV     │
                    │  (PM/Architect)  │
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
        ┌──────────┐  ┌──────────┐  ┌──────────┐
        │  AZIS   │  │ FATHAN  │  │  IHSAN  │
        │ (Mentor)│  │(Junior) │  │(Junior) │
        └──────────┘  └──────────┘  └──────────┘

        MASALAH:
        • Semua panah harusnya ke Azis DULU, baru ke Sandiko
        • Azis hanya menjadi anggota tim biasa, bukan mentor
        • Fathan & Ihsan tidak punya "partner ngoding"
        • Sandiko mendapat semua pertanyaan langsung
```

#### ✅ ALUR SEHARUSNYA (Berdasarkan Playbook)

```
                    ┌──────────────────┐
                    │   SANDIKODEV     │  ← Final review, arsitektur,
                    │  (PM/Architect)  │    blocker > 2 jam
                    └────────┬─────────┘
                             │
                     Eskalasi │ (hanya jika > 2 jam)
                             │
              ┌──────────────┼──────────────┐
              │              │              │
              ▼              ▼              ▼
        ┌──────────┐  ┌──────────┐  ┌──────────┐
        │  AZIS   │◄─│ FATHAN  │◄─│  IHSAN  │
        │ (Mentor)│──►│(Junior) │──►│(Junior) │
        └──────────┘  └──────────┘  └──────────┘
              │
              │  Peran Azis:
              │  • Daily check-in "Ada blocker?"
              │  • Pair programming 2x/minggu
              │  • Code review prep sebelum ke Sandiko
              │  • Debugging buddy
              │
              ▼
        ┌──────────────┐
        │   HANIF     │  ← Kalau requirement tidak jelas
        │ (Analyst)   │
        └──────────────┘
```

### 3.4. Diagram: ALUR KERJA SEHARUSNYA

```
HARI KERJA NORMAL
═══════════════════

09:00  ┌─ Daily Standup (WA Group) ─────────────────────┐
       │  Format:                                       │
       │  ✅ Kemarin: [card yang selesai]               │
       │  🎯 Hari ini: [card yang dikerjakan]           │
       │  🚫 Blocker: [ada/tidak]                       │
       └────────────────────────────────────────────────┘

09:15  ┌─ Kerja (Pomodoro 25/5) ────────────────────────┐
       │  • 25 menit fokus                               │
       │  • 5 menit istirahat                            │
       │  • Kalau stuck >15 menit → tanya Azis           │
       └────────────────────────────────────────────────┘

12:00  ┌─ Istirahat ────────────────────────────────────┐
       └────────────────────────────────────────────────┘

13:00  ┌─ Kerja lanjutan ───────────────────────────────┐
       │  • Pair programming (jadwal)                    │
       │  • Code review                                  │
       │  • Self-learning / baca dokumen                 │
       └────────────────────────────────────────────────┘

17:00  ┌─ End of day ───────────────────────────────────┐
       │  • Update Trello card status                    │
       │  • Commit progress                              │
       │  • Catat blocker untuk besok                    │
       └────────────────────────────────────────────────┘
```

---

## 4. PERAN & EKSPEKTASI DETAIL

### 4.1. Sandikodev — Project Manager & Lead Developer

> **Prinsip:** "Lead by example, not by doing everything"

| Area | Harus | Tidak Boleh |
|------|-------|-------------|
| **Arsitektur** | Memutuskan arah teknis, stack, pattern | — |
| **Coding** | Hanya fitur kritis & arsitektural | > 30% waktu coding |
| **Mentoring** | 1-on-1 dengan Azis, evaluasi mingguan | Menjawab pertanyaan yang Azis bisa jawab |
| **Code Review** | Final review & merge | Review tanpa Azis prep dulu |
| **Planning** | Sprint planning, backlog grooming | Membiarkan sprint tanpa goal jelas |
| **Stakeholder** | Komunikasi klien, demo | — |

**Komitmen Sandikodev:**
- [ ] Saya akan mengurangi coding ke maksimal 30% waktu
- [ ] Saya akan melakukan 1-on-1 dengan Azis setiap minggu
- [ ] Saya akan memberikan keputusan arsitektur dalam < 24 jam
- [ ] Saya tidak akan mengerjakan task yang seharusnya Azis selesaikan dengan junior

### 4.2. Azis — Learning Mentor

> **Prinsip:** "Mengajar adalah pemahaman tertinggi. Saya bukan guru — saya teman yang lebih dulu paham."

| Area | Harus | Tidak Boleh |
|------|-------|-------------|
| **Daily check-in** | 09:00 WIB tanya Fathan & Ihsan: "Ada blocker?" | Menunggu mereka datang duluan |
| **Pair programming** | Senin+Rabu (Fathan), Selasa+Kamis (Ihsan), 45 menit | Membatalkan tanpa alasan |
| **Debugging buddy** | Bantu resolve error < 1 jam | Membiarkan junior stuck > 1 jam |
| **Code review prep** | Review awal sebelum PR ke Sandiko | Mengirim PR mentah ke Sandiko |
| **Learning tracker** | Maintain card LP Fathan & Ihsan | — |
| **Eskalasi** | Jika blocker > 2 jam → ke Sandiko | Menyimpan masalah sendiri |

**Target Harian Azis:**

```
┌────────────────────────────────────────────────────────┐
│                    AZIS — RUTINITAS                    │
├────────────────────────────────────────────────────────┤
│                                                         │
│  09:00  Daily check-in via WA                          │
│         "Halo Fathan/Ihsan, ada blocker? Butuh          │
│          bantuan?"                                       │
│                                                         │
│  10:00  Pair programming (jadwal)                      │
│  14:00  Code review prep                               │
│  17:00  Report ke Sandiko: "Hari ini Fathan...          │
│          Ihsan... blocker..."                           │
│                                                         │
└────────────────────────────────────────────────────────┘
```

**Komitmen Azis:**
- [ ] Saya akan daily check-in setiap hari pukul 09:00
- [ ] Saya akan melakukan pair programming sesuai jadwal
- [ ] Saya akan merespon pertanyaan dalam < 1 jam
- [ ] Saya akan melakukan initial code review sebelum PR ke Sandiko
- [ ] Saya akan escalate ke Sandiko jika blocker > 2 jam

### 4.3. Fathan Mubina — Junior Frontend Developer

> **Prinsip:** "Tidak tahu itu wajar. Tidak bertanya itu masalah."

| Area | Harus | Tidak Boleh |
|------|-------|-------------|
| **Coding** | Ikuti Trello card, 1 card selesai → commit | Ganti-ganti task tanpa selesai |
| **Dokumen** | Baca dokumen yang diberikan | Mengabaikan dokumen |
| **Escalasi** | Stuck > 15 menit → tanya Azis | Diam berhari-hari |
| **Pair programming** | Ikuti jadwal dengan Azis | Tidak datang tanpa konfirmasi |
| **Daily standup** | Lapor progress setiap 09:00 | Tidak merespon |
| **Commit** | 1 task = 1 commit, meaningful message | Commit asal-asalan |

**Panduan: Saat Stuck**

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│   SAAT STUCK — LANGKAH WAJIB                       │
│                                                     │
│   1. Baca error dari paling bawah (stack trace)     │
│   2. Cari di kode: grep "namaMethod" atau cek docs  │
│   3. Coba 2 pendekatan berbeda (max 15 menit)       │
│   4. KALAU MENTOK → TANYA AZIS                      │
│                                                     │
│   ⚠️  TIDAK BOLEH:                                  │
│      • Diam > 15 menit tanpa progress              │
│      • Ganti task lain tanpa menyelesaikan blocker  │
│      • Nunggu ditanya Sandiko baru ngomong          │
│                                                     │
└─────────────────────────────────────────────────────┘
```

**Komitmen Fathan:**
- [ ] Saya akan membaca dokumen yang diberikan sebelum bertanya
- [ ] Saya akan bertanya ke Azis dalam 15 menit jika stuck
- [ ] Saya akan mengerjakan 1 card sampai selesai sebelum pindah
- [ ] Saya akan ikut daily standup & pair programming

### 4.4. Ihsan — Junior Backend Developer

> **Prinsip:** Sama dengan Fathan, beda stack.

| Area | Harus | Tidak Boleh |
|------|-------|-------------|
| **Coding** | Ikuti card, fokus 1 task sampai done | Loncat-loncat task |
| **Testing** | Tulis test setelah fitur | Merge tanpa test |
| **Database** | PostgreSQL syntax, no MySQL | Pakai MySQL-specific syntax |
| **Service Layer** | Logic di Service, controller tipis | Logic di controller |
| **Escalasi** | Sama seperti Fathan | Diam |

**Komitmen Ihsan:**
- [ ] Saya akan menyelesaikan 1 card sebelum memulai yang lain
- [ ] Saya akan bertanya dalam 15 menit jika stuck
- [ ] Saya akan menulis test untuk setiap fitur yang saya buat
- [ ] Saya akan ikut daily standup & pair programming

### 4.5. Hanif — Product Analyst

> **Prinsip:** "Requirement yang jelas adalah fondasi produk yang baik."

| Area | Harus | Tidak Boleh |
|------|-------|-------------|
| **Requirement** | Jelas, testable, user story format | Ambigu |
| **UAT** | Test semua AC sebelum release | Loloskan tanpa test |
| **Backlog** | Maintain Trello, prioritas jelas | — |
| **Stakeholder** | Komunikasi dengan Pak Mahfud | Janji tanpa koordinasi dengan Sandiko |

### 4.6. Matriks Tanggung Jawab

```
┌─────────────────────────────────────────────────────────────────────┐
│                       SANDIKO    AZIS    FATHAN    IHSAN    HANIF   │
├─────────────────────────────────────────────────────────────────────┤
│ Arsitektur              ●        ◌        ◌        ◌        ◌      │
│ Coding kritis           ●        ◌        ◌        ◌        ◌      │
│ Coding fitur            ◌        ◌        ●        ●        ◌      │
│ Code review final       ●        ◌        ◌        ◌        ◌      │
│ Code review initial     ◌        ●        ◌        ◌        ◌      │
│ Daily check-in          ◌        ●        ◌        ◌        ◌      │
│ Pair programming        ◌        ●        ◌        ◌        ◌      │
│ Daily standup           ●        ●        ●        ●        ●      │
│ Testing                 ◌        ◌        ●        ●        ◌      │
│ UAT                     ◌        ◌        ◌        ◌        ●      │
│ Dokumentasi             ◌        ◌        ●        ●        ●      │
│ Sprint planning         ●        ◌        ◌        ◌        ◌      │
│ Backlog grooming        ●        ◌        ◌        ◌        ●      │
│ Stakeholder comms       ●        ◌        ◌        ◌        ◌      │
│                                                     ● = PIC utama  │
│                                                     ◌ = Pendukung  │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 5. SISTEM KOMUNIKASI & ESKALASI

### 5.1. Daily Standup

**Waktu:** Setiap hari, 09:00 WIB  
**Channel:** WhatsApp Group  
**Format Wajib:**

```
📅 Daily Standup — 8 Jul 2026
👤 [Nama]
✅ Kemarin: [card yang selesai / progress]
🎯 Hari ini: [card yang dikerjakan]
🚫 Blocker: [deskripsi atau "None"]

📊 Progress Sprint: [sisa hari] hari lagi
```

**Aturan:**
- Semua wajib merespon sebelum 10:00
- Jika ada blocker, Azis harus langsung merespon
- Jika blocker > 2 jam, Sandiko di-tag

### 5.2. Eskalasi 5 Level

```
┌──────────────────────────────────────────────────────────────────┐
│                                                                  │
│   LEVEL 0: Stuck < 15 menit                                     │
│   → Coba sendiri: baca error, search docs, coba 2 pendekatan    │
│   PIC: Diri sendiri                                              │
│                                                                  │
│       ▼                                                         │
│                                                                  │
│   LEVEL 1: Stuck 15 menit - 1 jam                               │
│   → Tanya Azis via WA/Discord                                   │
│   PIC: Azis — target resolusi < 1 jam                            │
│                                                                  │
│       ▼                                                         │
│                                                                  │
│   LEVEL 2: Stuck 1 - 2 jam (Azis tidak bisa solve)              │
│   → Pair programming Azis + junior                              │
│   PIC: Azis — screen share, debug bareng                         │
│                                                                  │
│       ▼                                                         │
│                                                                  │
│   LEVEL 3: Stuck > 2 jam (pair programming tidak cukup)         │
│   → Tag Sandiko di WA Group                                     │
│   PIC: Sandiko — target resolusi < 2 jam                        │
│                                                                  │
│       ▼                                                         │
│                                                                  │
│   LEVEL 4: Requirement tidak jelas                              │
│   → Tag Hanif di Trello comment                                 │
│   PIC: Hanif — target klarifikasi < 24 jam                       │
│                                                                  │
└──────────────────────────────────────────────────────────────────┘
```

**⚠️ YANG TIDAK BOLEH:**

```
❌ Stuck > 15 menit → diam, buka YouTube, ganti task lain
❌ Stuck > 1 jam → tetap diam, nunggu ditanya
❌ Stuck > 1 hari → pura-pura sibuk, tidak ada progress
❌ Stuck → tanya langsung Sandiko (skip Azis)
```

### 5.3. Cara Bertanya yang Efektif

```
❌ "Pak, kok error ya?"
   → Tidak informatif, Sandiko harus tanya balik 5x

✅ "Pak, saya mau bikin fitur export PDF. Saya sudah install
    dompdf, baca docs-nya, tapi pas dijalanin error 'Class not
    found'. Ini screenshot errornya. Kira-kira kenapa ya?"
   → Langsung bisa dibantu

FORMAT BERTANYA:
1. Apa yang ingin saya capai?
2. Apa yang sudah saya coba?
3. Apa yang terjadi? (screenshot error)
4. Apa yang seharusnya terjadi?
5. Apa bedanya? (gap)
```

### 5.4. Channel Komunikasi

| Channel | Untuk | Response SLA |
|---------|-------|-------------|
| **WA Group** | Daily standup, urgent blocker | < 1 jam |
| **WA Personal** | Pair programming scheduling | < 2 jam |
| **Trello comment** | Diskusi task, requirement clarifikasi | < 4 jam |
| **GitHub PR comment** | Code review discussion | < 24 jam |
| **Google Meet** | Sprint planning, review, retro | Sesuai jadwal |

### 5.5. Jadwal Pair Programming

| Hari | Waktu | Sesi | PIC |
|------|-------|------|-----|
| Senin | 10:00 - 10:45 | Azis + Fathan (Frontend) | Azis |
| Selasa | 10:00 - 10:45 | Azis + Ihsan (Backend) | Azis |
| Rabu | 10:00 - 10:45 | Azis + Fathan (Frontend) | Azis |
| Kamis | 10:00 - 10:45 | Azis + Ihsan (Backend) | Azis |
| Jumat | 15:00 - 16:00 | All team (demo + review) | Sandiko |

---

## 6. WORKFLOW & SOP

### 6.1. TACO Protocol

Setiap task di Trello dikerjakan dengan urutan:

```
T — Trello
│   • Ambil card dari "Ready" → assign ke diri sendiri
│   • Pindahkan ke "In Progress"
│   • Baca acceptance criteria & deskripsi
│
├──> A — AI (Opsional)
│   • Buka AI agent dengan role & project context
│   • Prompt yang jelas: "Saya mau buat fitur X di file Y"
│   • Review hasil AI — jangan copy-paste blind
│
├──> C — Commit
│   • 1 task = 1 commit
│   • Conventional commit: feat/fix/docs/chore(scope): message
│   • Jangan commit file rusak / error
│
└──> O — Output
    • PR dibuat (jika task selesai)
    • Trello card dipindah ke "Code Review"
    • Blocker dicatat jika ada
```

### 6.2. Git Workflow

```
Branch Strategy:

main
  └── develop
       ├── feature/BE-012-triple-layer-validation
       ├── feature/FE-007-live-presensi
       ├── bugfix/FE-006-login-error
       ├── refactor/BE-008-service-optimization
       └── ...

Conventional Commits:
  feat(attendance): add triple-layer validation
  fix(auth): resolve token expiration on safari
  docs(api): update attendance endpoint docs
  chore(deps): update openspout to 5.7.2

Aturan:
  1. 1 branch = 1 card
  2. 1 task selesai → commit, push, PR
  3. PR → self-review → Azis review → Sandiko review → merge
  4. Jangan commit ke main langsung
```

### 6.3. Code Review Process

```
Fathan/Ihsan selesai coding
    │
    ▼
Self-review (5 menit)
    • Cek typo, debug, console.log
    • Cek apakah mengikuti existing pattern
    • Jalankan test
    │
    ▼
Azis: Initial review (< 24 jam)
    • Cek: N+1 query, logical error, TypeScript type
    • Label: ❌ Critical / ⚠️ Major / 💡 Suggestion
    • Fix minor langsung, diskusi major
    │
    ▼
Sandiko: Final review (< 24 jam)
    • Cek: architecture, security, best practices
    • Approve atau request changes
    │
    ▼
Merge ke develop (squash merge)
```

### 6.4. Trello Workflow

```
Backlog
  │  (card belum di-sprint)
  ▼
Ready for Dev
  │  (card sudah diestimasi, jelas AC-nya)
  ▼
In Progress
  │  (sedang dikerjakan — hanya 2 card per orang max)
  ▼
Code Review
  │  (menunggu review Azis → Sandiko)
  ▼
UAT / Testing
  │  (menunggu test oleh Hanif)
  ▼
Done
  │  (selesai, merge, deploy)
  ▼
```

### 6.5. Sprint Cycle

```
Minggu 1 (Senin - Jumat)
═══════════════
Senin:  Sprint Planning (pagi) + mulai coding
Selasa: Coding + pair programming
Rabu:   Coding + pair programming
Kamis:  Coding + pair programming
Jumat:  Code review + documentation sync

Minggu 2 (Senin - Jumat)
═══════════════
Senin:  Coding lanjutan
Selasa: Coding lanjutan
Rabu:   Freeze fitur — fokus testing
Kamis:  UAT (Hanif) + bug fixing
Jumat:  Sprint Review + Retrospective + Planning sprint berikutnya
```

---

## 7. KONSEKUENSI & AKUNTABILITAS

### 7.1. Jika Role Tidak Dijalankan

Ini bukan tentang menghukum — ini tentang **kesepakatan bersama**. Setiap orang menandatangani komitmen di bagian 10. Jika komitmen dilanggar:

| Pelanggaran | 1x | 2x | 3x+ |
|------------|-----|-----|------|
| **Tidak daily standup** | Teguran lisan | Teguran WA grup | Evaluasi keterlibatan |
| **Stuck > 1 jam tidak tanya** | Azis diingatkan | Diskusi 1-on-1 | Evaluasi peran |
| **Azis tidak check-in** | Pengingat | 1-on-1 dengan Sandiko | Evaluasi peran mentor |
| **Dokumen tidak dibaca** | Pengingat | Diskusi kenapa | Cari metode alternatif |
| **Task tidak selesai tanpa komunikasi** | Peringatan | Review beban kerja | Realokasi task |

**Prinsip:** Konsekuensi progresif, bukan langsung hukum. Tujuan utama adalah **memperbaiki**, bukan menghukum.

### 7.2. Jika Eskalasi Tidak Berjalan

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   ATURAN BESI:                                              │
│   "Jika kamu stuck > 15 menit dan kamu diam,                │
│    itu pelanggaran serius."                                 │
│                                                             │
│   Mengapa?                                                  │
│   Karena dengan diam:                                       │
│   • Kamu membuang waktu berharga tim                        │
│   • Kamu menyembunyikan masalah                             │
│   • Deadline terancam                                       │
│   • Tim lain yang menunggu task kamu ikut terhambat         │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 7.3. Evaluasi Mingguan

Setiap Jumat, Sandiko akan melakukan evaluasi singkat:

```
EVALUASI MINGGUAN — [Nama]
═══════════════════════════
✅ Card selesai:        [jumlah / target]
✅ Pair programming:    [jumlah hadir / total]
✅ Daily standup:       [jumlah ikut / total]
✅ Dokumen dibaca:      [self-report]
✅ Escalasi tepat waktu:[jumlah escalate / jumlah stuck]
🚫 Blocker:            [deskripsi]
📈 Progress level:     [Explorer/Builder/Crafter/Master]
```

---

## 8. LEARNING PATH & KOMPETENSI

### 8.1. Level System

```
LEVEL 0 — ONBOARDING (Minggu 1)
┌─────────────────────────────────────┐
│ Bisa clone repo, setup env, jalanin │
│ aplikasi, baca struktur kode        │
└─────────────────────────────────────┘
              │
              ▼
LEVEL 1 — EXPLORER (Minggu 2-3)
┌─────────────────────────────────────┐
│ Bisa baca kode, debug sederhana,    │
│ memahami pola yang ada,             │
│ membuat task kecil dengan panduan   │
└─────────────────────────────────────┘
              │
              ▼
LEVEL 2 — BUILDER (Minggu 4-5)
┌─────────────────────────────────────┐
│ Bisa buat fitur sederhana mandiri,  │
│ butuh bantuan untuk yang kompleks,  │
│ nulis test dasar                    │
└─────────────────────────────────────┘
              │
              ▼
LEVEL 3 — CRAFTER (Minggu 6-7)
┌─────────────────────────────────────┐
│ Bisa buat fitur kompleks mandiri,   │
│ nulis test komprehensif,            │
│ melakukan code review               │
└─────────────────────────────────────┘
              │
              ▼
LEVEL 4 — MASTER (Minggu 8+)
┌─────────────────────────────────────┐
│ Bisa bikin arsitektur, mentoring,   │
│ handling production issue           │
└─────────────────────────────────────┘
```

### 8.2. Target Level per Sprint

| Person | Saat Ini | Target Sprint 2 | Target Sprint 3 | Target Sprint 4 |
|--------|----------|----------------|----------------|----------------|
| **Fathan** | Level 1 (Explorer) | Level 2 (Builder) | Level 3 (Crafter) | Level 3+ |
| **Ihsan** | Level 1 (Explorer) | Level 2 (Builder) | Level 3 (Crafter) | Level 3+ |

**Peran Azis:** Memastikan Fathan & Ihsan naik 1 level per 2 sprint.

### 8.3. Skill Checklist Fathan (Frontend)

**Level 1 → 2 (Target: Akhir Sprint 2):**
- [ ] TypeScript: tipe dasar, interface, type alias
- [ ] React: functional component, useState, useEffect, props
- [ ] Inertia: usePage, InertiaLink, InertiaForm
- [ ] Tailwind: utility class, responsive prefix, component styling
- [ ] Git: clone, add, commit, push, pull, branch, PR
- [ ] Baca dan pahami kode existing

**Level 2 → 3 (Target: Akhir Sprint 3):**
- [ ] TypeScript: generic, utility type, discriminated union
- [ ] React: custom hooks, useContext, useReducer, useMemo
- [ ] Testing: Jest + React Testing Library
- [ ] Performance: lazy loading, code splitting
- [ ] Debugging: browser devtools, network, component tree

### 8.4. Skill Checklist Ihsan (Backend)

**Level 1 → 2 (Target: Akhir Sprint 2):**
- [ ] Laravel: route, controller, model, migration, seeder
- [ ] Service Layer pattern: controller → service → model
- [ ] Eloquent: CRUD, relationship, eager loading
- [ ] PostgreSQL: migration syntax, data type, indexing
- [ ] Form Request: validation, authorization
- [ ] PHPUnit: feature test, assert, RefreshDatabase

**Level 2 → 3 (Target: Akhir Sprint 3):**
- [ ] Sanctum: token management, middleware, ability
- [ ] Spatie: role, permission, gate, blade directive
- [ ] Advanced Eloquent: scope, accessor, mutator, event
- [ ] Testing: mock, Queue fake, Event fake, HTTP test
- [ ] API Design: RESTful, status code, error handling

---

## 9. RENCANA AKSI (ACTION PLAN)

### 9.1. Minggu Ini — Langkah Segera

| # | Aksi | PIC | Deadline |
|---|------|-----|----------|
| 1 | **Azis mulai daily check-in** setiap 09:00 | Azis | Besok (9 Jul) |
| 2 | **Fathan selesaikan FE-006** (responsive test) dengan Azis pair programming | Fathan + Azis | 9 Jul |
| 3 | **Ihsan selesaikan US-004** (session management) — breakdown dengan Azis | Ihsan + Azis | 11 Jul |
| 4 | **Azis lapor progress harian** ke Sandiko pukul 17:00 | Azis | Mulai besok |
| 5 | **Azis baca ulang** `ROLES/learning-mentor.md` dan semua dokumen yang diberikan | Azis | 9 Jul |
| 6 | **Fathan & Ihsan baca ulang** semua dokumen (starter-guide, workflow, master-plan) | Fathan, Ihsan | 10 Jul |
| 7 | **Pair programming session pertama**: Azis + Fathan (Figma → composable component live demo) | Azis + Fathan | 9 Jul 10:00 |
| 8 | **Pair programming session pertama**: Azis + Ihsan (breakdown US-004) | Azis + Ihsan | 10 Jul 10:00 |

### 9.2. Sprint Ini (6 - 18 Jul 2026)

| Card | Assignee | Due | Note |
|------|----------|-----|------|
| FE-006: Responsive Testing | Fathan | 9 Jul | Selesaikan dengan Azis |
| US-004: Session Management | Ihsan | 11 Jul | Sudah di Sprint Backlog — prioritas |
| LP-01: Learning Path Fathan | Azis | 18 Jul | Maintain card, tracking progress |
| LP-02: Learning Path Ihsan | Azis | 18 Jul | Maintain card, tracking progress |
| US-005: Triple-Layer Validation | Ihsan | 18 Jul | Baru mulai setelah US-004 selesai |

### 9.3. Evaluasi: 1 Minggu Lagi

**Tanggal: Jumat, 16 Juli 2026 — Evaluasi pertama**

Pertanyaan yang akan dijawab:
1. ✅ Apakah Azis daily check-in setiap hari?
2. ✅ Apakah Fathan & Ihsan escalate saat stuck?
3. ✅ Apakah pair programming berjalan sesuai jadwal?
4. ✅ Berapa card yang selesai minggu ini?
5. ✅ Apakah dokumen mulai dibaca?
6. ⚠️ Apa yang masih belum berjalan?

Jika dalam 1 minggu tidak ada perubahan, akan ada meeting lanjutan untuk restrukturisasi tim.

### 9.4. Komitmen Bersama

Setiap anggota tim wajib mengisi komitmen berikut di akhir meeting:

```
KOMITMEN SAYA
══════════════

Saya, [NAMA], dengan ini berkomitmen untuk:

1. [  ] Menjalankan peran saya sesuai dokumen ini
2. [  ] Daily standup setiap hari pukul 09:00
3. [  ] Bertanya dalam 15 menit jika stuck (untuk junior)
         / Merespon dalam 1 jam (untuk Azis)
4. [  ] Membaca dokumen yang diberikan
5. [  ] Pair programming sesuai jadwal
6. [  ] Menyelesaikan 1 task sebelum pindah ke task lain

Jika saya melanggar komitmen ini, saya siap menerima
konsekuensi yang telah disepakati bersama.

Tanda tangan: ___________
Tanggal: 7 Juli 2026
```

---

## 10. PENUTUP & KOMITMEN

### 10.1. Kutipan Penutup

> **"Teamwork is the ability to work together toward a common vision. The ability to direct individual accomplishments toward organizational objectives. It is the fuel that allows common people to attain uncommon results."** — Andrew Carnegie

> **"Jika kamu ingin berjalan cepat, berjalanlah sendiri. Jika kamu ingin berjalan jauh, berjalanlah bersama."** — Pepatah Afrika

### 10.2. Pesan dari Sandiko ke Tim

**Untuk Fathan:**
Kamu punya potensi besar. Masalahmu bukan di skill — tapi di keberanian untuk bertanya. Figma → composable component memang susah kalau baru pertama kali. Tapi kalau kamu diam, saya tidak bisa bantu. Azis sudah disiapkan untuk jadi partner coding kamu. Manfaatkan. Jangan malu, jangan takut. Kita semua pernah junior.

**Untuk Ihsan:**
Kamu perlu fokus. Kerjakan 1 card sampai selesai. Kalau bingung urutannya, tanya. Jangan ambil card baru kalau yang lama belum selesai. Backend itu soal disiplin — ikuti pola yang sudah ada (Service Layer, Form Request, Dual Controller), dan kamu akan lihat semuanya jadi lebih mudah.

**Untuk Azis:**
Peranmu adalah yang paling krusial sekarang. Tanpa mentor yang aktif, Fathan dan Ihsan akan terus stuck. Saya butuh kamu jadi jembatan antara saya dan mereka. Kamu bukan cuma anggota tim — kamu adalah **penggerak** tim. Kalau kamu jalan, tim jalan. Kalau kamu diam, tim mandek.

**Untuk Hanif:**
Jaga requirement tetap jelas. Kalau ada yang ambigu, segera klarifikasi. UAT adalah benteng terakhir sebelum produk sampai ke klien.

**Untuk Kita Semua:**
Kita punya 8 minggu untuk menyelesaikan SMART Absen SMA UII. Ini bukan proyek biasa — ini portofolio kita bersama. Kalau proyek ini sukses, kita semua punya pengalaman berharga. Kalau gagal, kita semua yang rugi.

Mari kita buat 8 minggu ini berarti.

---

```
═══════════════════════════════════════════════════════════════
  DOKUMEN INI TELAH DIBACA DAN DIPAHAMI OLEH:
═══════════════════════════════════════════════════════════════

  Nama                    Tanda Tangan           Tanggal
───────────────────────────────────────────────────────────────
  Sandikodev              ___________            7 Jul 2026
  Azis                    ___________            7 Jul 2026
  Fathan Mubina           ___________            7 Jul 2026
  Ihsan                   ___________            7 Jul 2026
  Ahmad Hanif Hasan       ___________            7 Jul 2026

═══════════════════════════════════════════════════════════════
```

---

*Dokumen ini adalah milik PT Koneksi Jaringan Indonesia. Tidak untuk disebarluaskan tanpa izin.*
