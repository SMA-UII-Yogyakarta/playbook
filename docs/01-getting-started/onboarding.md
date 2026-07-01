# Onboarding Checklist — First Day

> Checklist for new team members joining the SMA UII Yogyakarta project.

---

## ✅ Pre-Day 1 (HR/Admin)

- [ ] Invited to GitHub Organization `SMA-UII-Yogyakarta`
- [ ] Invited to Trello Board `SMART ABSEN SMAUII`
- [ ] Added to WhatsApp Group
- [ ] Given access to Google Drive (if any)
- [ ] Given laptop & equipment (if onsite)

---

## 📅 Day 1: Welcome & Setup

### Morning (09:00 - 12:00)

#### 1. Welcome Session (30 minutes)
**PIC:** Sandikodev

- Team introduction
- SMART Absen project overview
- Vision & mission of PT Koneksi Jaringan Indonesia
- 8-week expectations (MVP + Production)

#### 2. GitHub & Git Setup (30 minutes)
**PIC:** Sandikodev

- [ ] Accept GitHub Organization invitation
- [ ] Setup 2FA on GitHub
- [ ] Generate SSH Key
- [ ] Add SSH Key to GitHub
- [ ] Test: `git clone git@github.com:SMA-UII-Yogyakarta/playbook.git`

```bash
# Generate SSH Key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Add to GitHub
# Settings → SSH and GPG keys → New SSH Key
```

#### 3. Environment Setup (2 hours)
**PIC:** Each developer (assisted by Azis)

Follow the guide: [`environment-setup.md`](environment-setup.md)

- [ ] Install Laragon 6.0
- [ ] Setup PostgreSQL 16 (Laragon) or register for NeonDB
- [ ] Install Bun (frontend package manager)
- [ ] Install Composer
- [ ] Install VS Code + extensions
- [ ] Clone `core` repository to `C:\laragon\www\smauii-core`
- [ ] Setup `.env` (PostgreSQL connection)
- [ ] Run `composer install`
- [ ] Run `bun install`
- [ ] Test: `php artisan migrate`
- [ ] Test: `bun run dev`

#### 4. Git & GitHub Workflow (1 hour)
**PIC:** Sandikodev

Read: [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)

- [ ] Understand branching strategy
- [ ] Understand conventional commits
- [ ] Understand Pull Request workflow
- [ ] Understand code review process

---

### Afternoon (13:00 - 17:00)

#### 5. Trello & Project Management (1 hour)
**PIC:** Ahmad Hanif

Read: [`trello-workflow.md`](../02-workflow/trello-workflow.md)

- [ ] Accept Trello invitation
- [ ] Understand board structure
- [ ] Understand how to read cards
- [ ] Understand Definition of Ready (DoR)
- [ ] Understand Definition of Done (DoD)

#### 6. Role-Specific Training (2 hours)

**For Ahmad Hanif (Product Analyst):**
- Read: [`user-story.md`](../04-templates/user-story.md)
- Practice: Create 3 user stories for Sprint 1
- Setup: Acceptance criteria template

**For Fathan (Junior Frontend Developer):**
- Review: TypeScript basics (types, interface)
- Review: React hooks (useState, useEffect)
- Setup: VS Code extensions (Tailwind CSS, ESLint, Prettier)
- Practice: Create a simple React + TypeScript component (Counter / Todo List)
- Ensure Vite + Tailwind is running: `bun run dev`

**For Ihsan (Junior Backend Developer):**
- Review: Eloquent ORM + Service Layer concept
- Review: PostgreSQL basics (connect, migration, query)
- Setup: pgAdmin / DBeaver for PostgreSQL
- Practice: Create migration + model + service + controller (CRUD for one table)

**For Azis (Learning Mentor):**
- Review: Entire playbook (README, ADRs, team-roles, learning-resources)
- Understand Service Layer pattern + InertiaJS + React architecture
- Understand mentoring scope — discussion, debugging, not coding features

#### 7. Q&A Session (30 minutes)
**PIC:** Sandikodev

- Q&A on everything unclear
- Discuss role expectations
- Set goals for the first 2 weeks

---

## 📅 Day 2-3: Shadowing & First Task

### Day 2

#### Morning
- [ ] Shadowing — watch Azis or Sandikodev coding
- [ ] Read existing documentation in playbook + aksesekolah/docs
- [ ] Understand the database ERD (PostgreSQL)

#### Afternoon
- [ ] Take first task (good first issue) from GitHub Project
- [ ] Create first branch
- [ ] First commit
- [ ] Create first Pull Request (dummy)

### Day 3

#### Morning
- [ ] Azis initial PR review
- [ ] Fix based on Azis's review
- [ ] Sandikodev final review
- [ ] Merge first PR

#### Afternoon
- [ ] Start actual Sprint 1 task
- [ ] First standup meeting (15 minutes)

---

## 📅 Week 1 Goals

- [ ] Development environment working (Bun, PostgreSQL, Vite)
- [ ] At least 1 PR merged to main
- [ ] Understand Git → PR → Review → Merge workflow
- [ ] Understand how to read user stories
- [ ] Understand Definition of Ready & Done

---

## 📅 Week 2 Goals

- [ ] At least 2 tasks completed in Sprint 1
- [ ] Code review quality improving
- [ ] Start working independently (ask Azis first before escalating to Sandikodev)
- [ ] Active in standup meetings

---

## 📚 Required Reading

### All Team
- [ ] [`README.md`](../README.md) — Playbook overview
- [ ] [`team-roles.md`](team-roles.md) — Role details
- [ ] [`communication.md`](../02-workflow/communication.md) — Team communication

### Developers
- [ ] [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)
- [ ] [`code-review.md`](../03-sop/code-review.md)
- [ ] [`testing.md`](../03-sop/testing.md)

### Product Analyst
- [ ] [`user-story.md`](../04-templates/user-story.md)
- [ ] [`trello-workflow.md`](../02-workflow/trello-workflow.md)

---

## ✅ Onboarding Completion Checklist

Filled by Sandikodev at the end of Week 1

- [ ] Environment setup ✅ (Bun, PostgreSQL, Vite, Laragon)
- [ ] Git workflow understood ✅
- [ ] First PR merged ✅
- [ ] Role understanding clear ✅
- [ ] Communication smooth ✅
- [ ] Know who Azis is and how to ask for help ✅
- [ ] Ready for Sprint 1 ✅

**Notes:**
```
[Fill in performance notes & improvement areas]
```

---

## 🆘 If There's a Problem

| Problem | Solution | PIC |
|---|---|---|
| Git error | Re-clone, check SSH key | Sandikodev |
| Database won't connect | Check `.env`, PostgreSQL service | Azis / Ihsan |
| Bun / Vite error | Check `bun install`, restart terminal | Azis / Fathan |
| Port conflict | Check Laragon virtual host | Sandikodev |
| Requirement unclear | Ask Ahmad Hanif | Ahmad Hanif |
| Task blocker > 30 minutes | Ask Azis first | Azis |
| Task blocker > 2 hours | Escalate to Sandikodev | Sandikodev |

---

**Next Step:** [`environment-setup.md`](environment-setup.md)
