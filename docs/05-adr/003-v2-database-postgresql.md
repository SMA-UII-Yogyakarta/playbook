# ADR 003-v2: PostgreSQL via NeonDB untuk Production

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev  
**Supersedes:** [ADR-003](003-database-mysql.md)

---

## Context

Keputusan awal (ADR-003) memilih MySQL 8.0 dengan alasan team familiarity dan Laragon default. Setelah evaluasi lebih lanjut, tim memutuskan revisi karena:

1. **NeonDB (serverless PostgreSQL)** — memberikan fitur yang tidak dimiliki MySQL untuk deployment modern: auto-scaling, branching untuk preview deployment, dan connection pooling built-in.
2. **PostgreSQL features** — JSONB (untuk data presensi yang semi-structured), array column, window functions, dan full-text search yang lebih mature dari MySQL.
3. **Laravel first-class support** — Laravel 13 memiliki dukungan penuh untuk PostgreSQL, termasuk migration type yang kompatibel.
4. **Porting pathway** — Jika nanti core menjadi dedicated backend, PostgreSQL lebih cocok untuk multi-tenant dan analytical queries.

## Decision

**Production:** PostgreSQL 16 via NeonDB (serverless)  
**Development:** PostgreSQL 16 (Laragon) atau NeonDB branch  
**Testing:** SQLite (in-memory) untuk unit test, NeonDB branch untuk integration test

## Rationale

### Kenapa PostgreSQL, Bukan MySQL?

| Aspek | MySQL 8.0 | PostgreSQL 16 |
|-------|-----------|---------------|
| **JSON support** | JSON (teks) | JSONB (binary, indexable) |
| **Full-text search** | Terbatas | Mature (tsvector, tsquery) |
| **Window functions** | Limited | Full support |
| **Array column** | ❌ | ✅ Native |
| **Concurrency** | Lock-based | MVCC lebih baik |
| **NeonDB support** | ❌ | ✅ First-class |
| **Laravel support** | ✅ | ✅ (sama baik) |

### Kenapa NeonDB?

1. **Serverless** — Tidak perlu manage server, pooler, atau replicas
2. **Branching** — Setiap PR bisa punya database branch sendiri → preview deployment dengan data isolasi
3. **Connection pooling** — Built-in PgBouncer, tidak perlu setup tambahan
4. **Free tier** — 500MB storage, cukup untuk development dan MVP
5. **Point-in-time recovery** — Backup otomatis, bisa restore ke detik tertentu
6. **Familiar ecosystem** — PostgreSQL tools (pgAdmin, DBeaver, TablePlus) mature di Windows

### Kenapa SQLite tetap untuk Unit Test?

1. **Kecepatan** — In-memory, tidak perlu koneksi TCP
2. **Isolasi** — Setiap test dapat database bersih
3. **Laravel default** — `php artisan test` siap pakai
4. **Cukup untuk** — Unit test model, service, dan controller

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

Beberapa perbedaan MySQL → PostgreSQL yang perlu diperhatikan:

| MySQL | PostgreSQL | Catatan |
|-------|-----------|---------|
| `INT AUTO_INCREMENT` | `SERIAL` / `BIGSERIAL` | Laravel migration handle otomatis |
| `VARCHAR` | `VARCHAR` / `TEXT` | Sama |
| `DATETIME` | `TIMESTAMP` | Laravel `timestamps()` kompatibel |
| `JSON` | `JSONB` | Lebih baik untuk query |
| `BOOLEAN` TINYINT(1) | `BOOLEAN` | Native boolean |
| `ENUM` | `VARCHAR` + CHECK | Laravel enum migration support |

---

**Last Updated:** 2026-06-30
