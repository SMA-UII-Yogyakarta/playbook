# Learning Mentor — Role Definition

> **Role:** Learning Mentor / Technical Guide  
> **Reports to:** Project Manager (Sandikodev)  
> **Level:** Mid-Senior (technical generalist)

---

## 📋 Ringkasan

**Learning Mentor** adalah technical guide yang bertanggung jawab untuk mempercepat onboarding dan pembelajaran anggota tim junior. Fokus utama: **environment setup, debugging, dan concept explanation** — bukan code review final atau architecture decision.

---

## 🎯 Tanggung Jawab

### 1. Environment Setup & Troubleshooting

| Task | Deskripsi |
|------|-----------|
| **Laragon setup** | Install, konfigurasi PHP/Apache/MySQL, switch version |
| **Database local** | MySQL setup, user creation, import/export SQL |
| **Node.js & NPM** | Install, version management, troubleshooting |
| **Git & GitHub** | SSH key, clone repo, basic workflow |
| **Composer** | Install, dependency management |
| **Virtual hosts** | `.test` domain setup, SSL certificate |

**Tools yang digunakan:**
- Laragon 6.0
- MySQL Workbench / HeidiSQL
- Windows Terminal / PowerShell
- Git Bash

---

### 2. Debugging Session

| Task | Deskripsi |
|------|-----------|
| **Log reading** | Laravel log (`storage/logs/laravel.log`), Apache error log |
| **Telescope** | Laravel Telescope untuk request monitoring, query debug |
| **Tinker** | REPL interaktif untuk testing code snippet |
| **Browser DevTools** | Console, Network tab, debugging JavaScript |
| **Error analysis** | Stack trace reading, common error patterns |

**Tools yang digunakan:**
- Laravel Telescope
- Artisan Tinker
- Chrome/Firefox DevTools
- VS Code debugger

---

### 3. Concept Explanation

| Topik | Deskripsi |
|-------|-----------|
| **Laravel lifecycle** | Request → Bootstrap → Middleware → Controller → Response |
| **MVC architecture** | Model-View-Controller pattern di Laravel |
| **Eloquent ORM** | Relationship, query builder, eager loading |
| **Middleware** | Authentication, role-based access control |
| **Livewire/Inertia** | Reactive frontend tanpa write JavaScript |
| **SPA vs MPA vs SSR** | Rendering strategies comparison |
| **Git workflow** | Branching, PR, code review process |

**Metode:**
- 1-on-1 session (30-60 menit)
- Pair debugging
- Whiteboard explanation
- Link ke openkb-for-junior docs

---

### 4. Code Review Awal

| Aspek | Scope Learning Mentor | Scope PM/Senior |
|-------|----------------------|-----------------|
| **Syntax error** | ✅ Check & fix bersama junior | - |
| **Logic error** | ✅ Debug bersama | - |
| **Best practices** | ⚠️ Suggest improvement | ✅ Final approval |
| **Architecture** | ⚠️ Consult PM/Senior | ✅ Decision |
| **Security** | ⚠️ Basic check (SQL injection, XSS) | ✅ Deep review |
| **Performance** | ⚠️ Basic check (N+1 query) | ✅ Deep review |

**Workflow:**
1. Junior selesai task → submit ke Learning Mentor
2. Learning Mentor review awal → fix minor issues bersama
3. Submit ke PM/Senior untuk final review & merge

---

## 📚 Learning Path (Untuk Learning Mentor)

Sebelum mulai mentoring, Azis harus menguasai topik berikut dari [openkb-for-junior](https://github.com/konxc/openkb-for-junior):

### Wajib (Priority ✅)

| Fase | Topik | Dokumen Kunci |
|------|-------|---------------|
| 06 | Laravel Deep Dive | `06-02-arsitektur-laravel.md`, `06-07-middleware-dan-auth.md`, `06-08-service-layer.md` |
| 07 | Database & SQL | `07-03-relationship-dan-join.md`, `07-06-n-plus-one-problem.md` |
| 10 | Infrastruktur | `10-03-laragon-di-windows.md`, `10-05-ssh-dan-terminal.md` |
| 11 | Tools | `11-04-artisan-cli.md`, `11-05-tinker-dan-repl.md` |
| 12 | Testing | `12-05-debugging-strategy.md` |

### Pendukung (Priority ⚡)

| Fase | Topik | Dokumen Kunci |
|------|-------|---------------|
| 09 | Frontend | `09-01-cara-kerja-vite.md`, `09-03-alpine-js.md` |
| 08 | Design Pattern | `08-02-mvc-architecture.md`, `08-03-service-pattern.md` |

###Referensi Tambahan

- [`laravel-telescope.md`](https://github.com/konxc/openkb-for-junior/blob/main/laravel-telescope.md)
- [`laragon-vs-artisan-serve.md`](https://github.com/konxc/openkb-for-junior/blob/main/laragon-vs-artisan-serve.md)
- [`memahami-ekosistem-web-laravel.md`](https://github.com/konxc/openkb-for-junior/blob/main/memahami-ekosistem-web-laravel.md)

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
    ├── Question tentang environment/setup
    │   └── → Learning Mentor (Azis)
    │
    ├── Question tentang architecture/decision
    │   └── → PM/Senior (Sandikodev)
    │
    └── Blocker > 1 hari
        └── → PM/Senior (Sandikodev)
```

---

## 📊 Success Metrics

| Metric | Target | Cara Ukur |
|--------|--------|-----------|
| **Environment setup time** | < 1 hari per junior | Time from clone to first successful run |
| **Blocker resolution time** | < 4 jam | Time from question to solution |
| **Learning progress** | 1-2 fase/minggu | Trello checklist completion |
| **Code review turnaround** | < 24 jam | Time from submit to first review |
| **Junior satisfaction** | > 4.0/5.0 | Monthly survey (qualitative) |

---

## 🚀 Onboarding Checklist (Azis)

### Week 1: Orientation

- [ ] Clone semua repo: `core`, `aksesekolah`, `playbook`, `openkb-for-junior`
- [ ] Setup Laragon di laptop sendiri
- [ ] Baca `learning-resources.md` — pahami learning path Fathan & Ihsan
- [ ] Baca `sprint-1-plan.md` — pahami target Sprint 1
- [ ] Invite ke Trello board + GitHub org
- [ ] Meeting kickoff dengan PM (Sandikodev)

### Week 2: Mentoring dimulai

- [ ] Fasilitasi setup environment Fathan & Ihsan
- [ ] Review Fase 01-03 bersama (cepat)
- [ ] Mulai Fase 06 (Laravel) — session 1-on-1
- [ ] Setup Telescope untuk debugging
- [ ] Create Trello cards untuk learning tracker

### Week 3-4: Full mentoring

- [ ] Daily check-in (15 menit standup)
- [ ] Debugging session sesuai kebutuhan
- [ ] Review progress learning path
- [ ] Adjust pace berdasarkan pemahaman junior

---

## 📝 Notes

- **Learning Mentor bukan "walking encyclopedia"** — tidak harus tahu semua jawaban. Tapi harus tahu **cara mencari** jawaban (dokumentasi, Stack Overflow, Tinker).
- **Fokus pada empowerment** — tujuannya junior bisa mandiri, bukan tergantung mentor selamanya.
- **Document common issues** — jika ada pertanyaan yang sering muncul, buat catatan di playbook atau suggest improvement ke openkb-for-junior.
- **Eskalasi tepat waktu** — jika blocker > 1 hari atau ada architectural question, segera konsultasi PM/Senior.

---

<p align="center">
  <b>"Teaching is the highest form of understanding." — Aristotle</b>
</p>