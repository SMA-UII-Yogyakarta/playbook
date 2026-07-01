# Project Manager

> Role untuk Sandikodev — pengelola sprint, backlog, dan komunikasi stakeholder.
> Fokus: planning, tracking, reporting, dan risk management.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `project-manager` |
| **Dibuat** | 2026-06-25 |
| **Maintainer** | Sandikodev |
| **Level** | Lead |

---

## Ringkasan

Project Manager bertanggung jawab atas perencanaan sprint, pengelolaan backlog, tracking progress, dan komunikasi stakeholder. Role ini memastikan tim tetap fokus pada prioritas tertinggi dan hambatan segera diangkat.

---

## Tanggung Jawab

### 1. Sprint Planning & Management (30%)
- Sprint planning setiap 2 minggu
- Backlog refinement & prioritization
- Task estimation (Planning Poker)
- Capacity planning
- Sprint retrospective

### 2. Stakeholder Communication (25%)
- Progress reporting ke Pak Mahfud
- Manage ekspektasi client
- Escalation management
- Demo preparation

### 3. Risk & Issue Management (20%)
- Identifikasi risk sejak awal sprint
- Tracking blocker dan dependencies
- Mitigation plan
- Decision log maintenance

### 4. Process Improvement (15%)
- Refine workflow berdasarkan retro
- Update playbook documentation
- Metrics tracking (velocity, cycle time)
- Tool evaluation & optimization

### 5. Resource Management (10%)
- Tim allocation antar project
- Onboarding anggota baru
- Tools & license management
- Budget tracking

---

## AI Instructions

### Konteks Role
Saya adalah **Project Manager** di PT Koneksi Jaringan Indonesia. Saya mengelola sprint, backlog, dan komunikasi dengan stakeholder (Pak Mahfud). Saya perlu AI untuk membantu saya dalam planning, tracking, dan reporting.

### Cara AI Harus Membantu
1. **Sprint planning assistant** — Bantu breakdown epics menjadi task, estimasi effort, dan identifikasi dependencies.
2. **Status report generator** — Berdasarkan data Trello/GitHub, bantu saya membuat status report untuk stakeholder.
3. **Risk identifier** — Analisis sprint backlog dan ingatkan potensi risk: "Task ini dependen pada X yang belum selesai."
4. **Retro prompt** — Saat sprint selesai, AI harus prompt: "Apa yang berjalan baik? Apa yang perlu diperbaiki? Action items?"
5. **English-only** — All stakeholder communication and documentation in English
6. **Data-driven** — Saat melaporkan progress, sertakan metrik: story points completed, cycle time, bug count.

### Constraints
- Jangan janjikan timeline ke stakeholder tanpa konsultasi tim
- Jangan over-commit capacity — jaga buffer 20% per sprint
- Jangan skip retrospective — ini adalah mekanisme improvement utama

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (ALL repos) | admin | Manage issues, milestones, projects |
| GitHub Organization | admin | Team management, repo creation |
| Trello (ALL boards) | admin | Manage boards, cards, permissions |
| Google Calendar | manage | Sprint events, meetings |
| Google Drive | edit | Dokumen project, report |
| WhatsApp Group | admin | Komunikasi tim & stakeholder |

---

## Output yang Diharapkan

- Sprint plan siap H-1 sprint berikutnya
- Progress report mingguan untuk stakeholder
- Backlog selalu terprioritaskan dan refined
- Risk register yang terupdate tiap sprint
- Meeting notes untuk setiap session penting

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Project Manager | - |
| Next | Program Manager | Multiple projects, > 10 orang |
| Next | Delivery Head | Organization-level delivery |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Tech Lead (Sandikodev) | Technical feasibility, effort estimation |
| Product Analyst (Hanif) | Backlog grooming, priority setting |
| Stakeholder (Pak Mahfud) | Progress reporting, expectation management |
| Developer (Fathan, Ihsan) | Daily standup, blocker resolution |

---

## Contoh Penggunaan di opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/sandikodev/profile.md",
    "~/.openkb/ROLES/project-manager.md"
  ]
}
```

---

*Adapted from [team-roles.md](../docs/01-getting-started/team-roles.md).*
