# ADR 001: Monorepo Structure

**Date:** 2026-06-20  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

We need to decide the repository structure for the SMART Absen SMA UII project:
- Option 1: Single repository (Laravel monolith)
- Option 2: Multiple repositories (backend, frontend, mobile separate)
- Option 3: Monorepo with submodule

## Decision

Chosen: **Option 3 — Monorepo with Submodule**

Structure:
```
aksesekolah/ (entrypoint)
├── apps/
│   ├── backend/  → core (git submodule)
│   ├── frontend/ → webapp (git submodule)
│   └── mobile/   → flutter (git submodule)
└── docs/
```

## Rationale

**Advantages:**
1. Single entry point for documentation & onboarding
2. Backend (`core`) can be developed separately
3. Frontend can evolve to Next.js without breaking backend
4. Mobile app can be standalone
5. Versioning per module

**Disadvantages:**
1. Complexity git submodule
2. CI/CD more complex

## Consequences

- Developer must understand git submodule
- `core` can be deployed separately
- Frontend can consume `core` API without co-deployment

---

**Last Updated:** 2026-06-20
