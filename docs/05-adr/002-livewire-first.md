# ADR 002: Livewire First, React Later

**Date:** 2026-06-21  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

Kita perlu memutuskan stack frontend untuk MVP (Bulan 1):
- Opsi 1: Laravel Blade + Livewire
- Opsi 2: Laravel API + React/Next.js
- Opsi 3: Laravel API + Vue/Nuxt

## Decision

**Phase 1 (MVP — Bulan 1):** Laravel Blade + Livewire 3  
**Phase 2 (Bulan 2+):** Laravel API + Next.js 14

## Rationale

### Phase 1: Livewire

**Alasan:**
1. **Learning curve rendah** — Fathan & Ihsan sudah familiar Laravel
2. **Development cepat** — Tidak perlu terpisah backend/frontend
3. **Team kecil** — 2 developer, tidak perlu separation of concern ketat
4. **Simpler deployment** — Satu deploy, selesai
5. **Less complexity** — Tidak perlu manage API versioning, CORS, auth token

### Phase 2: Next.js

**Trigger migration:**
- UI complexity meningkat
- Perlu PWA capability
- Performance requirement lebih tinggi
- Team bertambah (dedicated frontend developer)

## Consequences

### Phase 1 (Livewire)

**Pros:**
- MVP selesai dalam 1 bulan
- Developer fokus business logic, bukan API integration
- Simpler debugging

**Cons:**
- Coupling backend-frontend
- Migration effort nanti

### Phase 2 (Next.js)

**Pros:**
- Separation of concern
- Better performance (SSR, SSG)
- PWA capable
- Mobile app dapat reuse API

**Cons:**
- Migration effort
- Learning curve untuk tim

---

**Last Updated:** 2026-06-21