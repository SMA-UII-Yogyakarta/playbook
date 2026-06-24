# Role Template — [Nama Role]

> Template untuk mendefinisikan role baru di ekosistem PT Koneksi Jaringan Indonesia.
> Copy file ini, rename sesuai role, dan isi setiap seksi.

---

## Metadata

| Atribut | Value |
|---|---|
| **Role ID** | `nama-role` (slug, lowercase, pakai hypen) |
| **Dibuat** | YYYY-MM-DD |
| **Maintainer** | Nama PIC |
| **Level** | Junior / Mid / Senior / Lead / Stakeholder |

---

## Ringkasan

[Jelaskan role ini dalam 2-3 kalimat. Siapa dia, apa yang dilakukan, di project apa.]

---

## Tanggung Jawab

### 1. [Area 1 — Persentase Waktu]
- [Task detail]
- [Task detail]

### 2. [Area 2 — Persentase Waktu]
- [Task detail]
- [Task detail]

---

## AI Instructions

> Bagian ini dibaca oleh AI Agent setiap kali membantu role ini.
> Tulis dalam bahasa Indonesia, gunakan kalimat perintah langsung.

### Konteks Role
- [Role ini bertanggung jawab atas apa]
- [Apa yang AI harus prioritaskan saat membantu]

### Cara AI Harus Membantu
- [Instruksi spesifik tentang format output]
- [Bahasa yang digunakan]
- [Hal yang harus dihindari]

### Constraints
- [Apa yang tidak boleh dilakukan AI]
- [Batasan akses informasi]

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (source code) | read / write / admin | Project spesifik |
| GitHub Issues | create / comment / triage | - |
| Trello | view / edit / admin | Board spesifik |
| Environment (staging) | view / operate | - |
| Environment (production) | view / operate | - |

---

## Output yang Diharapkan

- [Output 1]
- [Output 2]
- [Output 3]

---

## Growth Path

> Untuk role yang bersifat growth (junior → senior), tuliskan kemungkinan transisi.

| Level | Role Target | Prasyarat |
|---|---|---|
| Current | [Role saat ini] | - |
| Next | [Role berikutnya] | [Skill / waktu] |

---

## Related Roles

- [Role lain yang sering berinteraksi]
- [Role lain dengan tanggung jawab tumpang tindih]

---

## Contoh Penggunaan di opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/{{username}}/profile.md",
    "~/.openkb/ROLES/nama-role.md"
  ]
}
```

---

*Template ini adalah bagian dari [playbook Koneksi](../../README.md).*
