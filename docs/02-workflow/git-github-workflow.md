# Git & GitHub Workflow

> Standar workflow Git & GitHub untuk tim engineering SMA UII Yogyakarta.

---

## 🎯 Prinsip Dasar

1. **Main Branch adalah Sacred**
   - `main` selalu deployable
   - Tidak ada commit langsung ke `main`
   - Semua perubahan via Pull Request

2. **Satu Task = Satu Branch = Satu PR**
   - Jangan gabungkan fitur berbeda di branch sama
   - Jangan gabungkan bugfix dengan fitur

3. **Commit Message yang Jelas**
   - Conventional Commits
   - Bahasa Inggris
   - Jelaskan "kenapa", bukan "apa"

4. **Review Sebelum Merge**
   - Minimal 1 approval (Sandikodev)
   - CI check harus hijau
   - Self-review sebelum request review

---

## 🌿 Branching Strategy

### Branch Types

```
main
│
├── feature/ISSUE-12-login-api          # Fitur baru
├── bugfix/ISSUE-34-fix-null-pointer    # Bug fix
├── hotfix/fix-critical-login-error     # Critical production fix
├── refactor/ISSUE-56-optimize-query    # Refactor tanpa perubahan logic
├── docs/update-readme                  # Dokumentasi
└── chore/upgrade-laravel               # Maintenance
```

### Naming Convention

```
{type}/{ISSUE-ID}-{short-description}
```

**Contoh:**
```
feature/12-student-attendance
bugfix/34-fix-validation-error
hotfix/fix-critical-auth-bug
refactor/56-optimize-attendance-query
docs/add-api-documentation
chore/upgrade-laravel-13
```

### Branch Lifecycle

```bash
# 1. Update main branch
git checkout main
git pull origin main

# 2. Buat branch baru
git checkout -b feature/12-attendance-api

# 3. Coding... commit... commit...

# 4. Push branch
git push origin feature/12-attendance-api

# 5. Buat Pull Request di GitHub

# 6. Setelah merge, delete branch
git branch -d feature/12-attendance-api
git push origin --delete feature/12-attendance-api
```

---

## 📝 Commit Message Convention

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

| Type | Description |
|---|---|
| `feat` | Fitur baru |
| `fix` | Bug fix |
| `docs` | Dokumentasi |
| `style` | Formatting (semicolon, spacing, etc) |
| `refactor` | Refactor code (bukan fitur, bukan bugfix) |
| `test` | Menambah/memperbaiki test |
| `chore` | Maintenance (upgrade package, config, etc) |

### Examples

**Good:**
```
feat(presensi): add geolocation validation

- Add latitude/longitude validation
- Check if coordinates within school radius
- Return error if outside allowed area

Closes #12
```

```
fix(auth): resolve token expiration issue

Token Sanctum tidak expire setelah logout.
Fix dengan menambahkan token revoke di logout endpoint.

Fixes #34
```

**Bad:**
```
fix bug
```

```
update code
```

```
perbaikan presensi
```

---

## 🔄 Pull Request Workflow

### 1. Sebelum Buat PR

**Checklist:**
- [ ] Code complete
- [ ] Self-review (baca ulang code sendiri)
- [ ] Unit test hijau
- [ ] No `console.log()` atau `dd()`
- [ ] No commented-out code
- [ ] Follow Laravel conventions
- [ ] Update dokumentasi (jika perlu)

### 2. Buat Pull Request

**GitHub UI:**
1. Buka repository di GitHub
2. Klik "Compare & pull request"
3. Isi template PR
4. Assign reviewer (Sandikodev)
5. Link Issue (`Fixes #12`)

### 3. PR Template

```markdown
## Related Issue
Fixes #12

## Description
Jelaskan apa yang diubah dan kenapa

## Changes
- `AttendanceController.php`: add geolocation validation
- `presensi.blade.php`: add camera preview

## Testing
- [ ] Unit test
- [ ] Manual test (screenshot jika perlu)

## Screenshots
<!-- Jika ada perubahan UI -->

## Checklist
- [ ] Conventional commit
- [ ] No console.log
- [ ] Self-review completed
- [ ] Documentation updated
```

### 4. Code Review Process

**Reviewer (Sandikodev):**
- Review dalam 24 jam
- Berikan feedback spesifik
- Request changes atau Approve

**Author (Fathan/Ihsan):**
- Respond feedback
- Fix sesuai request
- Re-request review

**Merge Criteria:**
- ✅ Minimal 1 approval
- ✅ CI check hijau (jika ada)
- ✅ No unresolved comments
- ✅ Squash merge (default)

### 5. Setelah Merge

**Author:**
- Delete branch
- Pull latest main
- Test di local

```bash
git checkout main
git pull origin main
git branch -d feature/12-attendance-api
```

---

## 🚨 Handling Conflicts

### Jika Ada Merge Conflict

```bash
# 1. Update main
git checkout main
git pull origin main

# 2. Rebase branch
git checkout feature/12-attendance-api
git rebase main

# 3. Fix conflict di file yang ditandai
# Edit file → resolve <<<<<<< dan >>>>>>>

# 4. Continue rebase
git add .
git rebase --continue

# 5. Force push (karena history berubah)
git push origin feature/12-attendance-api --force-with-lease
```

### Prevent Conflict

- Update `main` sering (setiap hari jika possible)
- Komunikasi di WhatsApp jika ada file yang overlap
- Pecah task kecil-kecil

---

## 🛠️ Git Commands Cheat Sheet

### Daily Commands

```bash
# Check status
git status

# Lihat perubahan
git diff

# Stage file
git add file.php
git add .  # semua file

# Commit
git commit -m "feat: add attendance validation"

# Push
git push origin feature/12-attendance-api

# Pull latest main
git checkout main
git pull origin main

# Buat branch baru
git checkout -b feature/12-new-feature

# Switch branch
git checkout feature/12-attendance-api

# Delete branch (local)
git branch -d feature/12-attendance-api

# Delete branch (remote)
git push origin --delete feature/12-attendance-api
```

### Advanced Commands

```bash
# Stash perubahan (simpan untuk nanti)
git stash
git stash pop

# Lihat log
git log --oneline -10

# Undo commit (belum push)
git reset --hard HEAD~1

# Rebase interactive
git rebase -i HEAD~3

# Cherry pick commit
git cherry-pick <commit-hash>
```

---

## 🔐 Security Best Practices

### Jangan Pernah Commit

- [ ] `.env` file
- [ ] API keys, tokens, passwords
- [ ] Database credentials
- [ ] Private keys
- [ ] `vendor/` directory
- [ ] `node_modules/`

### Jika Tidak Sengaja Commit Secret

```bash
# 1. Revert commit yang ada secret
git revert <commit-hash>

# 2. Rotate secret yang ter-expose
# Ganti API key, password, dll

# 3. Force push (jika perlu)
git push origin main --force
```

---

## 📊 GitHub Project Integration

### Update Status Otomatis

GitHub Project akan auto-update:

1. **Issue dibuat** → `Backlog`
2. **Issue assigned** → `In Progress`
3. **PR dibuat** → `Code Review`
4. **PR merged** → `Done`

### Manual Update

Jika automation tidak jalan:
1. Buka GitHub Project
2. Drag & drop card ke kolom yang sesuai
3. Update status di Trello juga

---

## 🐛 Common Issues & Solutions

### Issue: "You need to resolve your current index first"

**Solusi:**
```bash
git stash
git pull origin main
git stash pop
```

### Issue: "Permission denied (publickey)"

**Solusi:**
1. Regenerate SSH key
2. Add ke GitHub
3. Test: `ssh -T git@github.com`

### Issue: "Changes not staged for commit"

**Solusi:**
```bash
git add .
git commit -m "fix: your commit message"
```

### Issue: Wrong branch

**Solusi:**
```bash
# Stash perubahan
git stash

# Checkout branch yang benar
git checkout correct-branch

# Apply stash
git stash pop
```

---

## 📚 Resources

- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [Git Documentation](https://git-scm.com/doc)
- [Laravel Git Workflow](https://laravel.com/docs/master/contributions)

---

**Next:** [`trello-workflow.md`](trello-workflow.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev