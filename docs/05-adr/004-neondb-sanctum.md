# ADR 004: NeonDB + Laravel Sanctum

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

After deciding on PostgreSQL as the database (ADR-003-v2), we need to determine:

1. **Database hosting** — Self-managed vs serverless (NeonDB)
2. **Auth strategy** — Plain Laravel Sanctum vs combination with Neon Auth
3. **Dev/Prod parity** — Development and production environments as close as possible

### Database Hosting Options
- Option 1: PostgreSQL self-managed on VPS (DigitalOcean, Linode)
- Option 2: NeonDB serverless PostgreSQL
- Option 3: Supabase (PostgreSQL + Auth + Storage bundled)

### Auth Options
- Option A: Laravel Sanctum (token-based, stateless)
- Option B: Neon Auth (built-in auth from Neon, JWT-based)
- Option C: Laravel Sanctum + Socialite (for SSO later)

## Decision

**Database Hosting:** NeonDB (serverless PostgreSQL)  
**Auth:** Plain Laravel Sanctum + Spatie Laravel Permission for RBAC  
**Dev Environment:** Laragon + PostgreSQL local + NeonDB branch for integration test

## Rationale

### Why NeonDB, Not Self-Managed or Supabase?

| Aspect | Self-Managed | Supabase | NeonDB |
|--------|-------------|----------|--------|
| **Setup effort** | High | Low | Low |
| **Dev/Prod parity** | Perfect | Different | Perfect (branch) |
| **Free tier** | ❌ | ✅ | ✅ |
| **Cold start** | None | Yes | Minimal |
| **Branching** | ❌ | ❌ | ✅ |
| **Vendor lock-in** | No | High | Low (standard PostgreSQL) |

**NeonDB was chosen because:**
1. **Standard PostgreSQL** — Can migrate to any other provider anytime (no lock-in)
2. **Branching for preview** — Every feature can have its own database branch
3. **Point-in-time recovery** — Safe for production
4. **Built-in pooling** — No need to set up PgBouncer
5. **Free for MVP** — 500MB storage is sufficient for development

**Supabase was not chosen because:**
1. **Vendor lock-in** — Auth, Realtime, Storage are all proprietary
2. **Cold start** — Instance sleeps when not in use, 1-5 second delay
3. **Less flexible** — Migration tooling limited compared to native PostgreSQL

### Why Sanctum, Not Neon Auth?

| Aspect | Laravel Sanctum | Neon Auth |
|--------|----------------|-----------|
| **Maturity** | Very mature (Laravel native) | New (preview) |
| **Self-contained** | ✅ Under our control | ❌ Dependency on Neon |
| **SSO capability** | ✅ Can extend to other providers | ❌ Limited |
| **Spatie integration** | ✅ First-class | ❌ Manual |
| **Porting (Phase 2)** | ✅ API token mode | ❌ Needs rewrite |

**Sanctum was chosen because:**
1. **Mature and stable** — Production-ready since Laravel 7
2. **Dual mode** — Session-based (Inertia) + Token-based (API) in one package
3. **Porting friendly** — Phase 2 just switch from session to token mode
4. **Spatie integration** — Role & permission directly integrated
5. **Self-contained** — Does not depend on third-party for auth

### RBAC with Spatie Laravel Permission

```php
// Install
// composer require spatie/laravel-permission

// Usage example
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
- Sanctum with **token-based** for API consumption from Next.js / Mobile
- SPA mode for Inertia pages (session-based)
- Multiple tokens per user (one for webapp, one for mobile app)
- Token abilities/scopes for fine-grained access control

### Security Considerations
- Sanctum token stored hashed in database
- Token expiry configurable (default: no expiry — can be set per use case)
- CSRF protection for Inertia session routes
- Rate limiting for API endpoints

---

**Last Updated:** 2026-06-30
