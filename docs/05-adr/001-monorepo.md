# ADR 001: Monorepo Structure

**Date:** 2026-06-20  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

Kita perlu memutuskan struktur repository untuk project SMART Absen SMA UII:
- Opsi 1: Single repository (Laravel monolith)
- Opsi 2: Multiple repositories (backend, frontend, mobile terpisah)
- Opsi 3: Monorepo dengan submodule

## Decision

Dipilih: **Opsi 3 — Monorepo dengan Submodule**

Struktur:
```
aksesekolah/ (entrypoint)
├── apps/
│   ├── backend/  → core (git submodule)
│   ├── frontend/ → webapp (git submodule)
│   └── mobile/   → flutter (git submodule)
└── docs/
```

## Rationale

**Keuntungan:**
1. Single entry point untuk dokumentasi & onboarding
2. Backend (`core`) dapat dikembangkan terpisah
3. Frontend dapat evolve ke Next.js tanpa breaking backend
4. Mobile app dapat standalone
5. Versioning per module

**Kerugian:**
1. Complexity git submodule
2. CI/CD lebih kompleks

## Consequences

- Developer harus paham git submodule
- `core` dapat di-deploy terpisah
- Frontend dapat consume API `core` tanpa deploy bersama

---

**Last Updated:** 2026-06-20