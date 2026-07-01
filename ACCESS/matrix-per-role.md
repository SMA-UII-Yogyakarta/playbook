# Access Matrix — Per Role

> Access matrix for each role in the PT Koneksi Jaringan Indonesia ecosystem.
> Used for onboarding, audit, and security.

---

## Access Matrix

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

| Level | Meaning |
|---|---|
| **admin** | Full control — manage, invite, delete |
| **write (branch)** | Push to feature branch, create PR, review PR |
| **write** | Edit, create, delete |
| **edit** | Edit content but cannot manage |
| **create/comment** | Create new issue + comment |
| **view/comment** | View + comment (cannot create) |
| **view** | Read-only |
| **operate** | Can deploy, restart, view logs |
| **full** | Root access |
| **❌** | No access |

---

## Privilege Escalation Path

For temporary limited access, can be escalated with approval:

| Current | Request | Approval Needed |
|---|---|---|
| Junior → Mid | write → write + review | Tech Lead |
| Product Analyst → UI/UX | read → write (webapp) | Project Manager |
| View → Operate (staging) | view → operate | Tech Lead |

---

## Policy

1. **Minimum privilege** — Each role only gets the minimum access needed
2. **Periodic review** — Access is reviewed every month by Tech Lead
3. **Revoke** — Access is revoked when role changes or contract ends
4. **Audit trail** — All access changes are recorded in decision-log

---

*This document is part of the [Koneksi playbook](../../README.md).*
