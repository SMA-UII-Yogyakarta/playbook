# Pull Request Template

> Template untuk Pull Request di repository SMA UII Yogyakarta.

---

## 📝 Template

```markdown
## Related Issue

Fixes #[issue-number]

## Description

Jelaskan secara singkat apa yang diubah dan kenapa.

**Context:**
[Kenapa perubahan ini diperlukan?]

**Solution:**
[Bagaimana solusi yang diimplementasikan?]

## Changes

### Backend
- `AttendanceController.php`: Add geolocation validation
- `Attendance.php` Model: Add scope for duplicate check
- `StoreAttendanceRequest.php`: New form request

### Frontend
- `attendance-form.blade.php`: Add camera preview
- `AttendanceForm.php` Livewire: Handle photo capture

### Database
- `create_attendances_table`: Add latitude, longitude columns

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

- [ ] Conventional commit message
- [ ] No `console.log()` or `dd()`
- [ ] No commented-out code
- [ ] Self-review completed
- [ ] Code follows Laravel conventions
- [ ] Documentation updated (if needed)
- [ ] CHANGELOG updated (if needed)
- [ ] No merge conflicts

## Screenshots (if UI change)

| Before | After |
|---|---|
| [Image] | [Image] |

## Notes for Reviewer

- Focus review on: `AttendanceController.php` line 45-67 (geolocation validation)
- Need clarification on: Error message format (apakah sudah sesuai UX standard?)
- Performance concern: Query di line 89 (apakah perlu eager loading?)

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
- Add screenshot untuk UI change
- Note untuk reviewer (focus area)

**Don'ts ❌**
- Empty description
- Hanya link Issue tanpa context
- Multiple unrelated changes di 1 PR
- No testing info

---

### PR Size

**Ideal PR:**
- < 400 lines changed
- < 10 files changed
- Single feature/fix
- Reviewable dalam 30 menit

**Too Big PR:**
- > 1000 lines changed
- > 20 files changed
- Multiple features
- Reviewer fatigue

**Solution:** Split jadi multiple PR

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

Token Sanctum tidak expire setelah logout.
Fix dengan menambahkan token revoke di logout endpoint.

Fixes #34
```

---

## 🔍 Review Process

### 1. Create PR

```bash
# Push branch
git push origin feature/12-attendance

# GitHub UI akan suggest create PR
# Klik "Compare & pull request"
```

---

### 2. Fill Template

- Copy template di atas
- Isi semua section
- Assign reviewer (@Sandikodev)
- Link Issue (`Fixes #12`)

---

### 3. Auto-Checks

GitHub akan auto-run:
- CI workflow (jika ada)
- Mergeability check
- Conflict detection

---

### 4. Code Review

**Reviewer akan:**
- Review code dalam 24 jam
- Comment & request changes
- Approve jika OK

**Author harus:**
- Respond feedback dalam 24 jam
- Fix sesuai request
- Re-request review

---

### 5. Merge

**Setelah approve:**
- Squash merge (default)
- Delete branch setelah merge
- Pull latest main

```bash
git checkout main
git pull origin main
git branch -d feature/12-attendance
```

---

## 🚦 PR Status

### Draft PR

**When:** Work in progress, belum siap review

**How:**
- Klik "Create draft pull request"
- Label: `🚧 WIP`
- Convert to ready setelah selesai

---

### Ready for Review

**When:** Semua checklist complete

**How:**
- Klik "Ready for review"
- Assign reviewer
- Tag di WhatsApp: "@Sandikodev PR ready untuk review"

---

## 🐛 Common Issues

### Issue: PR Stuck di Review > 24 jam

**Solution:**
1. Tag reviewer di PR comment: "@Sandikodev mohon review"
2. Ping di WhatsApp: "PR #34 ready untuk review"
3. Jika urgent, call/PM

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

# Fix conflict di file yang ditandai
# Edit file → resolve <<<<<<< dan >>>>>>>

# Continue rebase
git add .
git rebase --continue

# Force push
git push origin feature/12-attendance --force-with-lease
```

---

### Issue: CI Failed

**Solution:**
1. Check CI log di GitHub Actions
2. Fix error yang reported
3. Push ulang (auto re-run CI)

---

## 📊 PR Metrics

### Per PR

```
- Time to first review (jam)
- Time to merge (jam)
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

## 🎓 Tips untuk Junior Developer

### Before Submit PR

```bash
# Self-review
git diff main

# Run test
php artisan test

# Check code style
./vendor/bin/pint --test

# Build assets
npm run build

# Test locally
php artisan serve
```

---

### During Review

**Mindset:**
- Feedback = untuk code, bukan untuk person
- Request changes = learning opportunity
- Iteration = normal process

**Response:**
```
"Thanks for the review! Will fix."
"Good catch, I missed that."
"Question: Kenapa pakai eager loading di sini?"
```

---

**Next:** [`sprint-planning.md`](sprint-planning.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev