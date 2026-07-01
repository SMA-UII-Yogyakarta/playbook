# AI Agent Workflow — TACO Protocol

> Standard workflow for using AI Agents (Opencode, Claude Code, Claw Code, Cursor)
> for all team members of PT Koneksi Jaringan Indonesia.

---

## 🎯 TACO Protocol

TACO = **Trello → AI → Commit → Output**

Four steps that integrate planning (Trello) with execution (AI Agent):

```
┌──────────────────────────────────────────────────────────────────┐
│  T — Trello: Task taken from board, status → "In Progress"      │
│  A — AI: Open AI Agent with role & project context               │
│  C — Commit: Code complete → commit with conventional commit     │
│  O — Output: PR created, Trello updated, knowledge recorded      │
└──────────────────────────────────────────────────────────────────┘
```

---

## 📋 Workflow Detail

### Step 1: Trello — Pick Up Task

**Who:** Fathan / Ihsan (Developer)

**Action:**
1. Open Trello Sprint Board
2. Pick task from "Ready" column
3. Assign card to self
4. Move to "In Progress"
5. Note Issue ID: `ISSUE-12` (link from card description)

**Output:** Task assigned, Issue ID recorded.

---

### Step 2: AI — Agent Preparation

**Who:** Developer

**Action:**
```bash
# Example with Opencode:
opencode --task "Work on ISSUE-12: Attendance Validation"

# Example with Claude Code:
claude -p "Work on Issue #12 about attendance validation"

# Example with Cursor IDE:
# Open project → Ctrl+Shift+P → "AI: Start Task" → paste Issue URL
```

**What AI reads automatically:**
| Source | Content |
|---|---|
| `.opencode/SHARED/project-context.md` | Stack, architecture, team |
| `.opencode/SHARED/agent-rules.md` | Ground rules, coding standard |
| `~/.openkb/PERSONAL/<user>/profile.md` | Who I am, skills, preferences |
| `~/.openkb/ROLES/<role>.md` | Responsibilities & AI instructions per role |
| `playbook/ROLES/<role>.md` | Role definition & expectations |
| Issue #12 on GitHub | Requirement & acceptance criteria |

**Output:** AI Agent ready with full context.

---

### Step 3: Commit — Code Execution

**Who:** Developer + AI Agent

**Process:**
```
1. AI studies Issue & acceptance criteria
2. AI reads relevant existing code
3. AI writes new code / modifications
4. Developer reviews AI output
5. AI runs test: composer test / bun run test
6. Developer self-review
7. Commit: feat(attendance): implement attendance validation
```

**Branch naming:**
```
feature/ISSUE-12-attendance-validation
```

**Conventional Commit:**
```
feat(attendance): implement triple-layer validation
fix(attendance): fix geolocation radius bug
chore(deps): update laravel/framework
```

**Output:** Code committed and ready for PR.

---

### Step 4: Output — PR & Update

**Who:** Developer

**Action:**
```bash
git push origin feature/ISSUE-12-attendance-validation
gh pr create --title "feat(attendance): attendance validation" --body "Fixes #12"
```

**PR body:**
```markdown
## Related Issue
Fixes #12

## Changes
- [BE] Triple-layer validation logic
- [DB] Migration: add attendance table
- [Test] Unit test attendance validation

## Self-Checklist
- [ ] Acceptance criteria met
- [ ] Unit test coverage > 70%
- [ ] Security: no SQL injection, no XSS
- [ ] Performance: no N+1 query
- [ ] Coding standard: PSR-12

## Trello Card
SMART-21 → move to "Review"

## Notes for Reviewer
- Pay attention to geolocation radius validation
- Edge case: student at radius boundary
```

**After PR:**
1. Update Trello → move card to "Review"
2. Log in `.openkb/PERSONAL/<user>/sessions/YYYY-MM-DD.md`
3. Notify Sandikodev via WhatsApp

**Output:** PR ready for review.

---

## 🧠 Workflow Per Role

### Developer (Fathan / Ihsan)

```
Daily:
1. Check Trello "In Progress" → continue task
2. Open AI Agent → "Continue previous task"
3. Code with AI assistance
4. Self-review
5. If stuck > 30 minutes → ask on WhatsApp

Task Complete:
1. PR → "Ready for Review"
2. Trello → "Review"
3. Pick new task from "Ready"
```

### Product Analyst (Ahmad Hanif)

```
Daily:
1. Check feedback from stakeholders
2. Update requirement in Trello if needed
3. Test features that enter "Testing" column

UAT Complete:
1. Approve → move to "Done"
2. Reject → move to "Ready" + comment
```

### Tech Lead (Sandikodev)

```
Daily:
1. Review incoming PRs (target < 24 hours)
2. Check Trello "Review" column
3. Unblock stuck developers

Sprint:
1. Planning & retrospective
2. Update ADR if there are new decisions
```

### Stakeholder (Pak Mahfud)

```
Per Sprint:
1. Review demo at end of sprint
2. Approve / feedback via Trello
3. Priority decision if scope changes
```

---

## 🛡️ AI Agent Security

### What Is Allowed
- AI reads files `.md`, `.php`, `.js`, `.blade.php`, `.json`
- AI writes code on feature branch
- AI runs `composer test`, `bun run build`
- AI accesses Trello via MCP (read card, update status)

### What Is Not Allowed
- ❌ AI commits directly to `main` or `develop`
- ❌ AI accesses `.env`, credentials, API keys
- ❌ AI runs `php artisan migrate` in production
- ❌ AI deletes data in database
- ❌ AI pushes without PR (except hotfix with Sandikodev's approval)

### Environment Variable Setup
```bash
# Create separate env file for AI
notepad $HOME/.config/opencode/secrets.env
# Contents: TRELLO_API_KEY=xxx, TRELLO_TOKEN=xxx

# Reference in opencode.json
# "env": "~/.config/opencode/secrets.env"
```

---

## 🔄 Multi-Tool Integration

### Tool Matrix

| Tool | Use Case | Suitable For |
|---|---|---|
| **Opencode CLI** | Complex task, code generation, refactor | All developers |
| **Cursor IDE** | Daily coding, inline AI, debugging | Developers who prefer GUI |
| **Claude Code** | Opencode alternative (vendor diversity) | All developers |
| **Claw Code** | Open-source Claude alternative | Evaluation (anti vendor lock-in) |

### Switching Between Tools
```bash
# All tools read the same configuration:
# .opencode/SHARED/* → project context
# ~/.openkb/PERSONAL/<user>/* → personal context
# ~/.openkb/ROLES/<role>.md → role instructions

# So feel free to switch tools without losing context.
```

---

## 📚 AI Agent Session Examples

### Session 1: Ihsan working on backend task

```
User:  "Work on Issue #12 about attendance validation"
AI:    "Okay, I've read Issue #12. Requirements:
        - Academic calendar validation (holiday/workday)
        - Active day validation (duty schedule)
        - Attendance time range validation
        - Geolocation (50m radius from school)
        
        I'll start with the migration first."
       
       *Writes migration, model, controller*
       
       "Migration is ready. Run it? (y/n)"
```

### Session 2: Hanif writing user story

```
User:  "Help me write a user story for the attendance report feature"
AI:    "Sure. Who will use this feature?"
User:  "Homeroom teacher"
AI:    "What does the homeroom teacher want to see?"
User:  "Monthly student attendance recap"
AI:    "Okay, here's the user story draft:
        
        As a homeroom teacher
        I want to see a monthly student attendance recap in table format
        So that I can monitor attendance in my class
        
        Acceptance Criteria:
        1. Filter: month, year, class
        2. Columns: name, total present, sick, permission, absent
        3. Export Excel
        
        Anything to add?"
```

---

## 📈 Metrics & Tracking

| Metric | Target | How to Measure |
|---|---|---|
| Cycle time (Ready → Done) | < 3 days | Trello / GitHub |
| PR review time | < 24 hours | GitHub |
| Code review iteration | < 3x per PR | GitHub |
| AI session productivity | Tasks completed per day | Trello velocity |
| Tool adoption | All developers use AI | Monthly survey |

---

*This document is part of the [Koneksi playbook](../../README.md).*
