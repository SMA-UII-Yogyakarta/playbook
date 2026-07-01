# User Story Template

> Template for Product Analyst writing user stories.

---

## 📝 Template

```markdown
## User Story

**ID:** SMART-001  
**Title:** [Short title]  
**Priority:** High/Medium/Low  
**Sprint:** [Sprint number]

---

### Story

**As a** [role/user]  
**I want** [feature/capability]  
**So that** [benefit/business value]

---

### Acceptance Criteria

#### Functional
- [ ] Criterion 1 (specific, testable)
- [ ] Criterion 2 (specific, testable)
- [ ] Criterion 3 (specific, testable)

#### Non-Functional
- [ ] Performance: Load time < 2 seconds
- [ ] Security: [security requirement]
- [ ] UX: Responsive on mobile & desktop

---

### Business Rules

1. Rule 1
2. Rule 2
3. Rule 3

---

### Edge Cases

- Scenario 1: [Handling]
- Scenario 2: [Handling]

---

### Mockup/Wireframe

[Attach link to Figma/Excalidraw/screenshot]

---

### Dependencies

- [ ] Dependency 1 (link to card/issue)
- [ ] Dependency 2

---

### Out of Scope

- Features NOT included in this story:
  - Item 1
  - Item 2
```

---

## 📖 Examples

### Example 1: Login Feature

```markdown
## User Story

**ID:** SMART-001  
**Title:** Login with Email & Password  
**Priority:** High  
**Sprint:** 1

---

### Story

**As a** teacher or staff of SMA UII  
**I want** to login with email and password  
**So that** I can access the SMART Absen system

---

### Acceptance Criteria

#### Functional
- [ ] User can login with valid email & password
- [ ] User sees error "Email or password is wrong" if credentials invalid
- [ ] User sees validation error if email is empty
- [ ] User sees validation error if password is empty
- [ ] User is redirected to dashboard after successful login
- [ ] User can logout

#### Non-Functional
- [ ] Login page load < 2 seconds
- [ ] Password hashed in database (bcrypt)
- [ ] Session timeout after 2 hours of inactivity
- [ ] Responsive on mobile & desktop

---

### Business Rules

1. Password minimum 8 characters
2. Password must contain letters & numbers
3. User can reset password via email
4. Login failed 5x → account locked for 15 minutes

---

### Edge Cases

- Email not registered: Show generic error "Email or password is wrong"
- Forgot password: Link to reset password page
- Session expired: Redirect to login with message

---

### Mockup/Wireframe

[Link to Figma]

---

### Dependencies

- [ ] Database schema users (Issue #1)
- [ ] Sanctum authentication setup (Issue #2)

---

### Out of Scope

- Google SSO login (Sprint 3)
- NIP login (Sprint 2)
```

---

### Example 2: Student Attendance

```markdown
## User Story

**ID:** SMART-012  
**Title:** Student Attendance with Geolocation & Selfie  
**Priority:** High  
**Sprint:** 2

---

### Story

**As a** SMA UII student  
**I want** to do attendance with geolocation and selfie  
**So that** my attendance is recorded validly

---

### Acceptance Criteria

#### Functional
- [ ] Student can see attendance form on dashboard
- [ ] Form shows camera preview for selfie
- [ ] Form auto-detects geolocation (latitude, longitude)
- [ ] Attendance submission succeeds if geolocation within 50m radius of school
- [ ] Attendance submission fails if geolocation is outside radius
- [ ] Selfie must be captured before submit
- [ ] Attendance can only be done 1x per day
- [ ] Student can view their own attendance history

#### Non-Functional
- [ ] Camera load < 3 seconds
- [ ] Geolocation detect < 5 seconds
- [ ] Attendance submit < 2 seconds
- [ ] Photo stored in object storage (S3)
- [ ] Responsive on mobile (because students use phones)

---

### Business Rules

1. Attendance radius: 50 meters from school coordinates (-7.7956, 110.3695)
2. Attendance time: 06:00 - 07:30 WIB (ontime), after that late
3. Duplicate attendance: Rejected with message "You have already submitted attendance today"
4. Photo: Min 640x480, max 2MB, format JPG/PNG
5. Geolocation: Must be enabled, otherwise show error

---

### Edge Cases

- GPS inaccurate (accuracy > 100m): Show warning "Low GPS accuracy, try in an open area"
- Camera not accessible: Show error "Camera access denied, please allow camera access in browser"
- Slow internet: Show loading spinner with 30 seconds timeout
- Submit failed: Auto retry max 3x

---

### Mockup/Wireframe

[Link to Figma]

---

### Dependencies

- [ ] Authentication module (SMART-001) ✅
- [ ] Geolocation API (Issue #15)
- [ ] Camera API (Issue #16)
- [ ] Object Storage setup (Issue #10)

---

### Out of Scope

- Attendance without internet (offline mode) — Sprint 4
- Face recognition — Sprint 5
- Attendance via WhatsApp bot — Backlog
```

---

## 💡 Writing Tips

### Good User Story Characteristics (INVEST)

```
I - Independent (can be developed separately)
N - Negotiable (can be negotiated)
V - Valuable (has business value)
E - Estimable (can be estimated)
S - Small (can be completed in 1 sprint)
T - Testable (can be tested)
```

---

### Acceptance Criteria: Gherkin Format

```gherkin
Feature: Login
  Scenario: Login with valid credentials
    Given user is on the login page
    When user input email "admin@smauiiyk.sch.id"
    And user input password "Admin123!"
    And user clicks "Login" button
    Then user is redirected to dashboard
    And user sees welcome message "Welcome, Admin"

  Scenario: Login with invalid credentials
    Given user is on the login page
    When user input email "wrong@email.com"
    And user input password "wrongpass"
    And user clicks "Login" button
    Then user sees error "Email or password is wrong"
    And user stays on login page
```

---

### Common Mistakes

**Bad:**
```
As a user
I want to login
So that I can use the app
```

**Good:**
```
As a SMA UII teacher
I want to login with email & password
So that I can access SMART Absen to manage attendance
```

---

**Next:** [`github-issue.md`](github-issue.md)  
**Last Updated:** June 2026  
**Maintained by:** Ahmad Hanif
