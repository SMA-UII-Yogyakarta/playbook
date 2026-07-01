# Code Review SOP

> Code review standards for the SMA UII Yogyakarta engineering team.

---

## 🎯 Purpose

Code review is not just about finding bugs. Code review is:
- Knowledge sharing
- Quality assurance
- Best practice enforcement
- Mentoring opportunity

**Goal:** Every PR makes the codebase better and the developer smarter.

---

## 👥 Roles & Responsibilities

### Reviewer (Sandikodev)

**Responsibilities:**
- Review PR within 24 hours
- Provide specific & actionable feedback
- Approve or Request Changes
- Ensure coding standard
- Check security & performance

**Time Allocation:** 20% of total work time

---

### Author (Fathan/Ihsan)

**Responsibilities:**
- Self-review before submitting PR (check TypeScript compile, lint, test)
- Respond to feedback within 24 hours
- Fix as requested
- Re-request review after fix

### Initial Reviewer (Azis — Learning Mentor)

**Responsibilities:**
- Initial review before PR is sent to Sandikodev
- Check for: typos, N+1 queries, logical errors, TypeScript type issues
- Ensure self-checklist is completed
- Help fix minor issues together with author (pair programming)
- If OK → forward to Sandikodev for final review

**Mindset:** Feedback is for the code, not for the person.

---

## ✅ Pre-Review Checklist (Author)

Before requesting a review, ensure:

```markdown
## Self-Review Checklist

### Code Quality (Backend — PHP)
- [ ] No `console.log()`, `dd()`, `var_dump()`
- [ ] No commented-out code
- [ ] No TODO without Issue link
- [ ] Follow Laravel conventions
- [ ] PSR-12 compliance
- [ ] Service Layer pattern — logic in Service, thin controller

### Code Quality (Frontend — TypeScript/React)
- [ ] No `console.log()`, `debugger`
- [ ] TypeScript strict — no `any` type (unless emergency)
- [ ] Functional component with hooks (no class component)
- [ ] Props interface defined
- [ ] No unused imports/variables (ESLint clean)

### Testing (Backend)
- [ ] Unit test written (PHPUnit)
- [ ] Test green (`php artisan test`)
- [ ] Feature test for API endpoint (if any)

### Testing (Frontend)
- [ ] Jest + React Testing Library test written
- [ ] Test green (`bun run test`)
- [ ] Manual test done (browser)
- [ ] Screenshot attached (if UI change)

### Responsive Testing
- [ ] Test on mobile viewport (375px)
- [ ] Test on tablet viewport (768px)
- [ ] Test on desktop viewport (1280px+)

### Documentation
- [ ] PR description complete
- [ ] Related Issue linked (Fixes #12)
- [ ] API documentation updated (if any)
- [ ] CHANGELOG updated (if needed)

### Security
- [ ] No hardcoded credentials
- [ ] Input validation added
- [ ] SQL injection prevented (Eloquent used)
- [ ] XSS prevented (escape output)
- [ ] CSRF token present (form)

### Performance
- [ ] No N+1 query (eager loading used)
- [ ] Database index added (if needed)
- [ ] Heavy operation queued (if any)
```

---

## 🔍 Review Checklist (Reviewer)

### 1. Code Quality (Weight: 30%)

```markdown
## Code Quality Review

### Readability
- [ ] Variable naming is clear
- [ ] Function is not too long (< 50 lines ideal)
- [ ] Class is not too big (< 500 lines ideal)
- [ ] Consistent formatting

### Laravel Conventions
- [ ] Controller: thin controller (logic in Model/Service)
- [ ] Model: Eloquent relationship defined
- [ ] Validation: Form Request class used
- [ ] Service Layer: logic in `app/Services/`, thin controller
- [ ] Naming: camelCase, snake_case according to convention

### Frontend Conventions (React + TypeScript)
- [ ] TypeScript strict — no `any` type
- [ ] Functional component with hooks (no class component)
- [ ] Props interface defined & exported
- [ ] Inertia best practices (`useForm`, `usePage`) vs manual fetch
- [ ] Tailwind utility classes used (no custom CSS unless necessary)
- [ ] Component splitting — single responsibility

### DRY (Don't Repeat Yourself)
- [ ] No duplicate code
- [ ] Reusable logic extracted to method/class
```

**Example Comment:**
```
💡 Suggestion: This function is 80 lines, could be split into:
- validateInput()
- processAttendance()
- saveToDatabase()

Easier to test & maintain.
```

---

### 2. Functionality (Weight: 25%)

```markdown
## Functionality Review

### Requirement Match
- [ ] Code matches requirements (check Issue link)
- [ ] Acceptance criteria met
- [ ] Edge cases handled (null, empty, error)

### Logic Correctness
- [ ] Business logic is correct
- [ ] Conditional logic is accurate
- [ ] Loop is not infinite
- [ ] Error handling adequate
```

**Example Comment:**
```
❓ Question: The requirement says "attendance only 1x per day".
Is there validation to check for duplicate attendance on the same day?

Check at: Attendance.php line 45
```

---

### 3. Security (Weight: 20%) ⚠️ CRITICAL

```markdown
## Security Review

### Input Validation
- [ ] All user input validated
- [ ] Type validation (integer, string, email)
- [ ] Length validation (max, min)
- [ ] Format validation (regex)

### Authentication & Authorization
- [ ] Auth middleware present
- [ ] Policy/ability check for resource access
- [ ] No hard-coded user ID

### Common Vulnerabilities
- [ ] SQL Injection: Eloquent used (no raw query)
- [ ] XSS: Output escaped ({{ }} in Blade)
- [ ] CSRF: Token present in form
- [ ] Mass Assignment: $fillable/$guarded defined
```

**Example Comment:**
```
🚨 Security Issue:
Line 23: User::find($request->id)

This is vulnerable because the ID comes from user input without validation.

Fix:
1. Validate: 'id' => 'required|integer|exists:users,id'
2. Authorization: check if user has permission to access this ID
```

---

### 4. Performance (Weight: 15%)

```markdown
## Performance Review

### Database
- [ ] No N+1 query (with() used)
- [ ] Index added for frequently queried columns
- [ ] Select specific columns (no select *)

### Caching
- [ ] Heavy query cached (Cache::remember)
- [ ] Config cached (env() only in config file)

### Queue
- [ ] Heavy operation queued (email, report, export)
- [ ] Timeout set for long-running tasks
```

**Example Comment:**
```
⚡ Performance:
Line 67: Loop 100x with query inside the loop

Before:
foreach ($students as $student) {
    $attendance = Attendance::where('student_id', $student->id)->first();
}

After (Eager Loading):
$attendances = Attendance::whereIn('student_id', $studentIds)->get();
```

---

### 5. Testing (Weight: 10%)

```markdown
## Testing Review

### Unit Test
- [ ] Test file created
- [ ] Test coverage > 70%
- [ ] Edge cases tested
- [ ] Test naming clear

### Manual Test
- [ ] Screenshot attached (UI change)
- [ ] API tested (Postman/Insomnia)
- [ ] No regression
```

**Example Comment:**
```
✅ Test:
Test coverage is good (85%).

Suggestion: Add tests for edge cases:
- Student checks in 2x on the same day
- Geolocation outside radius
```

---

## 📝 Review Feedback Format

### Use Standard Labels

```
❌ Critical Issue — Must fix before merge
⚠️  Major Issue — Important, but can be discussed
💡 Suggestion — Improvement, not mandatory
✅ Approved — No issues
❓ Question — Needs clarification
```

### Be Specific

**Bad:**
```
"This code is bad, fix it."
```

**Good:**
```
"💡 Suggestion at AttendanceController.php line 45:

Function processAttendance() is too long (80 lines).
Can be split into validateInput(), calculateStatus(), saveToDatabase().

Reference: https://laravel.com/docs/controllers#controller-best-practices"
```

### Be Kind

**Bad:**
```
"Kenapa pakai query builder? Harus Eloquent!"
```

**Good:**
```
"❓ Question: Any specific reason for using query builder here?

If not, maybe we could use Eloquent for consistency:

Attendance::create([...])

vs

DB::table('attendances')->insert([...])"
```

---

## 🔄 Review Process Flow

```
1. Author creates PR
   ↓
2. GitHub notifies Reviewer
   ↓
3. Reviewer reviews (max 24 hours)
   ↓
4a. Request Changes          4b. Approve
    ↓                           ↓
    Author fixes               Merge
    ↓
    Re-request review
    ↓
    Back to step 3
```

### Timeline SLA

| Step | SLA | Owner |
|---|---|---|
| PR created → Review start | < 24 hours | Reviewer |
| Review → Feedback | < 24 hours | Reviewer |
| Feedback → Fix | < 24 hours | Author |
| Fix → Re-review | < 24 hours | Reviewer |

**Total:** Max 4 days for PR merge (ideal < 2 days)

---

## 🚦 Review Decision

### Approve ✅

**Criteria:**
- No critical issues
- No major security issues
- Test coverage adequate
- Code quality acceptable

**Action:**
- Click "Approve"
- Merge (squash merge default)

---

### Request Changes ❌

**Criteria:**
- There is a critical bug
- There is a security vulnerability
- Test coverage < 70%
- Code quality not acceptable

**Action:**
- Click "Request Changes"
- Comment with detailed issue
- Tag author

---

### Comment Only 💬

**Criteria:**
- There is a suggestion for improvement
- Not blocking merge
- Nice to have

**Action:**
- Comment without requesting changes
- Author decides whether to fix now or later

---

## 🐛 Common Issues & Solutions

### Issue: N+1 Query

**Detection:**
```php
// Bad
$students = Student::all();
foreach ($students as $student) {
    $class = $student->class; // Query per loop
}
```

**Fix:**
```php
// Good
$students = Student::with('class')->get();
foreach ($students as $student) {
    $class = $student->class; // No query
}
```

---

### Issue: Mass Assignment

**Detection:**
```php
// Bad - vulnerable
User::create($request->all());
```

**Fix:**
```php
// Good - explicit fillable
User::create($request->validated());

// Or define fillable in Model
class User extends Model {
    protected $fillable = ['name', 'email', 'password'];
}
```

---

### Issue: Hardcoded Credentials

**Detection:**
```php
// Bad
$password = 'admin123';
$apiKey = 'sk-1234567890';
```

**Fix:**
```php
// Good
$password = env('ADMIN_PASSWORD');
$apiKey = config('services.api.key');
```

---

### Issue: No Error Handling

**Detection:**
```php
// Bad
$user = User::find($id);
return $user->name; // Error if null
```

**Fix:**
```php
// Good
$user = User::findOrFail($id); // 404 if not found
return $user->name;

// Or
$user = User::find($id);
if (!$user) {
    return response()->json(['error' => 'User not found'], 404);
}
```

---

## 📊 Code Review Metrics

### Per PR

```
- Review time (hours)
- Comment count
- Iteration count (how many fixes)
- Time to merge (hours)
```

### Per Sprint

```
- Total PRs reviewed
- Average review time
- Critical issues found
- Security issues found
```

### Per Developer

```
- PRs submitted
- Average iteration count
- Code quality trend
```

---

## 🎓 Learning from Review

### For Junior Developers

Every review comment is a learning opportunity:

1. **Read the documentation** linked by the reviewer
2. **Ask "why"** if you don't understand
3. **Fix with understanding**, not copy-paste
4. **Note patterns** that are frequently commented on

### For Reviewer

Every review is a teaching moment:

1. **Explain "why"**, not just "what"
2. **Link documentation** for reference
3. **Give code examples**, not just theory
4. **Praise good code** too, not just critique

---

## 🏆 Code Review Best Practices

### Do's ✅

- ✅ Review within 24 hours
- ✅ Specific feedback with line reference
- ✅ Explain "why", not just "what"
- ✅ Link documentation
- ✅ Praise good code
- ✅ Use conventional comment labels (❌, ⚠️, 💡, ✅)
- ✅ Test code locally if complex

### Don'ts ❌

- ❌ Review > 24 hours (bottleneck)
- ❌ Vague comment ("fix this")
- ❌ Personal attack ("this is bad code")
- ❌ Nitpick everything (prioritize)
- ❌ Merge without review
- ❌ Skip test check
- ❌ Assume author knows (explain context)

---

## 📚 Resources

- [Laravel Contribution Guide](https://laravel.com/docs/contributions)
- [Code Review Best Practices](https://google.github.io/eng-practices/review/)
- [PSR-12 Coding Style](https://www.php-fig.org/psr/psr-12/)

---

**Next:** [`deployment.md`](deployment.md)  
**Last Updated:** June 2026  
**Maintained by:** Sandikodev
