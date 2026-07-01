# GitHub Issue Template

> Template for creating Issues in the SMA UII Yogyakarta GitHub repository.

---

## 📝 Template 1: Feature Request

```markdown
---
name: "\U0001F680 Feature Request"
about: Suggest an idea for this project
title: '[FEATURE] '
labels: enhancement
assignees: ''
---

## Problem Statement

Describe the problem to be solved:
- What is the problem?
- Who experiences it?
- How often does it happen?
- What is the impact?

## Proposed Solution

Describe the proposed solution:
- What kind of feature?
- How does it work?
- What are the benefits?

## User Story

**As a** [role]  
**I want** [feature]  
**So that** [benefit]

## Acceptance Criteria

```gherkin
Feature: [Feature name]
  Scenario: [Scenario description]
    Given [context]
    When [action]
    Then [expected result]
```

## Technical Notes

- API endpoint: `[METHOD] /api/...`
- Database table: `table_name`
- Frontend component: `ComponentName.vue`
- External services: [Service name]

## Dependencies

- [ ] Dependency 1 (link Issue)
- [ ] Dependency 2

## Out of Scope

- Features NOT included

## References

- [Link to Trello card](...)
- [Link to design](...)
- [Link to documentation](...)

## Priority

- [ ] 🔥 Critical
- [ ] ⚠️ High
- [ ] 📌 Medium
- [ ] 🐌 Low

## Estimated Effort

Story Points: 1 | 2 | 3 | 5 | 8
```

---

## 📝 Template 2: Bug Report

```markdown
---
name: "\U0001F41B Bug Report"
about: Create a report to help us improve
title: '[BUG] '
labels: bug
assignees: ''
---

## Bug Description

Describe the bug briefly and clearly.

## Severity

- [ ] 🔥 Critical (production down, data loss)
- [ ] ⚠️ Major (feature broken, workaround available)
- [ ] 📌 Minor (cosmetic, UX issue)
- [ ] 🐌 Trivial (typo, enhancement)

## Steps to Reproduce

1. Go to '...'
2. Click on '....'
3. Scroll down to '....'
4. See error

## Expected Behavior

What should have happened.

## Actual Behavior

What actually happened.

## Screenshots

If any, attach screenshots for clarity.

## Environment

**Desktop:**
- OS: Windows 11
- Browser: Chrome 114.0
- Version: v1.0.0

**Mobile:**
- Device: iPhone 13
- OS: iOS 16.0
- Browser: Safari
- Version: v1.0.0

## Error Logs

```
Paste error logs from:
- Laravel log: storage/logs/laravel.log
- Browser console: F12 → Console
- Network tab: Request/Response
```

## Possible Solution

If you have a suggested fix:
```php
// Code snippet or explanation
```

## Additional Context

Other relevant information.
```

---

## 📝 Template 3: Task Breakdown

```markdown
---
name: "\U0001F4CB Task"
about: Development task
title: '[TASK] '
labels: task
assignees: ''
---

## Context

Link to Trello card: [Card name](URL)

## Description

Describe the task to be done.

## Technical Requirements

### Backend
- [ ] Controller: `AttendanceController.php`
- [ ] Model: `Attendance.php`
- [ ] Migration: `create_attendances_table`
- [ ] Validation: `StoreAttendanceRequest.php`
- [ ] Policy: `AttendancePolicy.php`

### Frontend
- [ ] React Component: `AttendanceForm.tsx`
- [ ] Inertia Page: `resources/js/Pages/Presensi.tsx`
- [ ] TypeScript: `resources/js/types/presensi.ts`
- [ ] Tailwind CSS: Styling

### Testing
- [ ] Unit Test: `AttendanceTest.php`
- [ ] Feature Test: `CreateAttendanceTest.php`
- [ ] Manual Test: UAT checklist

## Definition of Ready

- [ ] Requirement clear (Trello card)
- [ ] Acceptance criteria defined
- [ ] Technical approach confirmed
- [ ] Dependencies resolved

## Definition of Done

- [ ] Code complete
- [ ] Unit test written (>70% coverage)
- [ ] Self-review done
- [ ] PR created
- [ ] Code review approved
- [ ] UAT passed
- [ ] Documentation updated

## Estimated Time

- [ ] < 4 hours (0.5 day)
- [ ] 4-8 hours (1 day)
- [ ] 2-3 days
- [ ] > 3 days (break down further)

## References

- [Laravel Docs](...)
- [Trello Card](...)
- [Figma Design](...)
```

---

## 📝 Template 4: Documentation

```markdown
---
name: "\U0001F4D6 Documentation"
about: Improve documentation
title: '[DOCS] '
labels: documentation
assignees: ''
---

## Type of Documentation

- [ ] API Documentation
- [ ] User Guide
- [ ] Setup Guide
- [ ] Troubleshooting
- [ ] Other (specify)

## Description

Describe what documentation needs to be created/updated.

## Target Audience

- [ ] Developer
- [ ] End User
- [ ] Stakeholder
- [ ] Admin

## Content Outline

1. Section 1
2. Section 2
3. Section 3

## Existing Documentation

Link to existing documentation (if any).

## Priority

- [ ] 🔥 Critical (blocking users/developers)
- [ ] ⚠️ High (important feature)
- [ ] 📌 Medium (nice to have)
- [ ] 🐌 Low (minor improvement)
```

---

## 💡 Best Practices

### Issue Title

**Good:**
```
[FEATURE] Student attendance with geolocation
[BUG] Login error 500 when password contains special chars
[TASK] Create attendance API endpoint
[DOCS] Add API documentation for attendance module
```

**Bad:**
```
Fix bug
New feature
Help
```

---

### Issue Description

**Do's ✅**
- Complete context
- Screenshot if UI bug
- Error log if backend bug
- Detailed steps to reproduce
- Environment info

**Don'ts ❌**
- Vague description
- No reproduction steps
- No error log
- Multiple bugs in 1 issue

---

### Label Usage

| Label | Color | Usage |
|---|---|---|
| `enhancement` | Green | Feature request |
| `bug` | Red | Bug fix |
| `task` | Blue | Development task |
| `documentation` | Purple | Docs improvement |
| `help wanted` | Yellow | Need help |
| `blocked` | Grey | Blocked by other issue |

---

### Assign Issues

```
Feature Request → Unassigned (until sprint planning)
Bug → Assign to developer on-call
Task → Assign during sprint planning
Docs → Assign to Ahmad Hanif
```

---

### Link Related Issues

```markdown
Related to #12
Blocks #34
Duplicate of #56
Part of milestone #3
```

---

## 🔄 Issue Workflow

```
1. Issue created (Ahmad/Sandikodev/Developer)
   ↓
2. Label added
   ↓
3. Sprint Planning → Assigned to developer
   ↓
4. Developer starts work → Status: In Progress
   ↓
5. PR created → Link PR in Issue
   ↓
6. PR merged → Issue auto-close
   ↓
7. Move card in GitHub Project
```

---

**Next:** [`pull-request.md`](pull-request.md)  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
