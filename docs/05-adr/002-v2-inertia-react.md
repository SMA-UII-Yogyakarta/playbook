# ADR 002-v2: InertiaJS + React From MVP

**Date:** 2026-06-30  
**Status:** Accepted  
**Deciders:** Sandikodev  
**Supersedes:** [ADR-002](002-livewire-first.md)

---

## Context

The initial decision (ADR-002) chose Livewire 3 for MVP due to low learning curve and fast development. After further evaluation, the team decided on a revision because:

1. **Stakeholder direction (Pak Mahfud)** — wants a modern application with an architecture that can be ported to mobile (React Native / Flutter) and a separate web app (Next.js) in the future.
2. **Team composition changed** — Azis joined as Learning Mentor, enabling Fathan & Ihsan to learn React/TypeScript faster with direct mentoring.
3. **Porting cost** — Building with Livewire then migrating to React/Next.js in Phase 2 requires a complete frontend rewrite. Starting with Inertia+React eliminates the porting cost.
4. **Ecosystem maturity** — InertiaJS 3 + React 19 + TypeScript 5.7 is already stable and mature for production.

## Decision

**Phase 1 (MVP):** InertiaJS 3 + React 19 + TypeScript 5.7 + Tailwind CSS 4 + Vite 8  
**Phase 2 (Dedicated Backend):** Laravel API-only + Next.js (Web App) + React Native / Flutter (Mobile)

### Phase 1 Architecture

```
Browser
  │
  ├── InertiaJS 3 (bridge)
  │     ├── Server-side: Laravel routing + controller
  │     └── Client-side: React 19 + TypeScript
  │
  ├── Tailwind CSS 4 (styling)
  ├── Vite 8 (bundler)
  └── Bun (package manager)
```

### Service Layer Pattern
All business logic is written in `app/Services/` so that:
- Controller stays thin — just call the service
- API routes (`/api/*`) can reuse the same service
- Porting to Phase 2 just replace controller → API controller

## Rationale

### Why Inertia + React, Not Livewire?

| Aspect | Livewire 3 | InertiaJS + React |
|--------|-----------|-------------------|
| **Learning curve** | Low (Blade familiar) | Medium (React new) |
| **Porting to Next.js** | Total rewrite | Partial (move routing) |
| **Type safety** | None (Blade/PHP) | Full TypeScript |
| **Component reusability** | Limited to Laravel | Can share with Next.js |
| **Mobile API reuse** | Not directly | Direct (service layer) |
| **Ecosystem** | Laravel-centric | React universal |

### Why React, Not Vue/Nuxt?

1. **Market dominance** — React is most widely used → easier to find references, libraries, hiring
2. **InertiaJS first-class support** — InertiaJS was created by the creator of Laravel, React support is on par with Vue
3. **Mobile pathway** — React Native is the most natural mobile choice from React
4. **Team preference** — Sandikodev and Azis are more familiar with React than Vue

### Why TypeScript from the Start?

1. **Type safety** — Prevents common runtime errors in JS (undefined is not a function, wrong prop types)
2. **IDE support** — Autocomplete, refactoring, type checking in VS Code
3. **Learning investment** — Fathan & Ihsan learn TypeScript from the start, not migrate later
4. **Next.js readiness** — Next.js is TypeScript-based by default

## Consequences

### Pros
- Zero rewrite when porting to Next.js / React Native — reuse React components
- Service layer can be used by API routes and Inertia controllers
- TypeScript provides a safety net for junior developers
- Vite 8 provides HDR (Hot Data Replacement) for React

### Cons
- Higher learning curve for Fathan & Ihsan (must learn React + TS + Inertia)
- InertiaJS adds one abstraction layer (compared to Livewire directly with Blade)
- Slower development at the start due to learning phase

### Mitigation
- Azis as Learning Mentor will do pair programming with Fathan & Ihsan
- Sprint 1 is focused on setup and learning, not feature building
- Learning path adjusted: React hooks first, Inertia later

---

**Last Updated:** 2026-06-30
