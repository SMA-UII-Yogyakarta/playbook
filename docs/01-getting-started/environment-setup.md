# Environment Setup — Development

> Panduan setup environment development untuk SMART Absen SMA UII.

**OS:** Windows 10/11  
**Stack:** Laragon 6.0, PHP 8.5.7, MySQL 8.0.30, Node.js 20+

---

## 📋 Prerequisites

### Software Wajib

| Software | Version | Download |
|---|---|---|
| **Laragon** | 6.0 | [laragon.org](https://laragon.org/download/) |
| **PHP** | 8.5.7 NTS | Included in Laragon |
| **Composer** | 2.x | [getcomposer.org](https://getcomposer.org/download/) |
| **Node.js** | 20.x LTS | [nodejs.org](https://nodejs.org/) |
| **Git** | Latest | [git-scm.com](https://git-scm.com/) |
| **VS Code** | Latest | [code.visualstudio.com](https://code.visualstudio.com/) |

---

## 🚀 Step-by-Step Setup

### 1. Install Laragon

1. Download Laragon 6.0
2. Install di `C:\laragon`
3. Start Laragon
4. Klik **Preferences** → Pastikan:
   - PHP Version: 8.5.7 NTS
   - Apache: Enabled
   - MySQL: Enabled
   - Auto Start: On

---

### 2. Install Composer

1. Download Composer Setup
2. Install dengan default settings
3. Test di terminal:

```bash
composer --version
```

---

### 3. Install Node.js

1. Download Node.js 20.x LTS
2. Install dengan default settings
3. Test:

```bash
node --version
npm --version
```

---

### 4. Install Git

1. Download Git for Windows
2. Install dengan default settings
3. Setup SSH Key:

```bash
# Generate SSH Key
ssh-keygen -t ed25519 -C "your_email@example.com"

# Tekan Enter untuk default location
# Masukkan passphrase (opsional)

# Copy public key
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

---

### 5. Install VS Code Extensions

Buka VS Code → Extensions → Install:

| Extension | Publisher | Purpose |
|---|---|---|
| **PHP Intelephense** | Ben Mewburn | PHP IntelliSense |
| **Laravel Blade Snippets** | Winnie Lin | Blade syntax highlight |
| **Tailwind CSS IntelliSense** | Brad Cornes | Tailwind autocomplete |
| **Prettier** | Prettier | Code formatter |
| **GitLens** | GitKraken | Git blame, history |
| **Thunder Client** | Ranga Vadhineni | API testing (alternatif Postman) |

---

## 📁 Clone Repositories

### 1. Clone Core (Backend)

```bash
cd C:\laragon\www
git clone git@github.com:SMA-UII-Yogyakarta/core.git
cd core
```

### 2. Setup Environment

```bash
# Copy .env example
copy .env.example .env

# Generate APP_KEY
php artisan key:generate

# Install dependencies
composer install
```

### 3. Setup Database

```bash
# Buat database di MySQL
# Via phpMyAdmin atau Laragon MySQL

CREATE DATABASE smauii_dev;
CREATE DATABASE smauii_test;
```

Edit `.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=smauii_dev
DB_USERNAME=root
DB_PASSWORD=
```

### 4. Migration & Seeder

```bash
# Run migration
php artisan migrate

# Run seeder
php artisan db:seed
```

### 5. Install Frontend Dependencies

```bash
npm install
npm run dev
```

### 6. Test

```bash
# Start development server
php artisan serve

# Atau via Laragon
# Auto start di http://core.test
```

---

## 🔧 Configuration

### PHP Configuration (`php.ini`)

Lokasi: `C:\laragon\bin\php\php-8.5.7-nts-Win32-vs17-x64\php.ini`

```ini
; Timezone
date.timezone = "Asia/Jakarta"

; Memory Limit
memory_limit = 512M

; Upload Max
upload_max_filesize = 10M
post_max_size = 10M

; Extensions (ensure enabled)
extension=pdo_mysql
extension=mbstring
extension=openssl
extension=curl
extension=fileinfo
```

### Apache Virtual Host

Laragon auto-generate virtual host. Pastikan:

```
DocumentRoot: C:\laragon\www\core\public
Server Name: core.test
```

---

## ✅ Verification Checklist

### Backend

```bash
# Check PHP version
php --version
# Expected: PHP 8.5.7

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
# Check Node version
node --version

# Check NPM
npm --version

# Build assets
npm run build

# Development server
npm run dev
```

### Git

```bash
# Check Git version
git --version

# Check SSH connection
ssh -T git@github.com
# Expected: Hi Sandikodev! You've successfully authenticated...
```

---

## 🐛 Troubleshooting

### Problem: Port 80/443 sudah digunakan

**Solusi:**
1. Stop Apache di Laragon
2. Edit `httpd.conf` → ganti port 8080/8443
3. Restart Apache

### Problem: Composer install gagal

**Solusi:**
```bash
composer clear-cache
composer update --no-cache
```

### Problem: npm install error

**Solusi:**
```bash
# Delete node_modules
rmdir /s /q node_modules

# Delete package-lock.json
del package-lock.json

# Install ulang
npm install
```

### Problem: Database connection refused

**Solusi:**
1. Pastikan MySQL running di Laragon
2. Cek `.env` DB_USERNAME, DB_PASSWORD
3. Test koneksi via phpMyAdmin

### Problem: Permission denied (storage/)

**Solusi:**
```bash
# Windows (PowerShell Admin)
icacls storage /grant Users:(OI)(CI)F /T
```

---

## 📚 Next Steps

Setelah environment setup:

1. [ ] Baca [`git-github-workflow.md`](../02-workflow/git-github-workflow.md)
2. [ ] Ambil first task dari GitHub Project
3. [ ] Buat branch pertama
4. [ ] Start coding!

---

**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev