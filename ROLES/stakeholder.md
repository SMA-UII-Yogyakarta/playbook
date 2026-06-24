# Stakeholder

> Role untuk Pak Mahfud (IT Manager SMA UII) — pengambil keputusan dan validator bisnis.
> Fokus: vision, priority decision, acceptance sign-off.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `stakeholder` |
| **Dibuat** | 2026-06-25 |
| **Maintainer** | Sandikodev |
| **Level** | Stakeholder |

---

## Ringkasan

Stakeholder adalah pemilik kepentingan bisnis dari SMA UII Yogyakarta. Role ini memberikan visi, memvalidasi requirement, mengambil keputusan prioritas, dan memberikan sign-off akhir untuk production deploy. Tidak terlibat dalam implementasi teknis.

---

## Tanggung Jawab

### 1. Vision & Direction (30%)
- Menentukan visi produk SMART Absen
- Prioritas fitur berdasarkan kebutuhan sekolah
- Decision maker untuk trade-off bisnis
- Validasi roadmap

### 2. Requirement Validation (25%)
- Review & approve user story
- Konfirmasi business rules
- Validasi flow bisnis sesuai SOP sekolah
- Tanda tangan persetujuan requirement

### 3. UAT & Acceptance (25%)
- Test fitur di staging (dibantu Product Analyst)
- Validasi kesesuaian dengan kebutuhan
- Sign-off production deploy
- Report feedback & issue

### 4. Resource & Policy (20%)
- Menyediakan data master (siswa, guru, kelas)
- Policy & aturan sekolah terkait presensi
- Approval budget & timeline
- Fasilitasi akses ke stakeholder sekolah lain

---

## AI Instructions

### Konteks Role
Saya adalah **Stakeholder** dari SMA UII Yogyakarta. Saya tidak coding dan tidak perlu paham teknis. Saya perlu AI untuk membantu saya memahami progress project dan membuat keputusan bisnis yang tepat.

### Cara AI Harus Membantu
1. **Non-technical explanation** — Jelaskan progress dan issue dalam bahasa Indonesia yang sederhana, tanpa jargon teknis.
2. **Decision support** — Saat ada trade-off, AI harus menyajikan opsi dengan konsekuensi masing-masing secara jelas.
3. **Visual progress** — Bantu interpretasi data progress dalam format yang mudah dipahami (bullet points, perbandingan).
4. **Risk communication** — Jika ada risiko, jelaskan dampak bisnisnya, bukan teknisnya.

### Constraints
- Jangan gunakan jargon teknis (API, endpoint, migration, dll) — gunakan istilah bisnis
- Jangan asumsikan saya tahu konteks teknis — selalu jelaskan dari sisi bisnis
- Format yang mudah dicerna — bullet points, tabel, perbandingan

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| Trello (Product Roadmap) | view, comment | Untuk lihat roadmap & feedback |
| Trello (Sprint Board) | view, comment | Untuk lihat progress sprint |
| WhatsApp Group | member | Komunikasi harian |
| Google Drive | view, comment | Dokumen requirement & report |
| GitHub Issues | view, comment | Untuk lihat & komentari issue |
| Code repositories | ❌ no access | Tidak perlu akses kode |

---

## Output yang Diharapkan

- Keputusan prioritas fitur yang jelas
- Sign-off requirement tepat waktu
- UAT feedback dalam 2x24 jam
- Data master (siswa, guru, kelas) tersedia tepat waktu

---

## Growth Path

| Level | Role | Prasyarat |
|---|---|---|
| Current | Stakeholder (Project) | - |
| Next | Product Owner (Org) | Memahami multiple product |
| Next | Executive Sponsor | Organization-level decision |

---

## Related Roles

| Role | Interaksi |
|---|---|
| Product Analyst (Hanif) | Requirement gathering, UAT |
| Project Manager (Sandikodev) | Progress report, escalation |
| Developer (Fathan, Ihsan) | Demo session, UAT support |

---

## Contoh Penggunaan di opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/mahfud/profile.md",
    "~/.openkb/ROLES/stakeholder.md"
  ]
}
```

---

*Adapted from [team-roles.md](../docs/01-getting-started/team-roles.md).*
