# Learning Mentor — Role Definition

> **Role:** Learning Mentor / Technical Buddy  
> **Reports to:** Project Manager (Sandikodev)  
> **Level:** Junior+ (konseptual matang, eksplorasi aktif)

---

## 📋 Ringkasan

**Learning Mentor** adalah technical buddy untuk Fathan (Junior Frontend) dan Ihsan (Junior Backend). Azis ditempatkan sebagai **teman diskusi** — bukan menggurui, tapi *ngoding bareng*. Tugas utamanya adalah membantu Fathan & Ihsan menyelesaikan blocker teknis, menjelaskan konsep, dan mempersiapkan code review sebelum dikirim ke Sandikodev.

Azis tidak mengerjakan task fitur — task-nya adalah **membantu Fathan & Ihsan menyelesaikan task mereka**.

---

## 🎯 Tanggung Jawab

### 1. Discussion Partner (30%)

| Task | Deskripsi |
|------|-----------|
| **Diskusi teknis** | Teman ngobrol untuk masalah coding — bukan "guru", tapi "teman yang lebih dulu paham" |
| **Pair coding** | Duduk bareng (screen share) untuk resolve task yang Fathan/Ihsan anggap sulit |
| **Code review prep** | Review awal sebelum PR dikirim ke Sandikodev — cari typo, N+1, logical error, TypeScript type issue |
| **Alternative solutions** | Diskusikan "apa kata Stack Overflow vs dokumentasi resmi" |

### 2. Concept Explainer (25%)

| Topik | Siapa | Prioritas |
|-------|------|-----------|
| **React hooks + TypeScript** | Fathan | 🔴 High |
| **InertiaJS (routing, form, page)** | Fathan | 🔴 High |
| **Tailwind CSS 4 + responsive** | Fathan | 🟠 Medium |
| **Laravel Service Layer** | Ihsan | 🔴 High |
| **Eloquent + PostgreSQL** | Ihsan | 🔴 High |
| **Sanctum + Spatie RBAC** | Ihsan | 🟠 Medium |
| **Git workflow & PR** | Keduanya | 🟠 Medium |
| **Architecture overview** | Keduanya | 🟢 Low (cukup overview) |

**Metode:**
- 1-on-1 session (30-60 menit) — jadwal flexible
- Pair debugging — duduk bareng selesaiin error
- Live coding — demo konsep sambil ngetik
- Whiteboard / Excalidraw untuk arsitektur

### 3. Debugging Buddy (25%)

| Area | Tools | Target |
|------|-------|--------|
| **PHP/Laravel** | Artisan Tinker, Telescope, log (storage/logs) | Debugging mandiri dalam < 1 jam |
| **React/TypeScript** | Browser DevTools (Console, Network, Components), Vite HMR | Debugging mandiri dalam < 1 jam |
| **Database** | pgAdmin / DBeaver, EXPLAIN ANALYZE, Telescope queries | Identifikasi N+1 dan slow query |
| **Git** | git log, git diff, git bisect | Resolve merge conflict mandiri |

### 4. Learning Tracker (20%)

| Task | Detail |
|------|--------|
| **Environment setup** | Fasilitasi install Laragon, Bun, PostgreSQL, NeonDB — target < 1 hari |
| **Trello tracker** | Maintain card `📚 Learning Path` untuk Fathan & Ihsan |
| **Progress check** | Daily check-in 15 menit — "Ada blocker? Butuh bantuan apa?" |
| **Document common issues** | Catat error yang sering muncul + solusi di playbook atau openkb |

---

## ❌ Batasan (Apa yang Azis TIDAK lakukan)

| Area | Penjelasan |
|------|------------|
| **Keputusan arsitektur** | Bukan ranah Learning Mentor. Jika ditanya arsitektur → "Tanya Sandikodev" |
| **Final code review** | Azis bisa liat-liat, tapi final approve PR tetap Sandikodev |
| **Sprint / backlog management** | Handle sama Sandikodev & Hanif |
| **Komunikasi stakeholder** | Handle sama Sandikodev & Hanif |
| **Mengerjakan task fitur** | Azis bukan junior developer — task-nya adalah membantu Fathan & Ihsan |

---

## 🛠️ Tools & Akses

### GitHub

| Repo | Akses | Alasan |
|------|-------|--------|
| `smauii-core` | **Maintainer** | Bisa review PR, merge ke main |
| `smauii-aksesekolah` | **Maintainer** | Bisa review PR, merge ke main |
| `smauii-playbook` | **Maintainer** | Bisa update docs learning path |
| `openkb-for-junior` | **Contributor** | Bisa suggest improvement ke kurikulum |

### Trello

| Board | Role | Akses |
|-------|------|-------|
| `SMART ABSEN SMAUII` | **Member** | Bisa create/edit cards, assign tasks |
| List `📚 Learning Path` | **Owner** | Manage progress tracking Fathan & Ihsan |

### Development Environment

| Tool | Akses | Catatan |
|------|-------|---------|
| **Laragon** | Full access | Install di laptop masing-masing |
| **NeonDB** | Read-write | Dashboard untuk monitor query, branching |
| **Staging server** | SSH access | `staging.smauiiyk.sch.id` (setup nanti) |
| **Wasabi S3** | Read access | Testing object storage |
| **Cloudflare DNS** | No access | Hanya PM/Senior |

---

## 📞 Communication

### Channel

| Media | Fungsi | Response Time |
|-------|--------|---------------|
| **Trello comments** | Task-specific discussion | < 4 jam |
| **WhatsApp group** | Quick question, urgent blocker | < 1 jam |
| **Discord (optional)** | Screen sharing, pair debugging | Scheduled session |
| **Email** | Formal documentation | < 24 jam |

### Escalation Path

```
Junior Developer (Fathan/Ihsan)
    │
    ├── Quick question / stuck < 30 menit
    │   └── → Learning Mentor (Azis)
    │
    ├── Butuh debugging / pair programming
    │   └── → Learning Mentor (Azis)
    │
    ├── Blocker > 2 jam / arsitektur question
    │   └── → PM/Senior (Sandikodev)
    │
    └── Requirement ambiguity
        └── → Product Analyst (Hanif) + PM/Senior (Sandikodev)
```

---

## 📊 Success Metrics

| Metric | Target | Cara Ukur |
|--------|--------|-----------|
| **Environment setup time** | < 1 hari per junior | Time from clone to first successful run |
| **Blocker resolution time** | < 4 jam | Time from question to solution |
| **Learning progress** | 1 sprint = 2 fase | Trello checklist completion |
| **Code review turnaround** | < 24 jam | Time from submit to first review |
| **Junior satisfaction** | > 4.0/5.0 | Monthly survey (qualitative) |
| **Junior independence** | Mandiri di Sprint 4 | Final assessment (Level 3) |

---

## 🚀 Onboarding Checklist (Azis)

### Week 1: Orientation

- [ ] Clone semua repo: `core`, `aksesekolah`, `playbook`, `openkb-for-junior`
- [ ] Setup Laragon + PostgreSQL + Bun di laptop sendiri
- [ ] Baca `learning-resources.md` — pahami learning path Fathan & Ihsan
- [ ] Baca `sprint-1-plan.md` — pahami target Sprint 1
- [ ] Baca ADR-002-v2, ADR-003-v2, ADR-004, ADR-005
- [ ] Invite ke Trello board + GitHub org
- [ ] Meeting kickoff dengan PM (Sandikodev)

### Week 2+ : Mentoring dimulai

- [ ] Fasilitasi setup environment Fathan & Ihsan
- [ ] Review skill baseline Fathan & Ihsan
- [ ] Mulai pair programming sesuai jadwal
- [ ] Create Trello cards untuk learning tracker
- [ ] Daily check-in (15 menit)

---

## 📝 Notes

- **Learning Mentor bukan "walking encyclopedia"** — tidak harus tahu semua jawaban. Tapi harus tahu **cara mencari** jawaban (dokumentasi, Stack Overflow, Tinker).
- **Fokus pada empowerment** — tujuannya Fathan & Ihsan bisa mandiri di akhir Sprint 4, bukan tergantung Azis selamanya.
- **Document common issues** — jika ada pertanyaan yang sering muncul, buat catatan di playbook atau suggest improvement ke openkb-for-junior.
- **Eskalasi tepat waktu** — jika blocker > 2 jam atau ada architectural question, segera konsultasi ke Sandikodev.
- **Azis gap year, kuliah, eksplorasi aktif** — kelebihan: cara berpikir terstruktur, cepat adaptasi tool baru. Kekurangan: pengalaman lapangan masih kurang seperti Fathan & Ihsan.

---

<p align="center">
  <b>"Teaching is the highest form of understanding." — Aristotle</b>
</p>
