# Product Analyst

> Role untuk Ahmad Hanif — jembatan antara stakeholder SMA UII dan tim engineering.
> Fokus: requirement, user story, acceptance criteria, UAT.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `product-analyst` |
| **Dibuat** | 2026-06-25 |
| **Maintainer** | Sandikodev |
| **Level** | Mid |

---

## Ringkasan

Product Analyst bertanggung jawab menerjemahkan kebutuhan bisnis dari stakeholder (Pak Mahfud, guru, staf SMA UII) menjadi user story dan acceptance criteria yang jelas, testable, dan implementable oleh developer. Role ini juga memvalidasi hasil implementasi melalui UAT sebelum production deploy.

---

## Tanggung Jawab

### 1. Requirement Gathering & Analysis (40%)
- Interview stakeholder untuk memahami business problem
- Riset alur kerja existing (manual → digital)
- Analisis pain point dan prioritas fitur
- Dokumentasi flow bisnis (diagram alur)

### 2. User Story & Documentation (30%)
- Tulis user story format baku: Sebagai [role] / Saya ingin [fitur] / Agar [manfaat]
- Tulis acceptance criteria yang spesifik dan testable
- Maintain product backlog di Trello
- Update dokumentasi requirement di `.openkb/`

### 3. UAT & Quality Validation (20%)
- Test fitur di staging environment
- Validasi acceptance criteria satu per satu
- Report bug dengan langkah reproduksi detail
- Sign-off fitur sebelum production deploy

### 4. Stakeholder Communication (10%)
- Update progress ke Pak Mahfud secara reguler
- Manage ekspektasi client terhadap timeline
- Kumpulkan feedback untuk sprint berikutnya

---

## AI Instructions

### Konteks Role
Saya adalah **Product Analyst** di PT Koneksi Jaringan Indonesia. Saya bekerja dengan stakeholder SMA UII dan developer. Saya perlu AI untuk membantu saya menulis requirement yang jelas dan testable.

### Cara AI Harus Membantu
1. **Bantu menulis user story** — Saat saya memberi ide fitur, AI harus langsung mengubahnya ke format:
   ```
   Sebagai [role]
   Saya ingin [fitur]
   Agar [manfaat]
   ```
2. **Tanya edge case** — Setelah saya selesai menjelaskan, AI harus bertanya: "Apa scenario yang tidak biasa yang perlu ditangani?"
3. **English-only** — Write in English, avoid unnecessary technical jargon
4. **Acceptance criteria yang testable** — Bantu saya menulis AC yang spesifik, bukan vague. Contoh buruk: "halaman harus cepat" — Contoh baik: "halaman load < 3 detik di koneksi 4G"
5. **Review requirement** — Saat saya selesai menulis, AI harus review: "Apakah ada yang kurang? Apakah edge case sudah tercover?"

### Constraints
- Jangan asumsikan technical implementation — fokus pada **apa** yang pengguna butuhkan, bukan **bagaimana** implementasinya
- Jangan janjikan timeline ke stakeholder tanpa konfirmasi Sandikodev
- Jangan hapus atau ubah requirement tanpa diskusi dengan stakeholder

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (core.git) | read-only | Untuk lihat progres implementasi |
| GitHub (aksesekolah.git) | read-only | Untuk lihat dokumentasi |
| GitHub Issues | create, comment | Untuk create feature request & bug report |
| Trello (Product Roadmap) | admin | Create & manage epics |
| Trello (Sprint Board) | edit | Create cards, update status, UAT tracking |
| Environment (staging) | view, operate | Untuk testing fitur |
| Environment (production) | view only | Untuk monitoring setelah deploy |
| Google Docs / Drive | edit | Dokumen requirement & flow bisnis |

---

## Output yang Diharapkan

- User story yang implementable oleh developer (tanpa perlu tanya ulang)
- Acceptance criteria yang bisa dijadikan test case
- UAT sign-off per fitur sebelum production
- Backlog Trello yang selalu up-to-date
- Flow diagram untuk fitur kompleks

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Product Analyst | - |
| Next | UI/UX Designer | Menguasai Figma, Tailwind CSS, design system |
| Next | Product Manager | Menguasai roadmap strategy, stakeholder management |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Project Manager (Sandikodev) | Konsultasi prioritas & timeline |
| Junior Developer (Fathan, Ihsan) | Klarifikasi requirement |
| Stakeholder (Pak Mahfud) | Requirement gathering & UAT |

---

## Contoh Penggunaan di opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/ahmad-hanif/profile.md",
    "~/.openkb/ROLES/product-analyst.md"
  ]
}
```

---

*Adapted from [team-roles.md](../docs/01-getting-started/team-roles.md).*
