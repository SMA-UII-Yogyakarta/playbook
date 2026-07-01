# Decision Log — Playbook

Format:
```
## YYYY-MM-DD — [Decision Title]
**Status**: [Proposed / Accepted / Deprecated]
**Decider**: [Name]
**Context**: [Background / problem]
**Decision**: [What was decided]
**Consequences**: [Positive & negative impacts]
```

---

## 2026-06-25 — Dynamic Role Definitions via ROLES/ Directory

**Status**: Accepted
**Decider**: Sandikodev
**Context**: Need a standard way to define dynamic roles — reusable across projects, loadable by AI Agent, and evolvable as the team grows.
**Decision**: Create a `ROLES/` directory in the playbook with a template (_TEMPLATE.md) and specific roles. Each role has AI Instructions that can be read by Opencode, Claude Code, Cursor, and other tools via `~/.openkb/ROLES/`.
**Consequences**:
- (+) Roles can be reused across different projects
- (+) AI Agent can behave according to role without reconfiguration
- (-) Requires maintenance to keep roles up-to-date

---

## 2026-06-25 — TACO Protocol for AI Agent Workflow

**Status**: Accepted
**Decider**: Sandikodev
**Context**: Developers use AI Agents (Opencode, Claude Code, Cursor) without a standardized workflow — need a standard flow from Trello → AI → Commit → Output.
**Decision**: Create TACO Protocol (Trello → AI → Commit → Output) as the standard AI Agent workflow. Documentation in WORKFLOWS/ai-agent-workflow.md.
**Consequences**:
- (+) All developers use the same workflow
- (+) Trello + GitHub + AI Agent integration becomes standardized
- (-) Needs team socialization for adoption

---

## 2026-06-25 — Multi-Tool AI Agent Strategy

**Status**: Accepted
**Decider**: Sandikodev
**Context**: The team needs AI Agent tool flexibility — no vendor lock-in to a single platform. Opencode as primary, but needs support for Claude Code, Cursor, Claw Code.
**Decision**: Multi-tool config is stored in each repo: `.opencode/` (opencode), `.cursorrules` (Cursor), `.claude/settings.json` (Claude Code). All tools read context from the same files (`.opencode/SHARED/`, `.openkb/`).
**Consequences**:
- (+) Free to choose tools without losing context
- (+) Anti vendor lock-in (Claw Code as open source option)
- (-) Need to maintain config in 3 different formats
