# Environment Setup — Development

> Panduan setup environment development untuk SMART Absen SMA UII.

**OS:** Windows 10/11  
**Stack:** Laragon 6.0, PHP 8.4, PostgreSQL 16, Node.js 20+, Bun

---

## 📋 Prerequisites

### Software Wajib

| Software | Version | Download |
|---|---|---|
| **Laragon** | 6.0 | [laragon.org](https://laragon.org/download/) — pilih versi **Full** |
| **PHP** | 8.4 NTS | Included in Laragon |
| **Composer** | 2.x | [getcomposer.org](https://getcomposer.org/download/) |
| **Bun** | latest | `powershell -c "irm bun.sh/install.ps1 | iex"` |
| **Git** | Latest | [git-scm.com](https://git-scm.com/) |
| **VS Code** | Latest | [code.visualstudio.com](https://code.visualstudio.com/) |
| **pgAdmin / DBeaver** | Latest | GUI tools untuk PostgreSQL |

---

## 🚀 Step-by-Step Setup

### 1. Install Laragon

1. Download Laragon 6.0 (versi **Full** direkomendasikan)
2. Install di `C:\laragon`
3. Start Laragon
4. Klik **Preferences** → Pastikan:
   - PHP Version: 8.4 NTS
   - Apache: Enabled
   - PostgreSQL: Tambahkan manual (lihat dokumentasi)

### 2. Setup PostgreSQL di Laragon

PostgreSQL tidak included secara default di Laragon. Ikuti langkah berikut:

1. Download PostgreSQL 16 zip dari [EnterpriseDB](https://www.enterprisedb.com/download-postgresql-binaries)
2. Extract ke `C:\laragon\bin\postgresql\postgresql-16.x-winx64\`
3. Buka Laragon > Menu > Tools > Service/Port > PostgreSQL
4. Inisialisasi database cluster:
   ```bash
   "C:\laragon\bin\postgresql\postgresql-16.x-winx64\bin\initdb.exe" -D "C:/laragon/data/postgresql-16" --username=postgres
   ```
5. Start PostgreSQL dari Laragon

Atau gunakan **NeonDB** langsung untuk development — daftar di [neon.tech](https://neon.tech) dan buat project baru.

### 3. Install Bun (Package Manager)

Bun digunakan sebagai package manager untuk frontend (menggantikan npm).

```bash
# Install via PowerShell (Admin recommended)
powershell -c "irm bun.sh/install.ps1 | iex"

# Verifikasi
bun --version
```

### 4. Install Composer

1. Download Composer Setup dari [getcomposer.org](https://getcomposer.org/download/)
2. Install dengan default settings
3. Test di terminal:
   ```bash
   composer --version
   ```

### 5. Install Git & Setup SSH

1. Download Git for Windows dari [git-scm.com](https://git-scm.com/)
2. Install dengan default settings
3. Setup SSH Key:
   ```bash
   ssh-keygen -t ed25519 -C "your_email@example.com"
   cat ~/.ssh/id_ed25519.pub
   ```
4. Add ke GitHub:
   - Buka [github.com/settings/keys](https://github.com/settings/keys)
   - Klik **New SSH Key**
   - Paste isi `id_ed25519.pub`
   - Save
5. Test koneksi:
   ```bash
   ssh -T git@github.com
   ```

### 6. Install VS Code Extensions

Buka VS Code → Extensions → Install:

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

# Install frontend dependencies (via Bun, bukan npm!)
bun install
```

### 3. Setup Database

**Opsi A — PostgreSQL Lokal (Laragon):**
```bash
# Buat database via psql atau pgAdmin
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

**Opsi B — NeonDB (Cloud):**
1. Daftar di [neon.tech](https://neon.tech)
2. Buat project → dapatkan connection string
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

### 4. Install Packages Tambahan

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

### 6. Jalankan Development Server

```bash
# Terminal 1: Vite dev server (frontend hot reload)
bun run dev

# Terminal 2: Laravel dev server
php artisan serve

# Atau via Laragon → auto start di http://smauii-core.test
```

---

## 🔧 Configuration

### PHP Configuration (`php.ini`)

Lokasi: `C:\laragon\bin\php\php-8.4.22-nts-Win32-vs17-x64\php.ini`

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

Laragon auto-generate virtual host. Pastikan:

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

| Masalah | Solusi |
|---|---|
| **PostgreSQL connection refused** | Pastikan PostgreSQL running di Laragon (Menu > Tools > Service/Port > PostgreSQL) |
| **pdo_pgsql not found** | Cek `php -m` — pastikan `pdo_pgsql` dan `pgsql` ada. Tambahkan `extension=pdo_pgsql` di php.ini jika belum |
| **Port 5432 sudah dipakai** | Cek aplikasi lain yang menggunakan port PostgreSQL. Ganti port di `.env` jika perlu |
| **Composer install gagal** | `composer clear-cache && composer update --no-cache` |
| **Bun install error** | Jalankan PowerShell sebagai Administrator. Atau install via npm: `npm install -g bun` |
| **Permission denied (storage/)** | `icacls storage /grant Users:(OI)(CI)F /T` (PowerShell Admin) |
| **APP_KEY not set** | `php artisan key:generate` |

---

## 📚 Next Steps

Setelah environment setup:

1. [ ] Baca [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)
2. [ ] Baca [`onboarding.md`](onboarding.md) untuk checklist lengkap
3. [ ] Ambil first task dari GitHub Project
4. [ ] Buat branch pertama
5. [ ] Start coding!

---

**Last Updated:** 2026-06-30  
**Maintained by:** Sandikodev
