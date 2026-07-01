# Communication Guidelines

> Communication standards for the SMA UII Yogyakarta engineering team.

---

## 📱 Communication Channels

| Channel | Purpose | Response Time | Members |
|---|---|---|---|
| **WhatsApp Group** | Quick communication, daily standup, urgent issues | < 1 hour | All team |
| **GitHub Issues** | Technical discussion, task tracking | < 24 hours | Developers |
| **GitHub PR Comments** | Code review discussion | < 24 hours | Developer + Reviewer |
| **Trello Card Comments** | Product discussion, requirement clarification | < 24 hours | All team |
| **Email** | Formal communication, stakeholder report | < 48 hours | All team |
| **Meeting (Google Meet)** | Sprint planning, retrospective, demo | Scheduled | All team |

---

## 💬 WhatsApp Group

**Name:** SMART Absen Dev Team  
**Members:**
- Sandikodev (Lead)
- Ahmad Hanif (Product Analyst)
- Fathan Mubina (Developer)
- Ihsan (Developer)
- Pak Mahfud (Stakeholder)

### Etiquette

**Do's ✅**
- Standup update every morning (format below)
- Share daily progress
- Ask if stuck > 30 minutes
- Share blockers immediately
- Tag the intended person: `@Sandikodev`
- Use threads to discuss specific topics

**Don'ts ❌**
- Don't spam (send 1 complete message, not 10 short messages)
- Don't discuss technical details too deeply (move to GitHub Issue)
- Don't forget to tag if you need a response
- Don't skip standup without notice

### Daily Standup Format

**Time:** Every day at 09:00 WIB  
**Format:**

```
📅 Daily Standup — [Date]
👤 [Name]

✅ Yesterday:
- Task 1
- Task 2

🎯 Today:
- Task 1
- Task 2

🚫 Blocker:
- [Blocker description, or "None"]
```

**Example:**

```
📅 Daily Standup — 24 June 2026
👤 Fathan

✅ Yesterday:
- Login page UI (completed)
- Responsive testing (completed)

🎯 Today:
- Dashboard component
- Fix bug in attendance form

🚫 Blocker:
- None
```

---

## 🐛 Escalation Matrix

### Level 1: Task Blocker (< 2 hours)

**Channel:** WhatsApp Group  
**Response:** Team  
**Example:**
```
"Guys, anyone know how to handle timezone in React?"
```

---

### Level 2: Task Blocker (> 2 hours)

**Channel:** WhatsApp Group + Tag Sandikodev  
**Response:** Sandikodev  
**Example:**
```
"@Sandikodev, stuck on geolocation validation for 2 hours.
Can you help with pair programming this afternoon?"
```

---

### Level 3: Critical Production Bug

**Channel:** WhatsApp Group + Call Sandikodev  
**Response:** Immediate  
**Example:**
```
🚨 CRITICAL: Login error in production
Users cannot log in since 10 minutes ago.
Error 500 at /auth/login.
@sandikodev checking logs now.
```

---

### Level 4: Requirement Ambiguity

**Channel:** Trello Card Comment + Tag Ahmad Hanif  
**Response:** Ahmad Hanif  
**Example:**
```
"@Ahmad Hanif, for the 'export report' user story,
need clarification: what export format? Excel or PDF?
And export period per month or custom date range?"
```

---

### Level 5: Stakeholder Decision

**Channel:** Email + WhatsApp (urgent)  
**Response:** Pak Mahfud + Sandikodev  
**Example:**
```
"Pak Mahfud, for the attendance feature, there are 2 options:
1. Attendance once per day (simple)
2. Check-in & check-out attendance (more detailed)

Our recommendation is option 1 for MVP.
Please advise so the team can proceed with development."
```

---

## 📧 Email Templates

### Sprint Report (To Stakeholder)

**To:** Pak Mahfud  
**CC:** Team  
**Subject:** Sprint [X] Report — SMART Absen — [Date]

```
Assalamu'alaikum Pak Mahfud,

Here is the Sprint [X] report for SMART Absen development:

✅ COMPLETED (Sprint [X])
- Feature 1
- Feature 2
- Feature 3

🚧 IN PROGRESS
- Task 1 (50%)
- Task 2 (30%)

📊 METRICS
- Velocity: [X] story points
- Bug count: [X] (critical: 0)
- Sprint completion: [X]%

📅 NEXT SPRINT
- Feature 1
- Feature 2

🚫 BLOCKER
- [Blocker description, or "None"]

Please provide feedback and direction.

Thank you.

Best regards,
Sandikodev
PT Koneksi Jaringan Indonesia
```

---

### Production Deployment Notice

**To:** Pak Mahfud, SMA UII Staff  
**CC:** Team  
**Subject:** Production Deployment — SMART Absen v1.0 — [Date]

```
Assalamu'alaikum,

We would like to inform you that there will be a SMART Absen version 1.0 deployment:

📅 Date: [Day, Date]
⏰ Time: [Time] WIB
⏱️ Duration: [X] hours (estimated)
🔧 Impact: [Downtime / No downtime]

NEW FEATURES
- Feature 1
- Feature 2

BUG FIX
- Fix issue 1
- Fix issue 2

Please inform users if there is any downtime.

Thank you.

Best regards,
Sandikodev
```

---

## 🎯 Meeting Guidelines

### Sprint Planning Meeting

**Frequency:** Every 2 weeks (Monday morning Week 1)  
**Duration:** 60-90 minutes  
**Attendees:** All team  
**Agenda:**
1. Review previous sprint (15 minutes)
2. Present backlog for next sprint (15 minutes)
3. Story point estimation (30 minutes)
4. Commit sprint goal (15 minutes)
5. Assign tasks (15 minutes)

**Preparation:**
- Ahmad: Backlog ready in Trello
- Sandikodev: Technical breakdown ready
- Developer: Review backlog before meeting

---

### Sprint Review & Demo

**Frequency:** Every 2 weeks (Monday morning Week 3)  
**Duration:** 60 minutes  
**Attendees:** All team + Pak Mahfud  
**Agenda:**
1. Demo completed features (30 minutes)
2. Stakeholder feedback (15 minutes)
3. Q&A (15 minutes)

**Preparation:**
- Developer: Demo environment ready
- Ahmad: Feedback form ready

---

### Sprint Retrospective

**Frequency:** Every 2 weeks (after Sprint Review)  
**Duration:** 45-60 minutes  
**Attendees:** Internal team (without stakeholder)  
**Agenda:**
1. What went well? (15 minutes)
2. What could be improved? (15 minutes)
3. Action items for next sprint (15 minutes)

**Format:**
```
😊 Went Well
- Code review faster
- Communication smooth

🤔 To Improve
- Task estimation off
- Blocker not escalated promptly

✅ Action Items
- Sandikodev: Daily blocker check-in
- Fathan: Update Trello status more diligently
```

---

### Daily Standup (Async)

**Frequency:** Every day (Monday-Friday) at 09:00  
**Duration:** 15 minutes (sync) or async on WhatsApp  
**Attendees:** Developers + Sandikodev  
**Format:** See "Daily Standup Format" above

**Note:**
- Sync meeting only if there are complex discussions
- Default: async on WhatsApp

---

## 📝 Documentation Communication

### GitHub Issue Discussion

**When:** Technical discussion for specific tasks  
**Format:**

```markdown
## Question
[Question description]

## Context
[Code link, screenshot, error log]

## Proposed Solution
[Proposed solution]

## Question for Reviewer
@Sandikodev is this approach correct?
```

---

### Pull Request Discussion

**When:** Code review feedback  
**Format:**

```markdown
## Review Comment
[Specific feedback with line reference]

## Suggestion
```php
// Before
$user = User::find($id);

// After
$user = User::with('roles')->findOrFail($id);
```

## Question
@Hans02-Neo are there any performance considerations for this query?
```

---

### Trello Card Discussion

**When:** Requirement clarification  
**Format:**

```markdown
@Ahmad Hanif

Need clarification for acceptance criteria:

"Export report max 1000 rows"

Questions:
1. What happens if data > 1000 rows?
   - Error?
   - Paginate?
   - Truncate?

2. Is there a period filter for this 1000 row limit?

Please advise.
```

---

## 🌐 Async Communication Best Practices

### Context is King

**Bad:**
```
"Got an error, how to fix it?"
```

**Good:**
```
"Error 500 at endpoint POST /api/attendance.
Tried debugging, turns out null pointer at line 45 AttendanceController.php.
Stack trace: [paste error]
Already tried: null check, still error.
Any ideas?"
```

---

### One Message, Complete Info

**Bad:**
```
Message 1: "Guys"
Message 2: "anyone knows Java?"
Message 3: "urgent"
```

**Good:**
```
"Guys, anyone experienced with Laravel Sanctum?
Need help implementing multi-device auth.
Urgent for this sprint.
@Sandikodev can you help this afternoon?"
```

---

### Tag the Right Person

```
General question → WhatsApp Group
Technical bug → @Sandikodev
Requirement → @Ahmad Hanif
Frontend → @Fathan
Backend → @Ihsan
Stakeholder decision → @Pak Mahfud
```

---

## 🕐 Response Time SLA

| Channel | Priority | Expected Response |
|---|---|---|
| WhatsApp (urgent) | Critical | < 15 minutes |
| WhatsApp (general) | High | < 1 hour |
| GitHub Issue | Medium | < 24 hours |
| GitHub PR Review | High | < 24 hours |
| Trello Comment | Medium | < 24 hours |
| Email | Low | < 48 hours |

---

## 🚨 Crisis Communication

### Production Outage

**Step 1:** WhatsApp Group + Call Sandikodev
```
🚨 CRITICAL: Production down
Error: [description]
Impact: [number of users affected]
Started: [time]
```

**Step 2:** Sandikodev investigating
```
Checking logs...
ETA fix: 30 minutes
```

**Step 3:** Periodic updates (every 15 minutes)
```
Update 1: Root cause identified (database connection)
Update 2: Fix in progress
Update 3: Fix deployed, monitoring...
```

**Step 4:** Post-mortem (after fix)
```
✅ Resolved
Root cause: [description]
Fix: [description]
Prevention: [action items]
```

---

## 📊 Communication Metrics

### Team Health Check (Monthly)

**Questions:**
1. Is communication smooth? (1-5)
2. Are blockers resolved quickly? (1-5)
3. Are requirements clear? (1-5)
4. Is feedback constructive? (1-5)

**Target:** Average score > 4.0

---

**Next:** [`code-review.md`](../03-sop/code-review.md)  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
