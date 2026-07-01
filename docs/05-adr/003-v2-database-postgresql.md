# ADR 003-v2: PostgreSQL via NeonDB for Production

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev  
**Supersedes:** [ADR-003](003-database-mysql.md)

---

## Context

The initial decision (ADR-003) chose MySQL 8.0 due to team familiarity and Laragon default. After further evaluation, the team decided on a revision because:

1. **NeonDB (serverless PostgreSQL)** — provides features that MySQL doesn't have for modern deployment: auto-scaling, branching for preview deployment, and built-in connection pooling.
2. **PostgreSQL features** — JSONB (for semi-structured attendance data), array column, window functions, and full-text search that is more mature than MySQL.
3. **Laravel first-class support** — Laravel 13 has full support for PostgreSQL, including compatible migration types.
4. **Porting pathway** — If core later becomes a dedicated backend, PostgreSQL is more suitable for multi-tenant and analytical queries.

## Decision

**Production:** PostgreSQL 16 via NeonDB (serverless)  
**Development:** PostgreSQL 16 (Laragon) or NeonDB branch  
**Testing:** SQLite (in-memory) for unit test, NeonDB branch for integration test

## Rationale

### Why PostgreSQL, Not MySQL?

| Aspect | MySQL 8.0 | PostgreSQL 16 |
|--------|-----------|---------------|
| **JSON support** | JSON (text) | JSONB (binary, indexable) |
| **Full-text search** | Limited | Mature (tsvector, tsquery) |
| **Window functions** | Limited | Full support |
| **Array column** | ❌ | ✅ Native |
| **Concurrency** | Lock-based | Better MVCC |
| **NeonDB support** | ❌ | ✅ First-class |
| **Laravel support** | ✅ | ✅ (equally good) |

### Why NeonDB?

1. **Serverless** — No need to manage server, pooler, or replicas
2. **Branching** — Every PR can have its own database branch → preview deployment with data isolation
3. **Connection pooling** — Built-in PgBouncer, no additional setup needed
4. **Free tier** — 500MB storage, sufficient for development and MVP
5. **Point-in-time recovery** — Automatic backup, can restore to a specific second
6. **Familiar ecosystem** — PostgreSQL tools (pgAdmin, DBeaver, TablePlus) mature on Windows

### Why SQLite still for Unit Test?

1. **Speed** — In-memory, no TCP connection needed
2. **Isolation** — Each test gets a clean database
3. **Laravel default** — `php artisan test` ready to use
4. **Sufficient for** — Unit testing models, services, and controllers

## Consequences

### Development Setup

```bash
# Local development (Laragon)
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=smauii_dev
DB_USERNAME=root
DB_PASSWORD=

# Local development (NeonDB direct)
DB_CONNECTION=pgsql
DB_HOST=ep-xxx-xxxx.us-east-2.aws.neon.tech
DB_PORT=5432
DB_DATABASE=smauii_dev
DB_USERNAME=smauii_owner
DB_PASSWORD=xxxxxx
DB_SSLMODE=require
```

### Testing

```bash
# PHPUnit unit test
DB_CONNECTION=sqlite
DB_DATABASE=:memory:
```

### Integration Test

```bash
# GitHub Actions (NeonDB branch)
DB_CONNECTION=pgsql
DB_HOST=${{ secrets.NEON_DB_HOST }}
DB_DATABASE=${{ secrets.NEON_DB_NAME }}
DB_USERNAME=${{ secrets.NEON_DB_USER }}
```

### Migration Notes

Some MySQL → PostgreSQL differences to note:

| MySQL | PostgreSQL | Notes |
|-------|-----------|-------|
| `INT AUTO_INCREMENT` | `SERIAL` / `BIGSERIAL` | Laravel migration handles automatically |
| `VARCHAR` | `VARCHAR` / `TEXT` | Same |
| `DATETIME` | `TIMESTAMP` | Laravel `timestamps()` compatible |
| `JSON` | `JSONB` | Better for queries |
| `BOOLEAN` TINYINT(1) | `BOOLEAN` | Native boolean |
| `ENUM` | `VARCHAR` + CHECK | Laravel enum migration support |

---

**Last Updated:** 2026-06-30
