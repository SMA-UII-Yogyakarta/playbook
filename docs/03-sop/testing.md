# Testing SOP

> Standar testing untuk SMART Absen SMA UII.

---

## 🎯 Testing Pyramid

```
        /\
       /  \
      / E2E \      Manual Testing (UAT)
     /--------\
    /  \    /  \
   /    \  /    \
  / Integration  \   Integration Test (API)
 /----------------\
/    \        /    \
|      \      /      |
|       \    /       |
|  Unit Test (PHPUnit) |
|----------------------|
```

**Strategy:**
- **70% Unit Test** — Fast, cheap, isolated
- **20% Integration Test** — API endpoint, database
- **10% E2E Test** — Critical user journey

---

## 🧪 Unit Testing (PHPUnit)

### Test Location

```
tests/
├── Unit/
│   ├── Models/
│   │   ├── AttendanceTest.php
│   │   ├── UserTest.php
│   │   └── StudentTest.php
│   ├── Services/
│   │   ├── AttendanceServiceTest.php
│   │   └── GeolocationServiceTest.php
│   └── Validators/
│       └── PresensiValidatorTest.php
│
└── Feature/
    ├── Auth/
    │   └── LoginTest.php
    ├── Attendance/
    │   ├── CreateAttendanceTest.php
    │   └── AttendanceValidationTest.php
    └── Report/
        └── ExportReportTest.php
```

---

### Test Structure

```php
<?php

namespace Tests\Unit\Models;

use App\Models\Attendance;
use App\Models\Student;
use Tests\TestCase;

class AttendanceTest extends TestCase
{
    /** @test */
    public function it_can_create_attendance()
    {
        // Arrange
        $student = Student::factory()->create();
        $data = [
            'student_id' => $student->id,
            'date' => now()->toDateString(),
            'in_time' => '07:00:00',
            'latitude' => -7.7956,
            'longitude' => 110.3695,
        ];

        // Act
        $attendance = Attendance::create($data);

        // Assert
        $this->assertDatabaseHas('attendances', [
            'student_id' => $student->id,
            'date' => now()->toDateString(),
        ]);
    }

    /** @test */
    public function it_prevents_duplicate_attendance()
    {
        // Arrange
        $student = Student::factory()->create();
        Attendance::create([
            'student_id' => $student->id,
            'date' => now()->toDateString(),
            'in_time' => '07:00:00',
        ]);

        // Act & Assert
        $this->expectException(\Illuminate\Database\UniqueConstraintException::class);

        Attendance::create([
            'student_id' => $student->id,
            'date' => now()->toDateString(),
            'in_time' => '08:00:00',
        ]);
    }

    /** @test */
    public function it_calculates_status_correctly()
    {
        // Arrange
        $attendance = Attendance::factory()->make([
            'in_time' => '07:30:00',
        ]);

        // Assert
        $this->assertEquals('on_time', $attendance->status);
    }
}
```

---

### Testing Best Practices

**Do's ✅**
```php
// Test naming: descriptive
public function test_user_cannot_login_with_invalid_password()

// Arrange-Act-Assert pattern
// One assertion per test (ideal)
// Factory untuk data creation
// Mock external services
```

**Don'ts ❌**
```php
// Bad naming
public function test_login()

// Multiple assertions tanpa context
// Hardcoded data
// Test yang depend on order
```

---

## 🔌 Integration Testing

### API Endpoint Test

```php
<?php

namespace Tests\Feature\Attendance;

use App\Models\User;
use Laravel\Sanctum\Sanctum;
use Tests\TestCase;

class CreateAttendanceTest extends TestCase
{
    /** @test */
    public function authenticated_user_can_submit_attendance()
    {
        // Arrange
        $user = User::factory()->create();
        Sanctum::actingAs($user);

        $payload = [
            'latitude' => -7.7956,
            'longitude' => 110.3695,
            'photo' => 'base64_encoded_image',
        ];

        // Act
        $response = $this->postJson('/api/attendance', $payload);

        // Assert
        $response->assertStatus(201)
            ->assertJson([
                'message' => 'Attendance submitted successfully',
                'status' => 'on_time',
            ]);

        $this->assertDatabaseHas('attendances', [
            'user_id' => $user->id,
            'date' => now()->toDateString(),
        ]);
    }

    /** @test */
    public function unauthenticated_user_cannot_submit_attendance()
    {
        // Act
        $response = $this->postJson('/api/attendance', []);

        // Assert
        $response->assertStatus(401);
    }

    /** @test */
    public function attendance_requires_valid_coordinates()
    {
        // Arrange
        $user = User::factory()->create();
        Sanctum::actingAs($user);

        $payload = [
            'latitude' => null,
            'longitude' => null,
        ];

        // Act
        $response = $this->postJson('/api/attendance', $payload);

        // Assert
        $response->assertStatus(422)
            ->assertJsonValidationErrors(['latitude', 'longitude']);
    }
}
```

---

## 🎭 End-to-End (E2E) Testing

### Critical User Journey

```php
<?php

namespace Tests\E2E;

use App\Models\Student;
use Laravel\Dusk\Browser;
use Laravel\Dusk\TestCase as DuskTestCase;

class StudentAttendanceTest extends DuskTestCase
{
    /** @test */
    public function student_can_submit_attendance()
    {
        $student = Student::factory()->create();

        $this->browse(function (Browser $browser) use ($student) {
            $browser->visit('/login')
                ->type('email', $student->email)
                ->type('password', 'password')
                ->press('Login')
                ->waitForLocation('/dashboard')
                ->clickLink('Presensi')
                ->waitForLocation('/attendance')
                ->assertSee('Form Presensi')
                ->script('navigator.geolocation.getCurrentPosition(function(p) { window.testLat = p.coords.latitude; window.testLng = p.coords.longitude; })')
                ->pause(1000)
                ->press('Kirim Presensi')
                ->waitForText('Presensi berhasil')
                ->assertSee('Presensi berhasil dikirim');
        });
    }
}
```

---

## 📊 Test Coverage Requirements

### Minimum Coverage

| Component | Coverage | Critical Files |
|---|---|---|
| **Models** | 80% | Attendance, User, Student |
| **Services** | 90% | AttendanceService, AuthService |
| **Controllers** | 70% | AttendanceController, AuthController |
| **Validators** | 95% | PresensiValidator, GeolocationValidator |
| **Overall** | > 70% | All app code |

---

### Coverage Check

```bash
# Run test dengan coverage
php artisan test --coverage

# Coverage minimum 70%
# Fail jika dibawah 70%
```

**phpunit.xml:**
```xml
<coverage>
    <include>
        <directory suffix=".php">./app</directory>
    </include>
    <report>
        <html outputDirectory="coverage-report"/>
    </report>
    <threshold>
        <low>70</low>
        <high>90</high>
    </threshold>
</coverage>
```

---

## 🧪 Manual Testing (UAT)

### UAT Checklist

**PIC:** Ahmad Hanif

```markdown
## Authentication Module

### Login
- [ ] Login dengan email & password valid
- [ ] Login dengan email invalid (show error)
- [ ] Login dengan password invalid (show error)
- [ ] Login dengan empty field (show validation)
- [ ] Remember me functionality
- [ ] Logout

### Dashboard
- [ ] Dashboard loads setelah login
- [ ] Statistik correct (hadir, sakit, izin, alfa)
- [ ] Menu accessible sesuai role
```

```markdown
## Presensi Module

### Student Attendance
- [ ] Form presensi accessible
- [ ] Camera preview working
- [ ] Geolocation detected
- [ ] Submit presensi berhasil
- [ ] Duplicate presensi prevented
- [ ] Outside radius prevented
- [ ] Photo saved to storage
- [ ] Riwayat presensi tampil
```

---

### UAT Sign-off Template

```markdown
## UAT Sign-off

**Feature:** Presensi Siswa  
**Version:** v1.0.0  
**Date:** 24 Juni 2026  
**Tester:** Ahmad Hanif

### Test Results

| Test Case | Expected | Actual | Status |
|---|---|---|---|
| Login valid | Success | Success | ✅ |
| Login invalid | Error | Error | ✅ |
| Submit presensi | Success | Success | ✅ |
| Duplicate presensi | Error | Error | ✅ |

### Issues Found

| Severity | Description | Status |
|---|---|---|
| Critical | None | - |
| Major | Camera slow loading | Open |
| Minor | UI alignment | Open |

### Decision

✅ **APPROVED** for production  
❌ **REJECTED** — Fix critical issues first

**Notes:**
Fix major & minor issues di Sprint berikutnya.
Critical issues: None.

**Signature:**
Ahmad Hanif
Product Analyst
```

---

## 🔄 Testing Workflow

```
1. Developer tulis code
   ↓
2. Developer tulis unit test
   ↓
3. Run test locally (php artisan test)
   ↓
4. Test hijau → Commit
   ↓
5. Push → CI run test (GitHub Actions)
   ↓
6. CI hijau → Code review
   ↓
7. Code review approved → Merge
   ↓
8. Deploy staging → UAT
   ↓
9. UAT passed → Deploy production
```

---

## 🛠️ Testing Tools

### PHPUnit (Unit & Integration)

```bash
# Install (already included in Laravel)
composer require --dev phpunit/phpunit

# Run all tests
php artisan test

# Run specific test
php artisan test --filter AttendanceTest

# Run with coverage
php artisan test --coverage

# Run specific file
php artisan test tests/Feature/AttendanceTest.php
```

---

### Laravel Dusk (E2E)

```bash
# Install
composer require --dev laravel/dusk
php artisan dusk:install

# Run tests
php artisan dusk

# Run specific test
php artisan dusk --filter StudentAttendanceTest
```

---

### Factory Bot (Test Data)

```php
// database/factories/AttendanceFactory.php
class AttendanceFactory extends Factory
{
    public function definition()
    {
        return [
            'student_id' => Student::factory(),
            'date' => now()->toDateString(),
            'in_time' => '07:00:00',
            'latitude' => $this->faker->latitude(-8, -7),
            'longitude' => $this->faker->longitude(110, 111),
            'status' => 'on_time',
        ];
    }
}

// Usage
$attendance = Attendance::factory()->create();
$attendances = Attendance::factory()->count(10)->create();
```

---

## 🐛 Bug Reporting

### Bug Report Template

```markdown
## Bug Report

**Title:** Presensi gagal submit saat geolokasi null

**Severity:** Critical

**Environment:** Production

**Steps to Reproduce:**
1. Login sebagai siswa
2. Klik menu Presensi
3. Disable GPS di browser
4. Klik "Kirim Presensi"

**Expected Result:**
Show error "Geolokasi wajib diaktifkan"

**Actual Result:**
Error 500, page crash

**Screenshot:**
[Attach screenshot]

**Browser:** Chrome 114.0  
**OS:** Windows 11  
**Device:** Desktop

**Reported by:** Ahmad Hanif  
**Date:** 24 Juni 2026
```

---

## 📈 Testing Metrics

### Per Sprint

```
- Total tests: 150
- New tests: 25
- Test coverage: 75%
- Bug found in staging: 5
- Bug found in production: 0
```

### Per Developer

```
- Tests written: 30
- Code coverage: 80%
- Bug rate: < 5%
```

---

## 🎓 Testing for Junior Developers

### Week 1-2: Write Simple Test

```php
/** @test */
public function it_can_create_user()
{
    $user = User::factory()->create();
    $this->assertDatabaseHas('users', ['email' => $user->email]);
}
```

### Week 3-4: Test Validation

```php
/** @test */
public function email_is_required()
{
    $response = $this->post('/login', ['password' => 'secret']);
    $response->assertSessionHasErrors('email');
}
```

### Week 5-6: Test API

```php
/** @test */
public function authenticated_user_can_access_api()
{
    Sanctum::actingAs($user);
    $response = $this->getJson('/api/user');
    $response->assertStatus(200);
}
```

### Week 7-8: Mock External Services

```php
/** @test */
public function it_sends_sms_after_attendance()
{
    $smsMock = Mockery::mock(SmsService::class);
    $smsMock->shouldReceive('send')->once();

    $this->app->instance(SmsService::class, $smsMock);

    // Test logic
}
```

---

## 📚 Resources

- [Laravel Testing Documentation](https://laravel.com/docs/testing)
- [PHPUnit Documentation](https://phpunit.de/documentation.html)
- [Laravel Dusk](https://laravel.com/docs/dusk)
- [Testing Laravel](https://testing-laravel.com/)

---

**Next:** [`incident-response.md`](incident-response.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev