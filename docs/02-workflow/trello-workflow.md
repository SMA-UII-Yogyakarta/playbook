# Trello Workflow — Product Management

> Guide to using Trello for product management at SMART Absen SMA UII.

---

## 🎯 Purpose

Trello is the **Source of Truth for Product Management**:
- Product roadmap
- Sprint planning
- Requirement tracking
- Stakeholder feedback

**GitHub Project** is the **Source of Truth for Engineering**:
- Technical task
- Code implementation
- PR tracking
- Release management

---

## 📋 Board Structure

### Board 1: Product Roadmap

**URL:** [`https://trello.com/b/BHXA6ZcR/smart-absen-smauii`](https://trello.com/b/BHXA6ZcR/smart-absen-smauii) (invite-only)

**Columns:**

```
📌 Q2 2026 (Planned)
📌 Next Sprint
🚧 In Development
✅ Released
```

**Level:** Epic / Feature (not technical tasks)

**Example Card:**

```
┌─────────────────────────────────────┐
│ Student Attendance                  │
├─────────────────────────────────────┤
│ • Attendance with geolocation       │
│ • Camera selfie                     │
│ • Triple-layer validation           │
│ • Attendance history                │
└─────────────────────────────────────┘
```

**Card Detail:**
```markdown
## Description
Attendance feature for students with location validation and selfie photo.

## Business Value
- Simplifies student attendance monitoring
- Prevents proxy attendance
- Real-time tracking

## Acceptance Criteria
- Students can check in via web
- Geolocation validation (50m radius from school)
- Mandatory selfie with face detection
- Attendance only once per day

## Dependencies
- SSO (Authentication)
- Geolocation API
- Camera API

## Stakeholder
Pak Mahfud (SMA UII)

## Timeline
Target: Sprint 2 (Weeks 3-4)
```

---

### Board 2: Sprint Board

**URL:** [`https://trello.com/b/BHXA6ZcR/smart-absen-smauii`](https://trello.com/b/BHXA6ZcR/smart-absen-smauii) (invite-only)

**Columns:**

```
📋 Product Backlog
✅ Ready for Dev
🚧 In Progress
👀 Code Review
🧪 UAT / Testing
✅ Done
```

**Level:** Task per Sprint (2 weeks)

**Example Card:**

```
┌─────────────────────────────────────┐
│ [FE-01] Login Page                  │
├─────────────────────────────────────┤
│ Assignee: Fathan                    │
│ Sprint: 1                           │
│ Story Points: 3                     │
└─────────────────────────────────────┘
```

---

## 🏷️ Labels

### Priority Labels

| Label | Color | Meaning |
|---|---|---|
| `🔥 Critical` | Red | Must be completed this sprint |
| `⚠️ High` | Orange | High priority |
| `📌 Medium` | Yellow | Normal priority |
| `🐌 Low` | Green | Can be postponed |

### Type Labels

| Label | Color | Meaning |
|---|---|---|
| `📱 Frontend` | Blue | Frontend task |
| `⚙️ Backend` | Purple | Backend task |
| `🎨 UI/UX` | Pink | Design task |
| `📄 Docs` | Gray | Documentation |
| `🐛 Bug` | Red | Bug fix |

### Sprint Labels

| Label | Color | Meaning |
|---|---|---|
| `Sprint 1` | Blue | Weeks 1-2 |
| `Sprint 2` | Green | Weeks 3-4 |
| `Sprint 3` | Orange | Weeks 5-6 |
| `Sprint 4` | Purple | Weeks 7-8 |

---

## 📝 Card Workflow

### 1. Card Created (Ahmad Hanif)

**PIC:** Ahmad Hanif

**Activities:**
- Research requirements
- Write user story
- Define acceptance criteria
- Add to `Product Backlog` column

**Checklist:**
```markdown
## Requirement Checklist
- [ ] User story is clear
- [ ] Acceptance criteria testable
- [ ] Business value defined
- [ ] Stakeholder approved
```

---

### 2. Card Reviewed (Sandikodev)

**PIC:** Sandikodev

**Activities:**
- Review requirement clarity
- Break down into technical tasks
- Estimate effort (Story Points)
- Move to `Ready for Dev` if ready

**Checklist:**
```markdown
## Technical Review
- [ ] Requirement is clear (not ambiguous)
- [ ] Acceptance criteria testable
- [ ] Technical feasibility confirmed
- [ ] Dependencies identified
- [ ] Story points assigned
```

---

### 3. Developer Takes Task (Fathan/Ihsan)

**PIC:** Developer (Fathan/Ihsan)

**Activities:**
- Assign name to card
- Move to `In Progress`
- Create GitHub Issue (link in card)
- Start coding

**Checklist:**
```markdown
## Development Checklist
- [ ] GitHub Issue created
- [ ] Branch created
- [ ] Coding in progress
- [ ] Self-test done
- [ ] PR created
```

**Update Card:**
```markdown
## Development
- GitHub Issue: #12
- Branch: feature/12-login
- PR: #34
- Status: In Progress
```

---

### 4. Code Review (Sandikodev)

**PIC:** Sandikodev

**Activities:**
- Review PR on GitHub
- Approve or request changes
- Move card to `UAT / Testing` if PR merged

**Checklist:**
```markdown
## Code Review
- [ ] Code quality OK
- [ ] Test coverage OK
- [ ] Security check OK
- [ ] Performance OK
- [ ] PR merged
```

---

### 5. UAT / Testing (Ahmad Hanif)

**PIC:** Ahmad Hanif

**Activities:**
- Test in staging environment
- Validate acceptance criteria
- Approve or report bug
- Move to `Done` if approved

**Checklist:**
```markdown
## UAT Checklist
- [ ] All acceptance criteria met
- [ ] No critical bug
- [ ] UI/UX meets expectations
- [ ] Tested in staging
- [ ] Stakeholder demo (if needed)
```

---

### 6. Card Done

**PIC:** Sandikodev

**Activities:**
- Update Trello card
- Add to Release Notes (if sprint end)
- Deploy to production (if scheduled)

---

## 📊 Definition of Ready (DoR)

Card may move from `Backlog` → `Ready for Dev` if:

```markdown
## Definition of Ready

✅ User Story format complete:
   - "As a [role]..."
   - "I want [feature]..."
   - "So that [benefit]..."

✅ Acceptance Criteria clear:
   - Specific
   - Measurable
   - Testable

✅ Business value defined

✅ Dependencies identified

✅ Technical feasibility confirmed

✅ Story points assigned (1, 2, 3, 5, 8)
```

---

## 📊 Definition of Done (DoD)

Card may move from `Testing` → `Done` if:

```markdown
## Definition of Done

✅ Code complete

✅ Unit test green (>70% coverage)

✅ Code review approved (minimum 1)

✅ PR merged to main

✅ UAT passed (Ahmad Hanif)

✅ No critical/open bugs

✅ Documentation updated (if needed)

✅ Deployed to staging

✅ Stakeholder demo (if required)
```

---

## 🔄 Sprint Cycle

### Sprint Duration: 2 Weeks

```
Week 1          Week 2
Mon Tue Wed Thu Fri Mon Tue Wed Thu Fri
│               │               │
├─ Sprint       ├─ Development  ├─ Sprint
│  Planning     │               │  Review
│               │               │  & Retro
```

### Sprint Timeline

**Day 1 (Monday Week 1): Sprint Planning**
- Review backlog
- Commit to sprint goal
- Assign tasks
- Estimate story points

**Day 1-8: Development**
- Daily standup (15 minutes, WhatsApp)
- Update Trello card progress
- PR & code review

**Day 9 (Friday Week 2): Testing**
- UAT by Ahmad Hanif
- Bug fixing

**Day 10 (Monday Week 3): Sprint Review & Retrospective**
- Demo to stakeholder (Pak Mahfud)
- Retrospective: What went well, what to improve
- Sprint 2 planning

---

## 📈 Velocity Tracking

### Story Points

**Fibonacci Scale:**
```
1 — Tiny (1-2 hours)
2 — Small (0.5 day)
3 — Medium (1 day)
5 — Large (2-3 days)
8 — XL (1 sprint)
```

**Velocity Calculation:**
```
Sprint 1: 13 points completed
Sprint 2: 15 points completed
Sprint 3: 12 points completed

Average Velocity: 13.3 points/sprint
```

**Capacity Planning:**
```
Sprint 4 capacity: 13 points

Task breakdown:
- Login: 3 points
- Dashboard: 5 points
- Attendance: 5 points
Total: 13 points ✅
```

---

## 🔗 Trello ↔ GitHub Integration

### Link Trello Card ↔ GitHub Issue

**In Trello Card:**
```markdown
## Links
- GitHub Issue: https://github.com/SMA-UII-Yogyakarta/core/issues/12
- PR: https://github.com/SMA-UII-Yogyakarta/core/pull/34
```

**In GitHub Issue:**
```markdown
## Context
Trello: https://trello.com/c/ABC123
```

### Automation (Power-Ups)

**GitHub Power-Up:**
- Link GitHub repo to Trello
- Attach PR to card
- Auto-update status

**Card Mapping:**
```
Trello: In Progress  →  GitHub: In Progress
Trello: Code Review  →  GitHub: PR Open
Trello: Done         →  GitHub: Closed/Merged
```

---

## 💡 Best Practices

### Do's ✅

- Update card status in real-time
- Comment progress on card
- Link GitHub Issue on card
- Move card immediately after status change
- Detailed checklist for complex tasks

### Don'ts ❌

- Don't let a card stay stuck > 2 days without an update
- Don't skip DoR/DoD checklist
- Don't combine multiple features in 1 card
- Don't use vague acceptance criteria
- Don't forget to move card to Done after deploy

---

## 📱 Mobile Access

**Trello Mobile App:**
- iOS: [Download](https://apps.apple.com/app/trello/id461504587)
- Android: [Download](https://play.google.com/store/apps/details?id=com.trello)

**Quick Actions:**
- Update card status
- Add comment
- Check/uncheck checklist
- Assign member
- Add attachment (screenshot bug)

---

## 🆘 Troubleshooting

### Issue: Card requirement unclear

**Solution:**
1. Comment on card: "@Ahmad Hanif please clarify requirement for..."
2. Wait for clarification
3. Update card after clear

### Issue: Task blocker > 2 hours

**Solution:**
1. Add label `🚫 Blocked` to card
2. Comment on card: "Blocker: [problem description]"
3. Tag Sandikodev: "@Sandikodev need help for..."
4. Escalate in WhatsApp Group

### Issue: Card stuck in Code Review

**Solution:**
1. Tag reviewer: "@Sandikodev please review PR #..."
2. Wait max 24 hours
3. If no response, ping on WhatsApp

---

## 📚 Resources

- [Trello Guide](https://trello.com/guide)
- [Agile with Trello](https://trello.com/agile)
- [Power-Ups](https://trello.com/power-ups)

---

**Next:** [`communication.md`](communication.md)  
**Last Updated:** June 2026  
**Maintained by:** Ahmad Hanif
