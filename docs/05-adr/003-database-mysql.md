# ADR 003: MySQL Database [SUPERSEDED]

**Date:** 2026-06-22  
**Status:** ❌ **Superseded** — by [ADR-003-v2](003-v2-database-postgresql.md) on 2026-06-30  
**Deciders:** Sandikodev

---

## Context

We need to decide the database for SMART Absen:
- Option 1: MySQL 8.0
- Option 2: PostgreSQL 15
- Option 3: SQLite (development only)

## Decision (Original — Not Applied)

**Production:** MySQL 8.0.30  
**Development:** MySQL 8.0.30 (Laragon)  
**Testing:** SQLite (in-memory)

## Rationale

### MySQL 8.0

**Reasons:**
1. **Team familiarity** — Ihsan & Fathan are already familiar with MySQL
2. **Laragon default** — Easy setup on Windows
3. **Performance** — Sufficient for SMA UII scale (thousands of students)
4. **Ecosystem** — Many tools (phpMyAdmin, Workbench)
5. **Cost** — Free, open-source

### SQLite for Testing

**Reasons:**
1. **Fast** — In-memory, no I/O
2. **Simple** — No setup required
3. **Laravel default** — `php artisan test` ready

## Consequences

### Development

```bash
# Local development
DB_CONNECTION=mysql
DB_DATABASE=smauii_dev
```

### Testing

```bash
# PHPUnit testing
DB_CONNECTION=sqlite
DB_DATABASE=:memory:
```

### Production

```bash
# Production
DB_CONNECTION=mysql
DB_DATABASE=smauii_production
```

## Migration Path

If migration to PostgreSQL is needed later:
- Change `DB_CONNECTION` in `.env`
- Adjust data types (MySQL → PostgreSQL)
- Test thoroughly

---

**Last Updated:** 2026-06-22
