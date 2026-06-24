# Deployment SOP

> Standar deployment SMART Absen ke staging & production.

---

## 🎯 Environment Overview

| Environment | URL | Purpose | Access |
|---|---|---|---|
| **Local** | `http://core.test` | Development | Developer |
| **Staging** | `http://staging.smauiiyk.sch.id` | UAT, Testing | Tim + Stakeholder |
| **Production** | `https://smauiiyk.sch.id` | Live users | Public |

---

## 📋 Pre-Deployment Checklist

### Staging Deployment

```markdown
## Staging Checklist

### Code
- [ ] PR merged ke main
- [ ] All tests passed
- [ ] Code review approved

### Database
- [ ] Migration tested di local
- [ ] Seeder tested (jika ada)
- [ ] Backup database staging

### Environment
- [ ] .env.staging updated (jika ada config change)
- [ ] Cache cleared
- [ ] Config cached

### Testing
- [ ] Smoke test passed
- [ ] UAT by Ahmad Hanif
- [ ] Stakeholder demo (jika perlu)
```

---

### Production Deployment

```markdown
## Production Checklist

### Pre-Deployment
- [ ] Staging UAT passed
- [ ] Stakeholder approval (Pak Mahfud)
- [ ] Backup database production
- [ ] Rollback plan ready
- [ ] Deployment time scheduled (outside school hours)

### Code
- [ ] Git tag created (v1.0.0)
- [ ] CHANGELOG updated
- [ ] Main branch updated

### Database
- [ ] Migration script ready
- [ ] Rollback migration script ready
- [ ] Database backup verified

### Communication
- [ ] Deployment notice sent (email + WhatsApp)
- [ ] Support team on standby
- [ ] Monitoring tools ready
```

---

## 🚀 Deployment Process

### Staging Deployment (Automated)

**Frequency:** Setiap ada merge ke `main`  
**PIC:** Sandikodev  
**Duration:** 5-10 menit

```bash
# 1. SSH ke staging server
ssh user@staging.smauiiyk.sch.id

# 2. Navigate to project
cd /var/www/smauii-staging

# 3. Pull latest code
git pull origin main

# 4. Install dependencies
composer install --no-dev --optimize-autoloader
npm install
npm run build

# 5. Clear cache
php artisan cache:clear
php artisan config:clear
php artisan view:clear

# 6. Cache config (production optimization)
php artisan config:cache
php artisan route:cache
php artisan view:cache

# 7. Run migration (jika ada)
php artisan migrate --force

# 8. Restart queue worker (jika ada)
php artisan queue:restart

# 9. Test staging
curl http://staging.smauiiyk.sch.id
```

---

### Production Deployment (Manual)

**Frequency:** End of sprint (setiap 2 minggu) atau critical fix  
**PIC:** Sandikodev + Pak Mahfud (approval)  
**Duration:** 15-30 menit  
**Timing:** Weekend atau malam (outside school hours)

#### Phase 1: Pre-Deployment (H-1)

```bash
# 1. Create git tag
git tag -a v1.0.0 -m "Production Release v1.0.0"
git push origin v1.0.0

# 2. Backup database production
ssh user@smauiiyk.sch.id
mysqldump -u root smauii_production > backup_$(date +%Y%m%d).sql

# 3. Download backup
scp user@smauiiyk.sch.id:/home/user/backup_*.sql ./backups/

# 4. Verify backup
mysql -u root -e "CREATE DATABASE backup_test; USE backup_test; SOURCE backup_20260624.sql;"
```

---

#### Phase 2: Deployment Day

**Step 1: Maintenance Mode (5 menit)**

```bash
# Enable maintenance mode
php artisan down

# Or create maintenance file
touch storage/framework/down
```

**Step 2: Deploy Code (10 menit)**

```bash
# SSH ke production
ssh user@smauiiyk.sch.id

# Navigate to project
cd /var/www/smauii-production

# Pull latest code
git pull origin main

# Install dependencies
composer install --no-dev --optimize-autoloader

# Build assets
npm install
npm run build

# Clear cache
php artisan cache:clear
php artisan config:clear
php artisan view:clear

# Cache config
php artisan config:cache
php artisan route:cache
php artisan view:cache

# Optimize autoloader
composer dump-autoload --optimize
```

**Step 3: Database Migration (5 menit)**

```bash
# Run migration
php artisan migrate --force

# Verify migration
php artisan migrate:status
```

**Step 4: Post-Deployment (5 menit)**

```bash
# Restart queue worker
php artisan queue:restart

# Restart Octane (jika pakai)
php artisan octane:reload

# Clear compiled files
php artisan optimize:clear

# Test locally
curl http://localhost:8000
```

**Step 5: Bring Up (2 menit)**

```bash
# Disable maintenance mode
php artisan up

# Or remove maintenance file
rm storage/framework/down
```

---

#### Phase 3: Post-Deployment Testing

**Smoke Test Checklist:**

```markdown
## Smoke Test (5 menit)

### Authentication
- [ ] Login page accessible
- [ ] Login dengan valid credentials
- [ ] Logout berfungsi
- [ ] Invalid login shows error

### Core Features
- [ ] Dashboard loads
- [ ] Presensi form accessible
- [ ] Submit presensi berhasil
- [ ] Laporan accessible

### Performance
- [ ] Page load < 2 detik
- [ ] No console errors
- [ ] No 500 errors

### Mobile
- [ ] Responsive di mobile
- [ ] Camera accessible
- [ ] Geolocation working
```

---

## 🔄 Rollback Procedure

### When to Rollback

- Critical bug production
- Data corruption
- Performance degradation > 50%
- Security vulnerability

### Rollback Steps

```bash
# 1. Enable maintenance mode
php artisan down

# 2. Rollback code (git revert)
git revert HEAD
git push origin main

# OR checkout ke tag sebelumnya
git checkout v0.9.0

# 3. Rollback database migration
php artisan migrate:rollback --step=1

# 4. Restore database backup (jika perlu)
mysql -u root smauii_production < backup_20260624.sql

# 5. Clear cache
php artisan cache:clear
php artisan config:clear
php artisan view:clear

# 6. Bring up
php artisan up

# 7. Test
curl https://smauiiyk.sch.id
```

---

## 📊 Deployment Communication

### Pre-Deployment Notice (H-1)

**To:** Pak Mahfud, SMA UII Staff  
**Subject:** [NOTICE] Production Deployment — SMART Absen v1.0 — 25 Juni 2026

```
Assalamu'alaikum Pak Mahfud,

Kami informasikan akan ada deployment SMART Absen versi 1.0:

📅 Tanggal: Selasa, 25 Juni 2026
⏰ Waktu: 20:00 - 21:00 WIB
⏱️ Durasi: 60 menit (estimasi)
🔧 Impact: Downtime (sistem tidak dapat diakses)

FITUR BARU
- Presensi Siswa dengan Geolokasi
- Presensi Guru & Staff
- Dashboard Admin
- Export Laporan Excel

BUG FIX
- Fix login error
- Fix presensi duplicate

Mohon informasikan ke seluruh staff & guru.

Terima kasih.

Best regards,
Sandikodev
PT Koneksi Jaringan Indonesia
```

---

### Deployment Complete Notice

**To:** Pak Mahfud, SMA UII Staff  
**Subject:** [SUCCESS] Deployment SMART Absen v1.0 Completed

```
Assalamu'alaikum Pak Mahfud,

Deployment SMART Absen versi 1.0 telah selesai:

✅ Status: SUCCESS
⏰ Completed: 20:45 WIB (45 menit)
🐛 Issues: None

SISTEM SUDAH DAPAT DIAKSES KEMBALI

FITUR YANG AKTIF
✅ Login & Authentication
✅ Presensi Siswa
✅ Presensi Guru
✅ Dashboard Admin
✅ Export Laporan

KNOWN ISSUES
- Export laporan max 1000 baris (limitasi MVP)
- Belum ada notifikasi WhatsApp (roadmap Sprint 3)

SUPPORT
Jika ada kendala, silakan hubungi:
WhatsApp: [Group Link]
Email: support@koneksi.id

Terima kasih.

Best regards,
Sandikodev
```

---

## 🛠️ Deployment Tools

### Server Requirements

**Minimum:**
- CPU: 2 Core
- RAM: 4 GB
- Storage: 20 GB SSD
- OS: Ubuntu 20.04 LTS

**Recommended:**
- CPU: 4 Core
- RAM: 8 GB
- Storage: 40 GB SSD
- OS: Ubuntu 22.04 LTS

---

### Software Stack

```
Web Server    : Nginx 1.24+
PHP           : PHP 8.5.7 FPM
Database      : MySQL 8.0.30
Cache         : Redis 7.0
Queue         : Database/Redis
SSL           : Let's Encrypt (Certbot)
Monitoring    : Laravel Telescope, Sentry
```

---

### Nginx Configuration

```nginx
server {
    listen 80;
    server_name smauiiyk.sch.id;
    root /var/www/smauii-production/public;

    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-Content-Type-Options "nosniff";

    index index.php;

    charset utf-8;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }

    error_page 404 /index.php;

    location ~ \.php$ {
        fastcgi_pass 127.0.0.1:9000;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.(?!well-known).* {
        deny all;
    }
}
```

---

## 📈 Monitoring & Alerting

### Post-Deployment Monitoring (24 jam)

**Metrics to Watch:**
- Response time (< 200ms)
- Error rate (< 0.1%)
- Database query time (< 100ms)
- Queue lag (< 1 menit)

**Tools:**
- Laravel Telescope (local monitoring)
- Sentry (error tracking)
- Uptime Robot (uptime monitoring)

---

### Alert Configuration

**Critical Alerts (SMS/Call):**
- Server down
- Database connection lost
- Error rate > 5%

**Warning Alerts (WhatsApp):**
- Response time > 500ms
- Disk usage > 80%
- Queue lag > 10 menit

---

## 🐛 Troubleshooting

### Issue: 500 Error After Deploy

**Diagnosis:**
```bash
# Check logs
tail -f storage/logs/laravel.log

# Check PHP error log
tail -f /var/log/php/error.log

# Check Nginx error log
tail -f /var/log/nginx/error.log
```

**Common Causes:**
- Permission issue
- Missing dependency
- Config cache stale

**Fix:**
```bash
# Fix permission
chmod -R 775 storage bootstrap/cache
chown -R www-data:www-data storage bootstrap/cache

# Clear cache
php artisan cache:clear
php artisan config:clear
php artisan view:clear

# Reinstall dependencies
composer install --no-dev
```

---

### Issue: Migration Failed

**Diagnosis:**
```bash
# Check migration status
php artisan migrate:status

# Check specific error
php artisan migrate --step
```

**Fix:**
```bash
# Rollback last migration
php artisan migrate:rollback --step=1

# Fix migration file
# Re-run migration
php artisan migrate
```

---

### Issue: Assets Not Loading

**Diagnosis:**
```bash
# Check manifest
cat public/build/manifest.json
```

**Fix:**
```bash
# Rebuild assets
npm install
npm run build

# Clear cache
php artisan view:clear
```

---

## 📚 Resources

- [Laravel Deployment](https://laravel.com/docs/deployment)
- [ServerPilot](https://serverpilot.io/)
- [Laravel Forge](https://forge.laravel.com/)

---

**Next:** [`testing.md`](testing.md)  
**Last Updated:** Juni 2026  
**Maintained by:** Sandikodev