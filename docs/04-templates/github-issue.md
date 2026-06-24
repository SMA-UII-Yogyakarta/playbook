# GitHub Issue Template

> Template untuk membuat Issue di GitHub repository SMA UII Yogyakarta.

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

Jelaskan masalah yang ingin diselesaikan:
- Apa masalahnya?
- Siapa yang mengalami?
- Seberapa sering terjadi?
- Apa impact-nya?

## Proposed Solution

Jelaskan solusi yang diusulkan:
- Fitur seperti apa?
- Bagaimana cara kerjanya?
- Apa benefit-nya?

## User Story

**Sebagai** [role]  
**Saya ingin** [fitur]  
**Agar** [manfaat]

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

- Fitur yang TIDAK termasuk

## References

- [Link ke Trello card](...)
- [Link ke design](...)
- [Link ke dokumentasi](...)

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

Jelaskan bug secara singkat dan jelas.

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

Apa yang seharusnya terjadi.

## Actual Behavior

Apa yang sebenarnya terjadi.

## Screenshots

Jika ada, attach screenshot untuk memperjelas.

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
Paste error log dari:
- Laravel log: storage/logs/laravel.log
- Browser console: F12 → Console
- Network tab: Request/Response
```

## Possible Solution

Jika ada usulan fix:
```php
// Code snippet atau penjelasan
```

## Additional Context

Informasi lain yang relevan.
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

Link ke Trello card: [Card name](URL)

## Description

Jelaskan task yang harus dikerjakan.

## Technical Requirements

### Backend
- [ ] Controller: `AttendanceController.php`
- [ ] Model: `Attendance.php`
- [ ] Migration: `create_attendances_table`
- [ ] Validation: `StoreAttendanceRequest.php`
- [ ] Policy: `AttendancePolicy.php`

### Frontend
- [ ] Livewire Component: `AttendanceForm.php`
- [ ] Blade View: `attendance/form.blade.php`
- [ ] JavaScript: `attendance.js`
- [ ] Tailwind CSS: Styling

### Testing
- [ ] Unit Test: `AttendanceTest.php`
- [ ] Feature Test: `CreateAttendanceTest.php`
- [ ] Manual Test: UAT checklist

## Definition of Ready

- [ ] Requirement jelas (Trello card)
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

- [ ] < 4 jam (0.5 day)
- [ ] 4-8 jam (1 day)
- [ ] 2-3 hari
- [ ] > 3 hari (break down lagi)

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

Jelaskan dokumentasi apa yang perlu dibuat/diupdate.

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

Link ke dokumentasi yang sudah ada (jika ada).

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
- Context lengkap
- Screenshot jika UI bug
- Error log jika backend bug
- Steps to reproduce detail
- Environment info

**Don'ts ❌**
- Vague description
- No reproduction steps
- No error log
- Multiple bugs di 1 issue

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
1. Issue dibuat (Ahmad/Sandikodev/Developer)
   ↓
2. Label ditambahkan
   ↓
3. Sprint Planning → Assigned ke developer
   ↓
4. Developer mulai kerja → Status: In Progress
   ↓
5. PR dibuat → Link PR di Issue
   ↓
6. PR merged → Issue auto-close
   ↓
7. Move card di GitHub Project
```

---

**Next:** [`pull-request.md`](pull-request.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev