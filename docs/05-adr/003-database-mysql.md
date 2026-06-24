# ADR 003: MySQL Database

**Date:** 2026-06-22  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

Kita perlu memutuskan database untuk SMART Absen:
- Opsi 1: MySQL 8.0
- Opsi 2: PostgreSQL 15
- Opsi 3: SQLite (development only)

## Decision

**Production:** MySQL 8.0.30  
**Development:** MySQL 8.0.30 (Laragon)  
**Testing:** SQLite (in-memory)

## Rationale

### MySQL 8.0

**Alasan:**
1. **Team familiarity** — Ihsan & Fathan sudah familiar MySQL
2. **Laragon default** — Easy setup di Windows
3. **Performance** — Cukup untuk scale SMA UII (ribuan siswa)
4. **Ecosystem** — Banyak tooling (phpMyAdmin, Workbench)
5. **Cost** — Free, open-source

### SQLite untuk Testing

**Alasan:**
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

Jika perlu migrate ke PostgreSQL nanti:
- Change `DB_CONNECTION` di `.env`
- Adjust data types (MySQL → PostgreSQL)
- Test thoroughly

---

**Last Updated:** 2026-06-22