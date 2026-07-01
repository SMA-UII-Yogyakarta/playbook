# GitHub Organization — SMA UII Yogyakarta

> Panduan setup dan management GitHub Organization untuk tim engineering SMA UII Yogyakarta.

---

## 🏢 Organization Info

**Name:** SMA UII Yogyakarta  
**URL:** `https://github.com/SMA-UII-Yogyakarta`  
**Description:** Engineering organization for SMART Absen — Sistem Presensi Digital SMA UII Yogyakarta  
**Website:** https://smauiiyk.sch.id

---

## 👥 Team Members

| GitHub Username | Name | Role | Team |
|---|---|---|---|
| [@Sandikodev](https://github.com/Sandikodev) | Sandiko | Project Manager, Architect | `owners` |
| [@Rosyiii](https://github.com/Rosyiii) | Ahmad Hanif Hasan Rosyidi | Product Analyst | `developers` |
| [@Hans02-Neo](https://github.com/Hans02-Neo) | Fathan Mubina | Junior Developer | `developers` |
| [@Odauna](https://github.com/Odauna) | Ihsan | Junior Developer | `developers` |

**Stakeholder:**
- Pak Mahfud — IT Manager SMA UII (no GitHub account needed)
- Azis — Learning Mentor (GitHub TBD)

---

## 🔐 Permission Structure

### Organization Base Permission

```
Base Permission: Read
```

Artinya: Member default hanya bisa read repository, tidak bisa push/create.

---

### Teams

#### 1. `owners`
**Members:** Sandikodev  
**Permission:**
- ✅ Full admin access
- ✅ Create/delete repositories
- ✅ Manage organization settings
- ✅ Manage teams & members
- ✅ Manage billing & billing plans

#### 2. `maintainers`
**Members:** (Empty untuk saat ini)  
**Permission:**
- ✅ Manage repository settings
- ✅ Manage team members (add/remove)
- ✅ Merge pull requests
- ❌ Cannot delete organization
- ❌ Cannot manage billing

#### 3. `developers`
**Members:** Ahmad Hanif (Rosyiii), Fathan Mubina (Hans02-Neo), Ihsan (Odauna)  
**Permission:**
- ✅ Read & write access to assigned repos
- ✅ Create branches
- ✅ Create pull requests
- ✅ Comment on issues
- ❌ Cannot merge to main (requires approval)
- ❌ Cannot delete repositories

---

## 📦 Repositories

### Active Repositories

| Repo | Description | Visibility | Access |
|---|---|---|---|
| **aksesekolah** | Monorepo entrypoint | Private | owners, maintainers, developers |
| **core** | Backend Laravel | Private | owners, maintainers, developers |
| **playbook** | Engineering handbook | Public | owners, maintainers, developers |
| **webapp** | Frontend (Next.js) | Private | owners, maintainers, developers |
| **flutter** | Mobile app | Private | owners, maintainers, developers |

### Future Repositories
```
- docs (Public documentation site)
- design (Figma exports, assets)
- infrastructure (Terraform, Docker configs)
```

---

## 🛡️ Branch Protection Rules

### Main Branch Protection (All Repos)

**Settings → Branches → Branch protection rules → Add rule**

```
Branch name pattern: main

✅ Require a pull request before merging
   - Require approvals: 1
   - Dismiss stale pull request approvals when new commits are pushed

✅ Require status checks to pass before merging
   - CI/CD checks (if configured)

✅ Require branches to be up to date before merging

✅ Require linear history

✅ Include administrators

✅ Do not allow bypassing the above settings

✅ Restrict who can push to matching branches
   - Only owners team
```

**Result:**
- Semua perubahan ke `main` harus via PR
- Minimal 1 approval (dari owner/maintainer)
- Admin (bahkan Sandikodev) harus via PR
- Tidak ada force push ke main
- Tidak ada merge tanpa approval

---

## 🔀 Merge Strategy

**Settings → General → Pull Requests**

```
✅ Allow squash merging
   - Default commit message: PR title + description

❌ Disable allow merge commits
❌ Disable allow rebase merging
```

**Reason:** Squash merge menjaga history bersih (1 commit = 1 feature).

---

## 📋 Issue Templates

### Location: `.github/ISSUE_TEMPLATE/`

**Template 1: Feature Request** (`feature-request.md`)
```markdown
---
name: 🚀 Feature Request
about: Suggest an idea for this project
title: '[FEATURE] '
labels: enhancement
assignees: ''
---

## Problem Statement
[Jelaskan masalah yang ingin diselesaikan]

## Proposed Solution
[Jelaskan solusi yang diusulkan]

## User Story
**Sebagai** [role]
**Saya ingin** [fitur]
**Agar** [manfaat]

## Acceptance Criteria
- [ ] Kriteria 1
- [ ] Kriteria 2

## Additional Context
[Link ke Trello, design, atau referensi lain]
```

**Template 2: Bug Report** (`bug-report.md`)
```markdown
---
name: 🐛 Bug Report
about: Create a report to help us improve
title: '[BUG] '
labels: bug
assignees: ''
---

## Bug Description
[Jelaskan bug secara singkat]

## Severity
- [ ] 🔥 Critical (production down, data loss)
- [ ] ⚠️ Major (feature broken, workaround available)
- [ ] 📌 Minor (cosmetic, UX issue)

## Steps to Reproduce
1. Go to '...'
2. Click on '....'
3. See error

## Expected Behavior
[APA yang seharusnya terjadi]

## Actual Behavior
[Apa yang sebenarnya terjadi]

## Environment
- OS: Windows 11
- Browser: Chrome 114.0
- Version: v1.0.0

## Screenshots
[Attach screenshot jika ada]

## Error Logs
```
Paste error log di sini
```
```

---

## 📝 Pull Request Template

**Location:** `.github/pull_request_template.md`

```markdown
## Related Issue
Fixes #[issue-number]

## Description
[Jelaskan apa yang diubah dan kenapa]

## Changes
### Backend
- `File.php`: Change description

### Frontend
- `File.vue`: Change description

## Type of Change
- [ ] 🚀 New feature
- [ ] 🐛 Bug fix
- [ ] ⚠️ Breaking change
- [ ] 📄 Documentation update

## Testing
### Unit Tests
```bash
php artisan test
```
Result: [Paste result]

### Manual Testing
- [ ] Tested locally
- [ ] Screenshots attached (if UI change)

## Checklist
- [ ] Conventional commit
- [ ] No console.log()
- [ ] Self-review completed
- [ ] Documentation updated

## Notes for Reviewer
[@Sandikodev: Focus review pada file X line Y]
```

---

## 🏷️ Labels

### Default Labels

| Label | Color | Description |
|---|---|---|
| `enhancement` | Green | New feature request |
| `bug` | Red | Something isn't working |
| `documentation` | Purple | Documentation improvements |
| `help wanted` | Yellow | Extra attention is needed |

### Custom Labels

| Label | Color | Description |
|---|---|---|
| `🔥 critical` | Red | Critical priority |
| `⚠️ high` | Orange | High priority |
| `📌 medium` | Yellow | Medium priority |
| `🐌 low` | Green | Low priority |
| `🚧 wip` | Blue | Work in progress |
| `🚫 blocked` | Grey | Blocked by other task |
| `frontend` | Blue | Frontend task |
| `backend` | Purple | Backend task |
| `testing` | Pink | Testing related |
| `sprint-1` | Light Blue | Sprint 1 task |
| `sprint-2` | Light Green | Sprint 2 task |

---

## 📊 GitHub Projects

### Project Setup

**URL:** `https://github.com/orgs/SMA-UII-Yogyakarta/projects/1`

**Board Configuration:**

```
Layout: Board (Kanban)

Items: Issues + Pull Requests

Groups: Status (column based)
```

**Columns:**
```
📋 Backlog
   - All new issues

✅ Ready
   - DoR met
   - Ready for development

🚧 In Progress
   - Assigned to developer
   - Work in progress

👀 Code Review
   - PR created
   - Waiting for review

🧪 Testing
   - PR merged
   - UAT in progress

✅ Done
   - All checks passed
   - Closed issues
```

**Automation:**
```
When issue is opened → Add to Backlog
When issue is assigned → Move to In Progress
When PR is created → Move to Code Review
When PR is merged → Move to Testing
When issue is closed → Move to Done
```

---

## 🎯 Milestone Management

### Creating Milestones

**Issues → Milestones → New milestone**

**Format:**
```
Title: Sprint 1
Description: Authentication & SSO
Due date: [End date of sprint]
```

**Sprint Milestones:**
```
Sprint 1 — Authentication & SSO (Week 1-2)
Sprint 2 — Presensi Module (Week 3-4)
Sprint 3 — Laporan & Admin (Week 5-6)
Sprint 4 — Production Ready (Week 7-8)
```

---

## 🔗 Integrations

### Trello Integration

**Power-Up:** GitHub for Trello

**Setup:**
1. Buka Trello Board
2. Power-Ups → Add "GitHub"
3. Connect GitHub account
4. Link repository

**Benefit:**
- Attach PR ke Trello card
- Lihat status PR langsung di Trello
- Auto-update card saat PR status berubah

---

### CI/CD (GitHub Actions)

**Location:** `.github/workflows/`

**Workflow 1: Laravel Test** (`core/.github/workflows/test.yml`)
```yaml
name: Laravel Tests

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3

    - name: Setup PHP
      uses: shivammathur/setup-php@v2
      with:
        php-version: '8.4'

    - name: Install dependencies
      run: composer install --prefer-dist --no-progress

    - name: Run tests
      run: php artisan test
```

---

## 📈 Analytics & Insights

### Repository Insights

**Insights tab di setiap repository:**

```
- Contributors
- Commits
- Code frequency
- Dependency graph
- Network
- Members
```

### Organization Insights

**Organization → Settings → Rules → Insights**

```
- Active members
- Repository activity
- Contribution frequency
```

---

## 🛡️ Security Best Practices

### 1. Two-Factor Authentication (2FA)

**Requirement:** Semua member wajib enable 2FA

**How to enable:**
```
GitHub Settings → Password and authentication → Enable 2FA
```

---

### 2. Secret Scanning

**Settings → Code security and analysis**

```
✅ Enable secret scanning
✅ Enable push protection
```

---

### 3. Dependabot

**Settings → Code security and analysis**

```
✅ Enable Dependabot alerts
✅ Enable Dependabot security updates
```

**Config:** `.github/dependabot.yml`
```yaml
version: 2
updates:
  - package-ecosystem: "composer"
    directory: "/"
    schedule:
      interval: "weekly"

  - package-ecosystem: "npm" # Bun-compatible, tracked via bun.lock
    directory: "/"
    schedule:
      interval: "weekly"

  - package-ecosystem: "github-actions"
    directory: "/"
    schedule:
      interval: "weekly"
```

---

## 👥 Onboarding New Members

### Step-by-Step

**1. Invite to Organization**

```
Organization → People → Invite member
Enter GitHub username
Select team: developers (default)
Send invitation
```

**2. Add to Team**

```
Teams → developers → Add member
Select user
Set role: Member
```

**3. Grant Repository Access**

```
Repositories → Select repo → Manage access
Add team: developers
Set permission: Read & Write
```

**4. Onboarding Checklist**

- [ ] Accept organization invitation
- [ ] Enable 2FA
- [ ] Join WhatsApp Group
- [ ] Read playbook (this repo)
- [ ] Setup local environment
- [ ] Clone repositories
- [ ] First PR (dummy/test)

---

## 📞 Support & Contact

**Organization Admin:** Sandikodev  
**Email:** sandiko@koneksi.id  
**WhatsApp:** [Group Link]

**For Issues:**
- Technical issues → Create Issue di repository terkait
- Organization issues → Contact Sandikodev directly

---

## 📚 Resources

- [GitHub Organization Documentation](https://docs.github.com/en/organizations)
- [GitHub Teams](https://docs.github.com/en/organizations/organizing-members-into-teams)
- [GitHub Branch Protection](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches)
- [SMA UII Playbook](https://github.com/SMA-UII-Yogyakarta/playbook)

---

**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev