# Decision Log — Playbook

Format:
```
## YYYY-MM-DD — [Judul Keputusan]
**Status**: [Proposed / Accepted / Deprecated]
**Pemutus**: [Nama]
**Konteks**: [Latar belakang / masalah]
**Keputusan**: [Apa yang diputuskan]
**Konsekuensi**: [Dampak positif & negatif]
```

---

## 2026-06-25 — Dinamic Role Definitions via ROLES/ Directory

**Status**: Accepted
**Pemutus**: Sandikodev
**Konteks**: Perlu cara standar untuk mendefinisikan role yang dinamis — bisa dipakai ulang antar project, bisa di-load oleh AI Agent, dan bisa berkembang seiring pertumbuhan anggota tim.
**Keputusan**: Buat direktori `ROLES/` di playbook dengan template (_TEMPLATE.md) dan role spesifik. Setiap role punya AI Instructions yang bisa dibaca oleh Opencode, Claude Code, Cursor, dan tools lain via `~/.openkb/ROLES/`.
**Konsekuensi**:
- (+) Role bisa dipakai ulang di project berbeda
- (+) AI Agent bisa behave sesuai role tanpa config ulang
- (-) Perlu maintenance agar role tetap up-to-date

---

## 2026-06-25 — TACO Protocol untuk AI Agent Workflow

**Status**: Accepted
**Pemutus**: Sandikodev
**Konteks**: Developer menggunakan AI Agent (Opencode, Claude Code, Cursor) tanpa workflow yang standar — perlu alur baku dari Trello → AI → Commit → Output.
**Keputusan**: Buat TACO Protocol (Trello → AI → Commit → Output) sebagai standar workflow AI Agent. Dokumentasi di WORKFLOWS/ai-agent-workflow.md.
**Konsekuensi**:
- (+) Semua developer pakai workflow yang sama
- (+) Integrasi Trello + GitHub + AI Agent jadi terstandarisasi
- (-) Perlu sosialisasi ke tim agar diadopsi

---

## 2026-06-25 — Multi-Tool AI Agent Strategy

**Status**: Accepted
**Pemutus**: Sandikodev
**Konteks**: Tim perlu fleksibilitas tools AI Agent — tidak vendor lock-in ke satu platform. Opencode sebagai primary, tapi perlu support Claude Code, Cursor, Claw Code.
**Keputusan**: Config untuk multi-tool disimpan di tiap repo: `.opencode/` (opencode), `.cursorrules` (Cursor), `.claude/settings.json` (Claude Code). Semua tool membaca konteks dari file yang sama (`.opencode/SHARED/`, `.openkb/`).
**Konsekuensi**:
- (+) Bebas pilih tool tanpa kehilangan konteks
- (+) Anti vendor lock-in (Claw Code sebagai opsi open source)
- (-) Perlu maintain config di 3 format berbeda
