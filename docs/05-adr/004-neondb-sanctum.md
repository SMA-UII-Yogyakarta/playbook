# ADR 004: NeonDB + Laravel Sanctum

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

Setelah memutuskan PostgreSQL sebagai database (ADR-003-v2), kita perlu menentukan:

1. **Database hosting** — Self-managed vs serverless (NeonDB)
2. **Auth strategy** — Laravel Sanctum murni vs kombinasi dengan Neon Auth
3. **Dev/Prod parity** — Environment development dan produksi sedekat mungkin

### Opsi Database Hosting
- Opsi 1: PostgreSQL self-managed di VPS (DigitalOcean, Linode)
- Opsi 2: NeonDB serverless PostgreSQL
- Opsi 3: Supabase (PostgreSQL + Auth + Storage bundled)

### Opsi Auth
- Opsi A: Laravel Sanctum (token-based, stateless)
- Opsi B: Neon Auth (built-in auth dari Neon, JWT-based)
- Opsi C: Laravel Sanctum + Socialite (untuk SSO nanti)

## Decision

**Database Hosting:** NeonDB (serverless PostgreSQL)  
**Auth:** Laravel Sanctum murni + Spatie Laravel Permission untuk RBAC  
**Dev Environment:** Laragon + PostgreSQL lokal + NeonDB branch untuk integration test

## Rationale

### Kenapa NeonDB, Bukan Self-Managed atau Supabase?

| Aspek | Self-Managed | Supabase | NeonDB |
|-------|-------------|----------|--------|
| **Setup effort** | Tinggi | Rendah | Rendah |
| **Dev/Prod parity** | Sempurna | Berbeda | Sempurna (branch) |
| **Free tier** | ❌ | ✅ | ✅ |
| **Cold start** | Tidak ada | Ada | Minimal |
| **Branching** | ❌ | ❌ | ✅ |
| **Vendor lock-in** | Tidak | Tinggi | Rendah (PostgreSQL standar) |

**NeonDB dipilih karena:**
1. **PostgreSQL standar** — Bisa migrate ke provider lain kapan saja (tidak ada lock-in)
2. **Branching untuk preview** — Setiap fitur bisa punya database branch sendiri
3. **Point-in-time recovery** — Aman untuk production
4. **Built-in pooling** — Tidak perlu setup PgBouncer
5. **Gratis untuk MVP** — 500MB storage cukup untuk development

**Supabase tidak dipilih karena:**
1. **Vendor lock-in** — Auth, Realtime, Storage semuanya proprietary
2. **Cold start** — Instance tidur jika tidak dipakai, delay 1-5 detik
3. **Kurang fleksibel** — Migration tooling terbatas dibanding native PostgreSQL

### Kenapa Sanctum, Bukan Neon Auth?

| Aspek | Laravel Sanctum | Neon Auth |
|-------|----------------|-----------|
| **Maturity** | Sangat matang (Laravel native) | Baru (preview) |
| **Self-contained** | ✅ Dalam kontrol kita | ❌ Dependency ke Neon |
| **SSO capability** | ✅ Bisa extend ke provider lain | ❌ Terbatas |
| **Spatie integration** | ✅ First-class | ❌ Manual |
| **Porting (Fase 2)** | ✅ API token mode | ❌ Perlu rewrite |

**Sanctum dipilih karena:**
1. **Mature dan stabil** — Sudah production-ready sejak Laravel 7
2. **Dual mode** — Session-based (Inertia) + Token-based (API) dalam satu paket
3. **Porting friendly** — Fase 2 tinggal switch dari session ke token mode
4. **Spatie integration** — Role & permission langsung terintegrasi
5. **Self-contained** — Tidak tergantung pihak ketiga untuk auth

### RBAC dengan Spatie Laravel Permission

```php
// Install
// composer require spatie/laravel-permission

// Contoh penggunaan
$user->assignRole('guru');
$user->givePermissionTo('create-presensi');

// Middleware
Route::middleware(['auth:sanctum', 'role:guru|admin']);
Route::middleware(['auth:sanctum', 'permission:create-presensi']);
```

## Consequences

### Development
```bash
# Install Sanctum
bun add composer laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"

# Install Spatie Permission
bun add composer spatie/laravel-permission
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"

# Setup NeonDB
DB_CONNECTION=pgsql
DB_HOST=ep-xxx-xxxx.us-east-2.aws.neon.tech
DB_PORT=5432
DB_DATABASE=smauii_dev
DB_USERNAME=smauii_owner
DB_PASSWORD=xxxxxx
DB_SSLMODE=require
```

### Production
- Sanctum dengan **token-based** untuk API consumption dari Next.js / Mobile
- SPA mode untuk Inertia pages (session-based)
- Multiple token per user (satu untuk webapp, satu untuk mobile app)
- Token abilities/scopes untuk fine-grained access control

### Security Considerations
- Sanctum token disimpan hashed di database
- Token expiry configurable (default: tidak expire — bisa di-set per use case)
- CSRF protection untuk Inertia session routes
- Rate limiting untuk API endpoints

---

**Last Updated:** 2026-06-30
