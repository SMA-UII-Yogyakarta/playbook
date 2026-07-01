# Environment Setup — Development

> Development environment setup guide for SMART Absen SMA UII.

**OS:** Windows 10/11  
**Stack:** Laragon 6.0, PHP 8.4, PostgreSQL 16, Node.js 20+, Bun

---

## 📋 Prerequisites

### Required Software

| Software | Version | Download |
|---|---|---|
| **Laragon** | 6.0 | [laragon.org](https://laragon.org/download/) — choose the **Full** version |
| **PHP** | 8.4 NTS | Included in Laragon |
| **Composer** | 2.x | [getcomposer.org](https://getcomposer.org/download/) |
| **Bun** | latest | `powershell -c "irm bun.sh/install.ps1 | iex"` |
| **Git** | Latest | [git-scm.com](https://git-scm.com/) |
| **VS Code** | Latest | [code.visualstudio.com](https://code.visualstudio.com/) |
| **pgAdmin / DBeaver** | Latest | GUI tools for PostgreSQL |

---

## 🚀 Step-by-Step Setup

### 1. Install Laragon

1. Download Laragon 6.0 (**Full** version recommended)
2. Install at `C:\laragon`
3. Start Laragon
4. Click **Preferences** → Ensure:
   - PHP Version: 8.4 NTS
   - Apache: Enabled
   - PostgreSQL: Add manually (see documentation)

### 2. Setup PostgreSQL in Laragon

PostgreSQL is not included by default in Laragon. Follow these steps:

1. Download PostgreSQL 16 zip from [EnterpriseDB](https://www.enterprisedb.com/download-postgresql-binaries)
2. Extract to `C:\laragon\bin\postgresql\postgresql-16.x-winx64\`
3. Open Laragon > Menu > Tools > Service/Port > PostgreSQL
4. Initialize the database cluster:
   ```bash
   "C:\laragon\bin\postgresql\postgresql-16.x-winx64\bin\initdb.exe" -D "C:/laragon/data/postgresql-16" --username=postgres
   ```
5. Start PostgreSQL from Laragon

Or use **NeonDB** directly for development — register at [neon.tech](https://neon.tech) and create a new project.

### 3. Install Bun (Package Manager)

Bun is used as the package manager for the frontend (replacing npm).

```bash
# Install via PowerShell (Admin recommended)
powershell -c "irm bun.sh/install.ps1 | iex"

# Verify
bun --version
```

### 4. Install Composer

1. Download Composer Setup from [getcomposer.org](https://getcomposer.org/download/)
2. Install with default settings
3. Test in terminal:
   ```bash
   composer --version
   ```

### 5. Install Git & Setup SSH

1. Download Git for Windows from [git-scm.com](https://git-scm.com/)
2. Install with default settings
3. Setup SSH Key:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   cat ~/.ssh/id_ed25519.pub
   ```
4. Add to GitHub:
   - Open [github.com/settings/keys](https://github.com/settings/keys)
   - Click **New SSH Key**
   - Paste the contents of `id_ed25519.pub`
   - Save
5. Test connection:
   ```bash
   ssh -T git@github.com
   ```

### 6. Install VS Code Extensions

Open VS Code → Extensions → Install:

| Extension | Publisher | Purpose |
|---|---|---|
| **PHP Intelephense** | Ben Mewburn | PHP IntelliSense |
| **Tailwind CSS IntelliSense** | Brad Cornes | Tailwind autocomplete |
| **Prettier** | Prettier | Code formatter |
| **GitLens** | GitKraken | Git blame, history |
| **Thunder Client** | Ranga Vadhineni | API testing |

---

## 📁 Clone & Setup Project

### 1. Clone Core (Backend + Frontend)

```bash
cd C:\laragon\www
git clone git@github.com:SMA-UII-Yogyakarta/core.git smauii-core
cd smauii-core
```

### 2. Setup Environment

```bash
# Copy .env example
copy .env.example .env

# Generate APP_KEY
php artisan key:generate

# Install PHP dependencies
composer install

# Install frontend dependencies (via Bun, not npm!)
bun install
```

### 3. Setup Database

**Option A — Local PostgreSQL (Laragon):**
```bash
# Create database via psql or pgAdmin
psql -U postgres -c "CREATE DATABASE smauii_core;"
```

Edit `.env`:
```env
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=smauii_core
DB_USERNAME=postgres
DB_PASSWORD=
```

**Option B — NeonDB (Cloud):**
1. Register at [neon.tech](https://neon.tech)
2. Create a project → get connection string
3. Edit `.env`:
```env
DB_CONNECTION=pgsql
DB_HOST=ep-xxx-xxxx.us-east-2.aws.neon.tech
DB_PORT=5432
DB_DATABASE=smauii_dev
DB_USERNAME=smauii_owner
DB_PASSWORD=xxxxxx
DB_SSLMODE=require
```

### 4. Install Additional Packages

```bash
# Laravel Sanctum (auth)
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"

# Spatie Laravel Permission (RBAC)
composer require spatie/laravel-permission
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
```

### 5. Migration & Seeder

```bash
# Run migration
php artisan migrate

# Run seeder
php artisan db:seed
```

### 6. Run Development Server

```bash
# Terminal 1: Vite dev server (frontend hot reload)
bun run dev

# Terminal 2: Laravel dev server
php artisan serve

# Or via Laragon → auto start at http://smauii-core.test
```

---

## 🔧 Configuration

### PHP Configuration (`php.ini`)

Location: `C:\laragon\bin\php\php-8.4.22-nts-Win32-vs17-x64\php.ini`

```ini
; Timezone
date.timezone = "Asia/Jakarta"

; Memory Limit
memory_limit = 512M

; Upload Max
upload_max_filesize = 10M
post_max_size = 10M

; Extensions (ensure enabled)
extension=pdo_pgsql
extension=pgsql
extension=mbstring
extension=openssl
extension=curl
extension=fileinfo
```

### Apache Virtual Host

Laragon auto-generates virtual hosts. Ensure:

```
DocumentRoot: C:\laragon\www\smauii-core\public
Server Name: smauii-core.test
```

---

## ✅ Verification Checklist

### Backend

```bash
# Check PHP version
php --version
# Expected: PHP 8.4

# Check Composer
composer --version

# Check Laravel
php artisan --version

# Check database connection
php artisan migrate:status

# Run test
php artisan test
```

### Frontend

```bash
# Check Bun version
bun --version

# Build assets
bun run build

# Development server
bun run dev
```

### Git

```bash
# Check Git version
git --version

# Check SSH connection
ssh -T git@github.com
# Expected: Hi <username>! You've successfully authenticated...
```

---

## 🐛 Troubleshooting

| Problem | Solution |
|---|---|
| **PostgreSQL connection refused** | Make sure PostgreSQL is running in Laragon (Menu > Tools > Service/Port > PostgreSQL) |
| **pdo_pgsql not found** | Check `php -m` — ensure `pdo_pgsql` and `pgsql` are present. Add `extension=pdo_pgsql` to php.ini if not |
| **Port 5432 already in use** | Check other applications using the PostgreSQL port. Change port in `.env` if needed |
| **Composer install fails** | `composer clear-cache && composer update --no-cache` |
| **Bun install error** | Run PowerShell as Administrator. Or install via npm: `npm install -g bun` |
| **Permission denied (storage/)** | `icacls storage /grant Users:(OI)(CI)F /T` (PowerShell Admin) |
| **APP_KEY not set** | `php artisan key:generate` |

---

## 📚 Next Steps

After environment setup:

1. [ ] Read [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)
2. [ ] Read [`onboarding.md`](onboarding.md) for complete checklist
3. [ ] Take first task from GitHub Project
4. [ ] Create first branch
5. [ ] Start coding!

---

**Last Updated:** 2026-06-30  
**Maintained by:** Sandikodev
