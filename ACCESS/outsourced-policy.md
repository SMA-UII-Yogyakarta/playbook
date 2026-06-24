# Outsourced Worker Policy

> Kebijakan akses dan keamanan untuk pekerja outsourcing/mitra (non-employee PT Koneksi).
> Contoh: Ahmad Hanif (IT Support SMA UII) — bekerja di project SMART Absen.

---

## 🔴 Prinsip Dasar

1. **Privilege minimum** — Hanya akses yang diperlukan untuk完成任务
2. **Isolasi project** — Hanya bisa akses repo project yang ditugaskan, bukan semua project Koneksi
3. **No production access** — Tidak boleh akses production environment, hanya staging
4. **Time-bound** — Akses aktif selama project berjalan
5. **Monitorable** — Semua aktivitas tercatat di audit log GitHub/Trello

---

## 🔐 Level Akses Outsourced

### Level 1: Product Analyst (Hanif — saat ini)
| Resource | Access | Reason |
|---|---|---|
| core.git | read-only | Untuk lihat progres implementasi |
| aksesekolah.git | read-only | Dokumentasi & monorepo |
| playbook.git | write | Bisa update dokumentasi requirement |
| GitHub Issues (core) | create, comment | Feature request & bug report |
| Trello Product Roadmap | admin | Manage epics & requirement |
| Trello Sprint Board | edit | Update card, UAT tracking |
| Staging | view, operate | Testing fitur |
| Production | ❌ | Tidak perlu |
| Project Koneksi lain | ❌ | Isolasi project |

### Level 2: UI/UX Designer (Hanif — future)
| Resource | Access | Reason |
|---|---|---|
| core.git | read-only | Paham struktur halaman |
| webapp.git | write (branch) | Implementasi UI component |
| Figma | edit | Design system, wireframe |
| Staging | view, operate | Testing UI |

### Level 3: Contributor Spesifik (Future)
| Resource | Access | Reason |
|---|---|---|
| Repo spesifik | write (branch) | Kontribusi terbatas |
| Issue spesifik | create, comment | Diskusi task |
| Lainnya | ❌ | Sesuai scope kontrak |

---

## 📋 Onboarding Outsourced Worker

### Checklist Onboarding

```
□ 1. Tentukan scope project & durasi kontrak
□ 2. GitHub:
   □ Invite ke organization → team "developers"
   □ Set repo access (read → write sesuai level)
   □ Setup 2FA
□ 3. Trello:
   □ Invite ke board yang relevan
   □ Set permission (view/edit/admin)
□ 4. Environment:
   □ Clone repo yang diperlukan
   □ Setup local development
□ 5. Playbook:
   □ Read: docs/01-getting-started/*
   □ Read: docs/02-workflow/*
   □ Read: ROLES/<role>.md
□ 6. AI Agent:
   □ Setup .openkb/PERSONAL/<user>/
   □ Setup opencode.json user-level
   □ Role file di ~/.openkb/ROLES/
```

### Checklist Offboarding

```
□ 1. GitHub: Remove from organization
□ 2. Trello: Remove from board
□ 3. Revoke API keys / tokens
□ 4. Archive personal notes di .openkb/
□ 5. Handover dokumentasi
```

---

## 🚫 Restricted Actions

Outsourced workers **TIDAK BOLEH**:

| Action | Risiko |
|---|---|
| Push langsung ke main/develop | Bypass code review |
| Merge PR sendiri | Bypass review |
| Akses production environment | Data leak / kerusakan |
| Invite orang lain ke GitHub org | Security breach |
| Share credentials | Security breach |
| Commit di repo non-project | Isolasi project violated |
| Delete branches/code | Data loss |
| Modify GitHub Actions / CI | Security risk |

---

## 📞 Kontak & Eskalasi

| Issue | Kontak |
|---|---|
| Akses bermasalah | Sandikodev (WhatsApp) |
| Perlu akses tambahan | Sandikodev (approval) |
| Violation / security issue | Sandikodev (immediate) |
| Technical blocker | WhatsApp Group |

---

## ⚖️ Policy Enforcement

- Violation → peringatan lisan (1x)
- Violation berulang → akses dicabut sementara
- Severe violation (data leak, credential sharing) → akses dicabut permanen + report ke stakeholder

---

*Dokumen ini adalah bagian dari [playbook Koneksi](../../README.md).*
