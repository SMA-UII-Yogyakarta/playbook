# ADR 002: Livewire First, React Later [SUPERSEDED]

**Date:** 2026-06-21  
**Status:** ❌ **Superseded** — by [ADR-002-v2](002-v2-inertia-react.md) on 2026-06-30  
**Deciders:** Sandikodev

---

## Context

We need to decide the frontend stack for MVP (Month 1):
- Option 1: Laravel Blade + Livewire
- Option 2: Laravel API + React/Next.js
- Option 3: Laravel API + Vue/Nuxt

## Decision (Original — Not Applied)

**Phase 1 (MVP — Month 1):** Laravel Blade + Livewire 3  
**Phase 2 (Month 2+):** Laravel API + Next.js 14

## Rationale

### Phase 1: Livewire

**Reasons:**
1. **Low learning curve** — Fathan & Ihsan are already familiar with Laravel
2. **Fast development** — No need for separate backend/frontend
3. **Small team** — 2 developers, no need for strict separation of concerns
4. **Simpler deployment** — One deploy, done
5. **Less complexity** — No need to manage API versioning, CORS, auth tokens

### Phase 2: Next.js

**Trigger migration:**
- UI complexity increases
- PWA capability needed
- Higher performance requirements
- Team grows (dedicated frontend developer)

## Consequences

### Phase 1 (Livewire)

**Pros:**
- MVP completed within 1 month
- Developer focuses on business logic, not API integration
- Simpler debugging

**Cons:**
- Coupling backend-frontend
- Migration effort later

### Phase 2 (Next.js)

**Pros:**
- Separation of concern
- Better performance (SSR, SSG)
- PWA capable
- Mobile app can reuse API

**Cons:**
- Migration effort
- Learning curve for the team

---

**Last Updated:** 2026-06-21
