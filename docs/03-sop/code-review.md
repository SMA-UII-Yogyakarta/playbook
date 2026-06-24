# Code Review SOP

> Standar code review untuk tim engineering SMA UII Yogyakarta.

---

## 🎯 Purpose

Code review bukan sekadar mencari bug. Code review adalah:
- Knowledge sharing
- Quality assurance
- Best practice enforcement
- Mentoring opportunity

**Goal:** Setiap PR membuat codebase lebih baik dan developer lebih pintar.

---

## 👥 Roles & Responsibilities

### Reviewer (Sandikodev)

**Responsibilities:**
- Review PR dalam 24 jam
- Berikan feedback spesifik & actionable
- Approve atau Request Changes
- Ensure coding standard
- Check security & performance

**Time Allocation:** 20% dari total waktu kerja

---

### Author (Fathan/Ihsan)

**Responsibilities:**
- Self-review sebelum submit PR
- Respond feedback dalam 24 jam
- Fix sesuai request
- Re-request review setelah fix

**Mindset:** Feedback adalah untuk code, bukan untuk person.

---

## ✅ Pre-Review Checklist (Author)

Sebelum request review, pastikan:

```markdown
## Self-Review Checklist

### Code Quality
- [ ] No `console.log()`, `dd()`, `var_dump()`
- [ ] No commented-out code
- [ ] No TODO tanpa Issue link
- [ ] Follow Laravel conventions
- [ ] PSR-12 compliance

### Testing
- [ ] Unit test written
- [ ] Test hijau (php artisan test)
- [ ] Manual test done
- [ ] Screenshot attached (jika UI change)

### Documentation
- [ ] PR description lengkap
- [ ] Related Issue linked (Fixes #12)
- [ ] API documentation updated (jika ada)
- [ ] CHANGELOG updated (jika perlu)

### Security
- [ ] No hardcoded credentials
- [ ] Input validation added
- [ ] SQL injection prevented (Eloquent used)
- [ ] XSS prevented (escape output)
- [ ] CSRF token present (form)

### Performance
- [ ] No N+1 query (eager loading used)
- [ ] Database index added (jika perlu)
- [ ] Heavy operation queued (jika ada)
```

---

## 🔍 Review Checklist (Reviewer)

### 1. Code Quality (Bobot: 30%)

```markdown
## Code Quality Review

### Readability
- [ ] Variable naming jelas
- [ ] Function tidak terlalu panjang (< 50 baris ideal)
- [ ] Class tidak terlalu besar (< 500 baris ideal)
- [ ] Consistent formatting

### Laravel Conventions
- [ ] Controller: thin controller (logic di Model/Service)
- [ ] Model: Eloquent relationship defined
- [ ] Validation: Form Request class used
- [ ] Naming: camelCase, snake_case sesuai konvensi

### DRY (Don't Repeat Yourself)
- [ ] No duplicate code
- [ ] Reusable logic extracted to method/class
```

**Contoh Comment:**
```
💡 Suggestion: Function ini 80 baris, bisa dipecah jadi:
- validateInput()
- processAttendance()
- saveToDatabase()

Lebih mudah test & maintain.
```

---

### 2. Functionality (Bobot: 25%)

```markdown
## Functionality Review

### Requirement Match
- [ ] Code sesuai requirement (cek Issue link)
- [ ] Acceptance criteria terpenuhi
- [ ] Edge case handled (null, empty, error)

### Logic Correctness
- [ ] Business logic benar
- [ ] Conditional logic tepat
- [ ] Loop tidak infinite
- [ ] Error handling adequate
```

**Contoh Comment:**
```
❓ Question: Di requirement disebut "presensi hanya 1x per hari".
Apakah sudah ada validasi untuk cek presensi duplicate di hari yang sama?

Cek di: Attendance.php line 45
```

---

### 3. Security (Bobot: 20%) ⚠️ CRITICAL

```markdown
## Security Review

### Input Validation
- [ ] All user input validated
- [ ] Type validation (integer, string, email)
- [ ] Length validation (max, min)
- [ ] Format validation (regex)

### Authentication & Authorization
- [ ] Auth middleware present
- [ ] Policy/ability check untuk resource access
- [ ] No hard-coded user ID

### Common Vulnerabilities
- [ ] SQL Injection: Eloquent used (no raw query)
- [ ] XSS: Output escaped ({{ }} di Blade)
- [ ] CSRF: Token present di form
- [ ] Mass Assignment: $fillable/$guarded defined
```

**Contoh Comment:**
```
🚨 Security Issue:
Line 23: User::find($request->id)

Ini vulnerable karena ID dari user input tanpa validasi.

Fix:
1. Validate: 'id' => 'required|integer|exists:users,id'
2. Authorization: check if user has permission to access this ID
```

---

### 4. Performance (Bobot: 15%)

```markdown
## Performance Review

### Database
- [ ] No N+1 query (with() used)
- [ ] Index added untuk frequently queried column
- [ ] Select specific columns (no select *)

### Caching
- [ ] Heavy query cached (Cache::remember)
- [ ] Config cached (env() only di config file)

### Queue
- [ ] Heavy operation queued (email, report, export)
- [ ] Timeout set untuk long-running task
```

**Contoh Comment:**
```
⚡ Performance:
Line 67: Loop 100x dengan query di dalam loop

Before:
foreach ($students as $student) {
    $attendance = Attendance::where('student_id', $student->id)->first();
}

After (Eager Loading):
$attendances = Attendance::whereIn('student_id', $studentIds)->get();
```

---

### 5. Testing (Bobot: 10%)

```markdown
## Testing Review

### Unit Test
- [ ] Test file created
- [ ] Test coverage > 70%
- [ ] Edge case tested
- [ ] Test naming clear

### Manual Test
- [ ] Screenshot attached (UI change)
- [ ] API tested (Postman/Insomnia)
- [ ] No regression
```

**Contoh Comment:**
```
✅ Test:
Test coverage bagus (85%).

Suggestion: Tambah test untuk edge case:
- Student presensi 2x di hari yang sama
- Geolokasi outside radius
```

---

## 📝 Review Feedback Format

### Use Standard Labels

```
❌ Critical Issue — Harus fix sebelum merge
⚠️  Major Issue — Penting, tapi bisa diskusi
💡 Suggestion — Improvement, tidak wajib
✅ Approved — Tidak ada issue
❓ Question — Perlu clarification
```

### Be Specific

**Buruk:**
```
"This code is bad, fix it."
```

**Baik:**
```
"💡 Suggestion di AttendanceController.php line 45:

Function processAttendance() terlalu panjang (80 baris).
Bisa dipecah jadi validateInput(), calculateStatus(), saveToDatabase().

Referensi: https://laravel.com/docs/controllers#controller-best-practices"
```

### Be Kind

**Buruk:**
```
"Kenapa pakai query builder? Harus Eloquent!"
```

**Baik:**
```
"❓ Question: Ada pertimbangan khusus pakai query builder di sini?

Kalau tidak ada, mungkin kita bisa pakai Eloquent untuk consistency:

Attendance::create([...])

vs

DB::table('attendances')->insert([...])"
```

---

## 🔄 Review Process Flow

```
1. Author buat PR
   ↓
2. GitHub notify Reviewer
   ↓
3. Reviewer review (max 24 jam)
   ↓
4a. Request Changes          4b. Approve
    ↓                           ↓
    Author fix                 Merge
    ↓
    Re-request review
    ↓
    Back to step 3
```

### Timeline SLA

| Step | SLA | Owner |
|---|---|---|
| PR dibuat → Review start | < 24 jam | Reviewer |
| Review → Feedback | < 24 jam | Reviewer |
| Feedback → Fix | < 24 jam | Author |
| Fix → Re-review | < 24 jam | Reviewer |

**Total:** Max 4 hari untuk PR merge (ideal < 2 hari)

---

## 🚦 Review Decision

### Approve ✅

**Criteria:**
- No critical issue
- No major security issue
- Test coverage adequate
- Code quality acceptable

**Action:**
- Click "Approve"
- Merge (squash merge default)

---

### Request Changes ❌

**Criteria:**
- Ada critical bug
- Ada security vulnerability
- Test coverage < 70%
- Code quality tidak acceptable

**Action:**
- Click "Request Changes"
- Comment detail issue
- Tag author

---

### Comment Only 💬

**Criteria:**
- Ada suggestion improvement
- Tidak blocking merge
- Nice to have

**Action:**
- Comment tanpa request changes
- Author decide apakah fix sekarang atau nanti

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
return $user->name; // Error jika null
```

**Fix:**
```php
// Good
$user = User::findOrFail($id); // 404 jika tidak ada
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
- Review time (jam)
- Comment count
- Iteration count (berapa kali fix)
- Time to merge (jam)
```

### Per Sprint

```
- Total PR reviewed
- Average review time
- Critical issues found
- Security issues found
```

### Per Developer

```
- PR submitted
- Average iteration count
- Code quality trend
```

---

## 🎓 Learning from Review

### Untuk Junior Developer

Setiap review comment adalah kesempatan belajar:

1. **Baca dokumentasi** yang di-link reviewer
2. **Tanya "kenapa"** jika tidak paham
3. **Fix dengan paham**, bukan copy-paste
4. **Catat pattern** yang sering dikomentari

### Untuk Reviewer

Setiap review adalah teaching moment:

1. **Jelaskan "kenapa"**, bukan hanya "apa"
2. **Link dokumentasi** untuk reference
3. **Give example** code, bukan hanya teori
4. **Praise good code** juga, bukan hanya critique

---

## 🏆 Code Review Best Practices

### Do's ✅

- ✅ Review dalam 24 jam
- ✅ Feedback spesifik dengan line reference
- ✅ Explain "kenapa", bukan hanya "apa"
- ✅ Link dokumentasi
- ✅ Praise good code
- ✅ Use conventional comment labels (❌, ⚠️, 💡, ✅)
- ✅ Test code locally jika kompleks

### Don'ts ❌

- ❌ Review > 24 jam (bottleneck)
- ❌ Vague comment ("fix this")
- ❌ Personal attack ("this is bad code")
- ❌ Nitpick semua (prioritize)
- ❌ Merge tanpa review
- ❌ Skip test check
- ❌ Assume author tahu (explain context)

---

## 📚 Resources

- [Laravel Contribution Guide](https://laravel.com/docs/contributions)
- [Code Review Best Practices](https://google.github.io/eng-practices/review/)
- [PSR-12 Coding Style](https://www.php-fig.org/psr/psr-12/)

---

**Next:** [`deployment.md`](deployment.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev