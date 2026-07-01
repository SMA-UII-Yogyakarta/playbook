# Outsourced Worker Policy

> Access and security policy for outsourced workers/partners (non-employee of PT Koneksi).
> Example: Ahmad Hanif (IT Support SMA UII) — working on the SMART Absen project.

---

## 🔴 Core Principles

1. **Minimum privilege** — Only access needed to complete tasks
2. **Project isolation** — Can only access assigned project repos, not all Koneksi projects
3. **No production access** — Must not access production environment, only staging
4. **Time-bound** — Access active during project duration
5. **Monitorable** — All activities are logged in GitHub/Trello audit logs

---

## 🔐 Outsourced Access Levels

### Level 1: Product Analyst (Hanif — current)
| Resource | Access | Reason |
|---|---|---|
| core.git | read-only | To see implementation progress |
| aksesekolah.git | read-only | Documentation & monorepo |
| playbook.git | write | Can update requirement documentation |
| GitHub Issues (core) | create, comment | Feature request & bug report |
| Trello Product Roadmap | admin | Manage epics & requirements |
| Trello Sprint Board | edit | Update cards, UAT tracking |
| Staging | view, operate | Feature testing |
| Production | ❌ | Not needed |
| Other Koneksi projects | ❌ | Project isolation |

### Level 2: UI/UX Designer (Hanif — future)
| Resource | Access | Reason |
|---|---|---|
| core.git | read-only | Understand page structure |
| webapp.git | write (branch) | UI component implementation |
| Figma | edit | Design system, wireframe |
| Staging | view, operate | UI testing |

### Level 3: Specific Contributor (Future)
| Resource | Access | Reason |
|---|---|---|
| Specific repo | write (branch) | Limited contribution |
| Specific issue | create, comment | Task discussion |
| Others | ❌ | Per contract scope |

---

## 📋 Onboarding Outsourced Worker

### Onboarding Checklist

```
□ 1. Define project scope & contract duration
□ 2. GitHub:
   □ Invite to organization → team "developers"
   □ Set repo access (read → write per level)
   □ Setup 2FA
□ 3. Trello:
   □ Invite to relevant board
   □ Set permission (view/edit/admin)
□ 4. Environment:
   □ Clone required repos
   □ Setup local development
□ 5. Playbook:
   □ Read: docs/01-getting-started/*
   □ Read: docs/02-workflow/*
   □ Read: ROLES/<role>.md
□ 6. AI Agent:
   □ Setup .openkb/PERSONAL/<user>/
   □ Setup opencode.json user-level
   □ Role file at ~/.openkb/ROLES/
```

### Offboarding Checklist

```
□ 1. GitHub: Remove from organization
□ 2. Trello: Remove from board
□ 3. Revoke API keys / tokens
□ 4. Archive personal notes in .openkb/
□ 5. Handover documentation
```

---

## 🚫 Restricted Actions

Outsourced workers **MUST NOT**:

| Action | Risk |
|---|---|
| Push directly to main/develop | Bypass code review |
| Merge own PR | Bypass review |
| Access production environment | Data leak / damage |
| Invite others to GitHub org | Security breach |
| Share credentials | Security breach |
| Commit in non-project repo | Project isolation violated |
| Delete branches/code | Data loss |
| Modify GitHub Actions / CI | Security risk |

---

## 📞 Contact & Escalation

| Issue | Contact |
|---|---|
| Access issues | Sandikodev (WhatsApp) |
| Need additional access | Sandikodev (approval) |
| Violation / security issue | Sandikodev (immediate) |
| Technical blocker | WhatsApp Group |

---

## ⚖️ Policy Enforcement

- Violation → verbal warning (1x)
- Repeated violation → temporary access revocation
- Severe violation (data leak, credential sharing) → permanent access revocation + report to stakeholder

---

*This document is part of the [Koneksi playbook](../../README.md).*
