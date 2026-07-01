# Git & GitHub Workflow

> Standard Git & GitHub workflow for the SMA UII Yogyakarta engineering team.

---

## 🎯 Basic Principles

1. **Main Branch is Sacred**
   - `main` is always deployable
   - No direct commits to `main`
   - All changes via Pull Request

2. **One Task = One Branch = One PR**
   - Don't combine different features in the same branch
   - Don't combine bugfix with feature

3. **Clear Commit Message**
   - Conventional Commits
   - Use English
   - Explain "why", not "what"

4. **Review Before Merge**
   - Minimum 1 approval (Sandikodev)
   - CI check must be green
   - Self-review before requesting review

---

## 🌿 Branching Strategy

### Branch Types

```
main
│
├── feature/ISSUE-12-login-api          # New feature
├── bugfix/ISSUE-34-fix-null-pointer    # Bug fix
├── hotfix/fix-critical-login-error     # Critical production fix
├── refactor/ISSUE-56-optimize-query    # Refactor without logic changes
├── docs/update-readme                  # Documentation
└── chore/upgrade-laravel               # Maintenance
```

### Naming Convention

```
{type}/{ISSUE-ID}-{short-description}
```

**Examples:**
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

# 2. Create new branch
git checkout -b feature/12-attendance-api

# 3. Coding... commit... commit...

# 4. Push branch
git push origin feature/12-attendance-api

# 5. Create Pull Request on GitHub

# 6. After merge, delete branch
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
| `feat` | New feature |
| `fix` | Bug fix |
| `docs` | Documentation |
| `style` | Formatting (semicolon, spacing, etc) |
| `refactor` | Code refactor (not a feature, not a bugfix) |
| `test` | Adding/fixing tests |
| `chore` | Maintenance (package upgrade, config, etc) |

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

Sanctum token does not expire after logout.
Fix by adding token revoke at logout endpoint.

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

### 1. Before Creating PR

**Checklist:**
- [ ] Code complete
- [ ] Self-review (reread own code)
- [ ] Unit test green
- [ ] No `console.log()` or `dd()`
- [ ] No commented-out code
- [ ] Follow Laravel conventions
- [ ] Update documentation (if needed)

### 2. Create Pull Request

**GitHub UI:**
1. Open repository on GitHub
2. Click "Compare & pull request"
3. Fill in PR template
4. Assign reviewer (Sandikodev)
5. Link Issue (`Fixes #12`)

### 3. PR Template

```markdown
## Related Issue
Fixes #12

## Description
Describe what was changed and why

## Changes
- `AttendanceController.php`: add geolocation validation
- `presensi.blade.php`: add camera preview

## Testing
- [ ] Unit test
- [ ] Manual test (screenshot if needed)

## Screenshots
<!-- If there are UI changes -->

## Checklist
- [ ] Conventional commit
- [ ] No console.log
- [ ] Self-review completed
- [ ] Documentation updated
```

### 4. Code Review Process

**Reviewer (Sandikodev):**
- Review within 24 hours
- Provide specific feedback
- Request changes or Approve

**Author (Fathan/Ihsan):**
- Respond to feedback
- Fix as requested
- Re-request review

**Merge Criteria:**
- ✅ Minimum 1 approval
- ✅ CI check green (if any)
- ✅ No unresolved comments
- ✅ Squash merge (default)

### 5. After Merge

**Author:**
- Delete branch
- Pull latest main
- Test locally

```bash
git checkout main
git pull origin main
git branch -d feature/12-attendance-api
```

---

## 🚨 Handling Conflicts

### If There Is a Merge Conflict

```bash
# 1. Update main
git checkout main
git pull origin main

# 2. Rebase branch
git checkout feature/12-attendance-api
git rebase main

# 3. Fix conflict in marked files
# Edit file → resolve <<<<<<< and >>>>>>>

# 4. Continue rebase
git add .
git rebase --continue

# 5. Force push (because history changed)
git push origin feature/12-attendance-api --force-with-lease
```

### Prevent Conflict

- Update `main` often (daily if possible)
- Communicate on WhatsApp if there are overlapping files
- Break tasks into small pieces

---

## 🛠️ Git Commands Cheat Sheet

### Daily Commands

```bash
# Check status
git status

# View changes
git diff

# Stage file
git add file.php
git add .  # all files

# Commit
git commit -m "feat: add attendance validation"

# Push
git push origin feature/12-attendance-api

# Pull latest main
git checkout main
git pull origin main

# Create new branch
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
# Stash changes (save for later)
git stash
git stash pop

# View log
git log --oneline -10

# Undo commit (not yet pushed)
git reset --hard HEAD~1

# Rebase interactive
git rebase -i HEAD~3

# Cherry pick commit
git cherry-pick <commit-hash>
```

---

## 🔐 Security Best Practices

### Never Commit

- [ ] `.env` file
- [ ] API keys, tokens, passwords
- [ ] Database credentials
- [ ] Private keys
- [ ] `vendor/` directory
- [ ] `node_modules/`

### If You Accidentally Commit a Secret

```bash
# 1. Revert commit that contains the secret
git revert <commit-hash>

# 2. Rotate exposed secret
# Change API key, password, etc.

# 3. Force push (if necessary)
git push origin main --force
```

---

## 📊 GitHub Project Integration

### Automatic Status Update

GitHub Project will auto-update:

1. **Issue created** → `Backlog`
2. **Issue assigned** → `In Progress`
3. **PR created** → `Code Review`
4. **PR merged** → `Done`

### Manual Update

If automation doesn't work:
1. Open GitHub Project
2. Drag & drop card to the appropriate column
3. Update status in Trello too

---

## 🐛 Common Issues & Solutions

### Issue: "You need to resolve your current index first"

**Solution:**
```bash
git stash
git pull origin main
git stash pop
```

### Issue: "Permission denied (publickey)"

**Solution:**
1. Regenerate SSH key
2. Add to GitHub
3. Test: `ssh -T git@github.com`

### Issue: "Changes not staged for commit"

**Solution:**
```bash
git add .
git commit -m "fix: your commit message"
```

### Issue: Wrong branch

**Solution:**
```bash
# Stash changes
git stash

# Checkout correct branch
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
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
