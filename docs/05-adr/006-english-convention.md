# ADR 006: English-First Convention for Code and Documentation

**Date:** 2026-07-01  
**Status:** Accepted  
**Deciders:** Sandikodev

---

## Context

The SMART Absen codebase and documentation have historically used a mix of Indonesian and English across all repositories:

- **Code:** Variable names, function names, comments, and commit messages alternate between languages (e.g., `getSiswa()`, `buatLaporan()`, `// ambil data user`)
- **Documentation:** ADRs, README, and inline docs are predominantly Indonesian
- **AI instructions:** `agent-rules.md` explicitly states _"Gunakan bahasa Indonesia"_ as a rule
- **UI text:** Indonesian labels mixed with English placeholder text

This inconsistency creates several problems:

1. **Reduced professionalism** — Mixed-language codebases appear less polished to external contributors and clients
2. **Limited accessibility** — Future contributors who do not speak Indonesian cannot read comments, docs, or commit history
3. **Tooling friction** — Linters, AI code assistants, and translation-aware tools work best with a single language
4. **Ecosystem mismatch** — Laravel, React, TypeScript, PostgreSQL, and all major frameworks use English as their canonical language. Mixing languages breaks convention and makes the code harder to compare with official docs and community examples
5. **Open-source barrier** — Mixed-language repos deter international contributions

## Decision

All project artifacts will use **English** as the primary language. This applies to:

| Artifact | Language | Notes |
|----------|----------|-------|
| **Source code** (PHP, TS, JS) | English | Classes, methods, variables, comments |
| **Database** (migrations, seeders) | English | Column names, table names, index names |
| **Configuration files** | English | `.env`, `config/*.php`, `composer.json`, `package.json` |
| **Commit messages** | English | Conventional Commits format (already English — maintain) |
| **Pull requests & code review** | English | Titles, descriptions, comments |
| **Documentation** (ADRs, README, wiki) | English | All technical documentation |
| **AI instructions** (agent-rules.md, AGENTS.md) | English | Prompts, rules, conventions |
| **UI text** (React components) | English | User-facing labels, error messages, tooltips |
| **Communication** (Slack, Linear, Trello) | English | Technical discussions, task descriptions, comments |

**Indonesian is only acceptable in the following cases:**

1. **External stakeholder communication** — Reports or presentations for stakeholders who prefer Indonesian
2. **Verbal team discussions** — Internal conversations among Indonesian-speaking team members
3. **Domain terms without English equivalent** — If a domain-specific term has no clear English translation, it must be documented in `glossary.md` with a rationale

## Implementation

### Phase 1 — Immediate (Sprint N)

- Update `agent-rules.md` in all 3 repos to replace _"Gunakan bahasa Indonesia"_ with English-first convention
- This ADR becomes the governing reference

### Phase 2 — Incremental (Sprint N+1 onward)

- Convert existing comments and docblocks to English during normal development work (no dedicated "translation sprint")
- New code must be English from day 1 (enforced in code review)
- Existing variable/function names in Indonesian will be renamed when the surrounding code is modified (refactor-on-touch)

### Phase 3 — Documentation

- ADRs and README files may remain in Indonesian until they are next updated; at that point they should be written in English or migrated

## Consequences

### Pros

- **Professional standard** — Aligns with industry best practices for open-source and commercial projects
- **International accessibility** — Any developer worldwide can read the codebase, submit PRs, or contribute
- **Ecosystem consistency** — Matches Laravel, React, TypeScript, and PostgreSQL conventions exactly
- **Better tooling** — AI assistants, linters, static analysis, and translation tools work optimally with one language
- **Simpler onboarding** — New team members only need to learn the code, not the language switch
- **Open-source ready** — No language barrier for potential external contributors

### Cons

- **Learning curve** — Team members less comfortable with English may write code or docs more slowly initially
- **Documentation speed** — Writing docs in a non-native language can reduce output velocity in the short term
- **Stakeholder translations** — Reports for Indonesian-speaking stakeholders may require separate translation effort
- **Legacy inconsistency** — Old Indonesian comments and names will coexist with new English code during the transition

---

**Last Updated:** 2026-07-01
