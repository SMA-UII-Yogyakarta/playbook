# Role Template — [Nama Role]

> Template untuk mendefinisikan role baru di ekosistem PT Koneksi Jaringan Indonesia.
> Copy file ini, rename sesuai role, dan isi setiap seksi.

---

## Metadata

| Attribute | Value |
|---|---|
| **Role ID** | `role-name` (slug, lowercase, use hyphens) |
| **Created** | YYYY-MM-DD |
| **Maintainer** | PIC Name |
| **Level** | Junior / Mid / Senior / Lead / Stakeholder |

---

## Summary

[Describe this role in 2-3 sentences. Who they are, what they do, in which project.]

---

## Responsibilities

### 1. [Area 1 — Time Allocation]
- [Task detail]
- [Task detail]

### 2. [Area 2 — Time Allocation]
- [Task detail]
- [Task detail]

---

## AI Instructions

> This section is read by the AI Agent every time it assists this role.
> Write in English, use direct command sentences.

### Role Context
- [What this role is responsible for]
- [What the AI should prioritize when assisting]

### How AI Should Help
- [Specific instructions on output format]
- [Language to use]
- [Things to avoid]

### Constraints
- [What the AI is not allowed to do]
- [Information access limitations]

---

## Tool Access

| Tool | Access Level | Notes |
|---|---|---|
| GitHub (source code) | read / write / admin | Project specific |
| GitHub Issues | create / comment / triage | - |
| Trello | view / edit / admin | Board specific |
| Environment (staging) | view / operate | - |
| Environment (production) | view / operate | - |

---

## Expected Outputs

- [Output 1]
- [Output 2]
- [Output 3]

---

## Growth Path

> For growth-oriented roles (junior → senior), write possible transitions.

| Level | Target Role | Prerequisites |
|---|---|---|
| Current | [Current role] | - |
| Next | [Next role] | [Skill / time] |

---

## Related Roles

- [Role lain yang sering berinteraksi]
- [Role lain dengan tanggung jawab tumpang tindih]

---

## Example Usage in opencode.json

```json
{
  "instructions": [
    "~/.openkb/PERSONAL/{{username}}/profile.md",
    "~/.openkb/ROLES/nama-role.md"
  ]
}
```

---

*This template is part of the [Koneksi playbook](../../README.md).*
