# Pull Request Template

> Template for Pull Requests in the SMA UII Yogyakarta repository.

---

## 📝 Template

```markdown
## Related Issue

Fixes #[issue-number]

## Description

Briefly describe what was changed and why.

**Context:**
[Why is this change necessary?]

**Solution:**
[How was the solution implemented?]

## Changes

### Backend
- `AttendanceController.php`: Add geolocation validation
- `Attendance.php` Model: Add scope for duplicate check
- `StoreAttendanceRequest.php`: New form request

### Frontend
- `resources/js/Components/AttendanceForm.tsx`: Add camera preview
- `resources/js/Pages/Presensi.tsx`: Handle photo capture & geolocation

### Database (PostgreSQL)
- `create_attendances_table`: Add latitude, longitude columns (PostgreSQL)

### Testing
- `AttendanceTest.php`: Add geolocation validation test
- `CreateAttendanceTest.php`: Add API endpoint test

## Type of Change

- [ ] 🚀 New feature (non-breaking change)
- [ ] 🐛 Bug fix (non-breaking change)
- [ ] ⚠️ Breaking change (fix or feature that breaks existing functionality)
- [ ] 📄 Documentation update
- [ ] 🎨 UI/UX improvement
- [ ] ⚡ Performance improvement
- [ ] 🔒 Security fix

## Testing

### Unit Tests

```bash
php artisan test
```

**Result:**
```
Tests:  45 passed, 0 failed
Coverage: 78%
```

### Manual Testing

**Checklist:**
- [ ] Login test (valid & invalid credentials)
- [ ] Submit attendance test
- [ ] Geolocation validation test
- [ ] Duplicate attendance test
- [ ] Photo upload test
- [ ] Responsive test (mobile 375px, tablet 768px, desktop 1280px)
- [ ] TypeScript compile check (`bun run tsc --noEmit`)

**Screenshots:**

Before:
[Screenshot]

After:
[Screenshot]

### API Testing

**Endpoint:** `POST /api/attendance`

**Request:**
```json
{
  "latitude": -7.7956,
  "longitude": 110.3695,
  "photo": "base64_encoded_image"
}
```

**Response:**
```json
{
  "success": true,
  "message": "Attendance submitted successfully",
  "data": {
    "id": 1,
    "status": "on_time"
  }
}
```

## Checklist

### Backend
- [ ] Conventional commit message
- [ ] No `console.log()` or `dd()`
- [ ] Service Layer pattern — logic in Service, thin controller
- [ ] PostgreSQL compatible syntax
- [ ] Unit test written & passing
- [ ] No N+1 query (eager loading used)

### Frontend (if applicable)
- [ ] TypeScript strict (no `any`)
- [ ] React hooks pattern (no class component)
- [ ] Responsive tested (mobile first)
- [ ] Loading/error/empty states handled
- [ ] No `console.log()` or `debugger`

### General
- [ ] Self-review completed
- [ ] Documentation updated (if needed)
- [ ] No merge conflicts

## Screenshots (if UI change)

| Before | After |
|---|---|
| [Image] | [Image] |

## Notes for Reviewer

- Focus review on: `AttendanceController.php` line 45-67 (geolocation validation)
- Need clarification on: Error message format (is it already aligned with UX standards?)
- Performance concern: Query at line 89 (is eager loading needed?)

## Deployment Notes

**Migration required:**
```bash
php artisan migrate
```

**Config change:**
```env
ATTENDANCE_RADIUS=50
SCHOOL_LATITUDE=-7.7956
SCHOOL_LONGITUDE=110.3695
```

**Cache clear:**
```bash
php artisan cache:clear
php artisan config:clear
```

---

**Reviewer:** @Sandikodev  
**UAT:** @Rosyiii  
**Sprint:** Sprint 2
```

---

## 💡 Best Practices

### PR Title

**Good:**
```
feat(attendance): add geolocation validation
fix(auth): resolve token expiration issue
refactor(report): optimize query performance
docs(readme): add installation guide
```

**Bad:**
```
update code
fix bug
new feature
please review
```

---

### PR Description

**Do's ✅**
- Explain "why", not just "what"
- Link related Issue
- List changes clearly
- Include testing result
- Add screenshot for UI change
- Note for reviewer (focus area)

**Don'ts ❌**
- Empty description
- Only Issue link without context
- Multiple unrelated changes in 1 PR
- No testing info

---

### PR Size

**Ideal PR:**
- < 400 lines changed
- < 10 files changed
- Single feature/fix
- Reviewable within 30 minutes

**Too Big PR:**
- > 1000 lines changed
- > 20 files changed
- Multiple features
- Reviewer fatigue

**Solution:** Split into multiple PRs

---

### Conventional Commits

**Format:**
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Examples:**
```
feat(attendance): add geolocation validation

- Add latitude/longitude validation
- Check radius 50m from school
- Return error if outside radius

Closes #12
```

```
fix(auth): resolve token expiration issue

Sanctum token does not expire after logout.
Fixed by adding token revoke on the logout endpoint.

Fixes #34
```

---

## 🔍 Review Process

### 1. Create PR

```bash
# Push branch
git push origin feature/12-attendance

# GitHub UI will suggest creating a PR
# Click "Compare & pull request"
```

---

### 2. Fill Template

- Copy template above
- Fill all sections
- Assign reviewer (@Sandikodev)
- Link Issue (`Fixes #12`)

---

### 3. Auto-Checks

GitHub will auto-run:
- CI workflow (if any)
- Mergeability check
- Conflict detection

---

### 4. Code Review

**Reviewer will:**
- Review code within 24 hours
- Comment & request changes
- Approve if OK

**Author must:**
- Respond to feedback within 24 hours
- Fix as requested
- Re-request review

---

### 5. Merge

**After approval:**
- Squash merge (default)
- Delete branch after merge
- Pull latest main

```bash
git checkout main
git pull origin main
git branch -d feature/12-attendance
```

---

## 🚦 PR Status

### Draft PR

**When:** Work in progress, not yet ready for review

**How:**
- Click "Create draft pull request"
- Label: `🚧 WIP`
- Convert to ready after completion

---

### Ready for Review

**When:** All checklist complete

**How:**
- Click "Ready for review"
- Assign reviewer
- Tag on WhatsApp: "@Sandikodev PR ready for review"

---

## 🐛 Common Issues

### Issue: PR Stuck in Review > 24 hours

**Solution:**
1. Tag reviewer in PR comment: "@Sandikodev please review"
2. Ping on WhatsApp: "PR #34 ready for review"
3. If urgent, call/PM

---

### Issue: Merge Conflict

**Solution:**
```bash
# Update main
git checkout main
git pull origin main

# Rebase branch
git checkout feature/12-attendance
git rebase main

# Fix conflict in marked files
# Edit file → resolve <<<<<<< and >>>>>>>

# Continue rebase
git add .
git rebase --continue

# Force push
git push origin feature/12-attendance --force-with-lease
```

---

### Issue: CI Failed

**Solution:**
1. Check CI log in GitHub Actions
2. Fix reported error
3. Push again (auto re-run CI)

---

## 📊 PR Metrics

### Per PR

```
- Time to first review (hours)
- Time to merge (hours)
- Comment count
- Iteration count
```

### Per Sprint

```
- Total PR merged
- Average PR size (lines)
- Average review time
- Bug rate post-merge
```

---

## 🎓 Tips for Junior Developer

### Before Submit PR

```bash
# Self-review
git diff main

# Run test
php artisan test

# Check code style
./vendor/bin/pint --test

# Build assets
bun run build

# Test locally
php artisan serve
```

---

### During Review

**Mindset:**
- Feedback = for code, not for person
- Request changes = learning opportunity
- Iteration = normal process

**Response:**
```
"Thanks for the review! Will fix."
"Good catch, I missed that."
"Question: Why use eager loading here?"
```

---

**Next:** [`sprint-planning.md`](sprint-planning.md)  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
