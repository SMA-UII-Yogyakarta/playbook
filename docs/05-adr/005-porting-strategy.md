# ADR 005: Porting Strategy — Monolith (Inertia) → API + Multi Client

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

SMART Absen is built in two architectural phases:

- **Phase 1 (MVP):** Laravel monolith with InertiaJS + React — single codebase for backend and frontend
- **Phase 2 (Dedicated Backend):** Laravel API-only — backend separated from frontend, serving multiple clients (Next.js webapp, React Native / Flutter mobile, SIAD, external systems)

This decision documents the porting strategy so that the transition from Phase 1 to Phase 2 runs smoothly without a rewrite.

## Decision

### Service Layer Pattern

All business logic is written in `app/Services/` from Phase 1, not in controllers:

```
app/Services/
├── AuthService.php          → Login, register, SSO
├── PresensiService.php      → Check-in, geolocation, selfie
├── IzinService.php          → Leave application, approval
├── LaporanService.php       → Generate reports, export
├── SiswaService.php         → CRUD students, import
├── GuruService.php          → CRUD teachers, assign
└── KelasService.php         → CRUD classes, homeroom teachers
```

**Why Service Layer?**
- Controllers (Inertia and API) only call services — they don't contain logic
- When porting to Phase 2, just create a new API controller that calls the same service
- Services can be tested independently without mocking HTTP

### Two Controller Types from Phase 1

```
app/Http/Controllers/
├── Web/                    ← Controller for Inertia pages
│   ├── AuthController.php
│   ├── PresensiController.php
│   └── DashboardController.php
│
├── Api/                    ← Controller for API endpoints
│   ├── AuthController.php
│   ├── PresensiController.php
│   └── LaporanController.php
│
└── Services/              ← (link to app/Services)

routes/
├── web.php                 ← Inertia routes
└── api.php                 ← Sanctum-protected API routes
```

**Why two controllers from the start?**
- API routes remain active even though Inertia is used as the main frontend
- Mobile app can test API endpoints from Sprint 2 (even if using Postman first)
- No "big bang migration" — API already exists and is tested when Next.js is ready

### Porting Matrix

| Component | Phase 1 (Inertia) | Phase 2 (API-only) | Action |
|-----------|-----------------|-------------------|--------|
| **Service Layer** | `app/Services/*` | Same, unchanged | ✅ **Zero change** |
| **Models** | `app/Models/*` | Same, unchanged | ✅ **Zero change** |
| **Migrations** | `database/migrations/*` | Same, unchanged | ✅ **Zero change** |
| **Web Controllers** | `app/Http/Controllers/Web/*` | Remove/deactivate | ⚠️ Remove |
| **API Controllers** | `app/Http/Controllers/Api/*` | Same, still active | ✅ **Zero change** |
| **Inertia Pages** | `resources/js/Pages/*` | Move to Next.js | 🔄 Migrate |
| **React Components** | `resources/js/Components/*` | Move to Next.js | 🔄 Migrate |
| **Sanctum Auth** | Session mode | Token mode | 🔄 Switch mode |
| **Spatie RBAC** | Same | Same | ✅ **Zero change** |
| **Routes web.php** | Inertia routes | Remove | ⚠️ Remove |
| **Routes api.php** | API routes | API routes (same) | ✅ **Zero change** |

### Trigger Porting

Porting to Phase 2 is done when ONE or MORE of the following conditions are met:

1. **Dedicated frontend team** — There are frontend-specific developers who don't handle backend
2. **Mobile development started** — React Native / Flutter needs stable API endpoints
3. **Performance requirement** — Inertia server rendering is insufficient (concurrent users > 500)
4. **Third-party integration** — SIAD or external systems need API access
5. **Team size > 5** — Separation of concerns becomes a necessity

### Porting Step-by-Step

```
Phase 2 Porting Plan (estimated: 1-2 sprint / 1-2 weeks)

Sprint N:
  ├── Create Next.js project + copy React components from resources/js
  ├── Setup Sanctum token auth in API
  ├── Update CORS to allow Next.js origin
  └── Deploy Next.js to Vercel / Cloudflare Pages

Sprint N+1:
  ├── Testing parity: Inertia pages vs Next.js pages
  ├── Deprecate web.php routes
  ├── Update deployment pipeline
  └── Documentation update
```

### Risk Mitigation

| Risk | Impact | Mitigation |
|------|--------|------------|
| Service Layer not used consistently | High | Code review mandatory: controllers only call services |
| API controller not tested | Medium | Write API controller together with Web controller |
| React components different framework | Medium | Avoid Inertia-specific API in React components (use tanstack-query) |
| Sanctum session-to-token migration | Low | Sanctum supports dual mode from the start |

## Consequences

### Pros
- **Zero rewrite** — React components, services, models, migrations all reused
- **Gradual migration** — Can be done per feature, not big bang
- **API already exists from MVP** — Mobile development not blocked
- **Low risk** — Team is already familiar with the same codebase

### Cons
- **Double controller** — Maintenance overhead (Web + API controller for the same feature)
- **Service Layer requires discipline** — Must be code reviewed to ensure no logic in controllers
- **Inertia-specific code** — Some code (Inertia::render, form helper) is only in Web controller

---

**Last Updated:** 2026-06-30
