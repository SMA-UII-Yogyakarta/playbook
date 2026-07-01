# Senior Developer / Tech Lead

> Role untuk Sandikodev — arsitek, mentor, dan penjaga kualitas kode.
> Fokus: arsitektur, mentoring, code review, dan pengambilan keputusan teknis.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `senior-developer` |
| **Dibuat** | 2026-06-25 |
| **Maintainer** | Sandikodev |
| **Level** | Lead |

---

## Ringkasan

Senior Developer dan Tech Lead bertanggung jawab atas arsitektur sistem, mentoring junior developer, code review, dan memastikan kualitas & keamanan kode. Tidak boleh menjadi bottleneck — alokasi coding maksimal 30-40% dari total waktu.

---

## Tanggung Jawab

### 1. Architecture & Technical Design (30%)
- System architecture (monorepo, API design, database schema)
- Technology stack decisions
- Security & scalability planning
- Infrastructure & deployment strategy

### 2. Mentoring & Team Development (30%)
- Code review dengan feedback konstruktif
- Pair programming untuk task kompleks
- Knowledge sharing session (mingguan)
- Career growth tracking untuk junior developer

### 3. Code Review & Quality Assurance (20%)
- Review semua Pull Request sebelum merge
- Ensure coding standard (PSR-12, Laravel conventions)
- Check security best practices
- Performance optimization

### 4. Sprint Planning & Project Management (10%)
- Sprint planning meeting (setiap 2 minggu)
- Backlog refinement
- Task estimation & assignment
- Stakeholder communication (Pak Mahfud, SMA UII)

### 5. Hands-on Development (10%)
- Critical features (SSO, authentication core)
- Bug fixing production
- Performance bottleneck resolution
- **Tidak** mengambil task CRUD sederhana (delegate ke junior)

---

## AI Instructions

### Konteks Role
Saya adalah **Senior Developer & Tech Lead** di PT Koneksi Jaringan Indonesia. Saya mengawasi 2 junior developer (Fathan, Ihsan) dan 1 product analyst (Hanif). Saya perlu AI untuk membantu saya dalam arsitektur, review kode, dan mentoring.

### Cara AI Harus Membantu
1. **Help me think in architecture** — Saat saya mendeskripsikan masalah, AI harus membantu saya memikirkan trade-off, scalability, dan security implications sebelum memberikan solusi.
2. **Code review assistant** — Berikan review checklist yang lengkap: security (SQL injection, XSS, CSRF), performance (N+1 query), coding standard (PSR-12), dan konsistensi arsitektur.
3. **Mentoring mode** — Saat saya bertanya tentang cara mengajarkan konsep ke junior, AI harus memberikan analogi sederhana dan latihan bertahap.
4. **English-only** — All architecture discussions, mentoring, and code in English
5. **Decision log** — Saat ada keputusan arsitektur, AI harus mengingatkan: "Catat di decision-log.md ya."
6. **Anti-bottleneck** — Jika saya mulai mengerjakan task CRUD, AI harus ingatkan: "Ini bisa didelegate ke junior."

### Constraints
- Jangan over-engineer — pilih solusi paling sederhana yang bisa bekerja, bukan yang paling canggih
- Jangan skip dokumentasi — setiap keputusan arsitektur harus tercatat
- Jangan tunda code review > 24 jam — tim menunggu

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (ALL repos) | admin | Full access |
| GitHub Organization | admin | Manage teams, repos, settings |
| Trello (ALL boards) | admin | Full access |
| Environment (ALL) | full | Local, staging, production |
| Cloudflare DNS | admin | Domain management |
| Wasabi / S3 | admin | Object storage |

---

## Output yang Diharapkan

- Arsitektur yang terdokumentasi (ADR di playbook)
- Junior developer yang berkembang (skill assessment naik tiap sprint)
- PR yang direview < 24 jam
- Zero critical bug di production
- Sprint velocity yang konsisten

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Tech Lead | - |
| Next | Engineering Manager | Team > 5 orang, multiple projects |
| Next | CTO | Organization-level technical strategy |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Product Analyst (Hanif) | Requirement review, priority decision |
| Junior Developer (Fathan, Ihsan) | Mentoring, code review, pair programming |
| Stakeholder (Pak Mahfud) | Progress reporting, escalation |

---

## Contoh Penggunaan di opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/sandikodev/profile.md",
    "~/.openkb/ROLES/senior-developer.md"
  ]
}
```

---

*Adapted from [team-roles.md](../docs/01-getting-started/team-roles.md).*
