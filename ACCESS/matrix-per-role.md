# Access Matrix — Per Role

> Matriks akses untuk setiap role di ekosistem PT Koneksi Jaringan Indonesia.
> Digunakan untuk onboarding, audit, dan keamanan.

---

## Matriks Akses

| Resource | PM | Senior Dev | Junior Backend | Junior Frontend | Product Analyst | Stakeholder |
|---|---|---|---|---|---|---|
| **core.git (code)** | admin | admin | write (branch) | write (branch) | read | ❌ |
| **aksesekolah.git (monorepo)** | admin | admin | read | read | read | ❌ |
| **webapp.git (planned)** | admin | admin | ❌ | write (branch) | read | ❌ |
| **playbook.git (SOP)** | admin | admin | write | write | write | read |
| **kaede-powerup.git** | admin | admin | read | read | read | ❌ |
| **GitHub Issues** | triage | triage | create/comment | create/comment | create/comment | view/comment |
| **GitHub Projects** | admin | admin | view | view | view | view |
| **Trello Product Roadmap** | admin | admin | view | view | admin | view/comment |
| **Trello Sprint Board** | admin | admin | view/comment | view/comment | edit | view/comment |
| **Staging Environment** | full | full | operate | operate | operate | view |
| **Production Environment** | full | full | ❌ | ❌ | view | ❌ |
| **Cloudflare DNS** | admin | admin | ❌ | ❌ | ❌ | ❌ |
| **Wasabi S3 Storage** | admin | admin | ❌ | ❌ | ❌ | ❌ |
| **WhatsApp Group** | admin | admin | member | member | member | member |
| **Google Drive / Docs** | edit | edit | view | view | edit | view/comment |

---

## Level Definitions

| Level | Arti |
|---|---|
| **admin** | Full control — manage, invite, delete |
| **write (branch)** | Push ke branch fitur, buat PR, review PR |
| **write** | Edit, create, delete |
| **edit** | Edit content tapi tidak bisa manage |
| **create/comment** | Buat issue baru + komentar |
| **view/comment** | Lihat + komentar (tidak create) |
| **view** | Read-only |
| **operate** | Bisa deploy, restart, view logs |
| **full** | Root access |
| **❌** | No access |

---

## Privilege Escalation Path

Untuk sementara akses terbatas, bisa dinaikkan dengan approval:

| Current | Request | Approval Needed |
|---|---|---|
| Junior → Mid | write → write + review | Tech Lead |
| Product Analyst → UI/UX | read → write (webapp) | Project Manager |
| View → Operate (staging) | view → operate | Tech Lead |

---

## Policy

1. **Privilege minimum** — Setiap role hanya dapat akses minimum yang dibutuhkan
2. **Periodic review** — Akses direview setiap bulan oleh Tech Lead
3. **Revoke** — Akses dicabut saat role berubah atau kontrak berakhir
4. **Audit trail** — Semua perubahan akses tercatat di decision-log

---

*Dokumen ini adalah bagian dari [playbook Koneksi](../../README.md).*
