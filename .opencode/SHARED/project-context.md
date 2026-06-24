# Project Context — PT Koneksi Jaringan Indonesia Playbook

## Ringkasan
Playbook adalah pusat dokumentasi SOP, workflow, template, ADR, dan role definitions untuk seluruh proyek PT Koneksi Jaringan Indonesia.

## Struktur
```
ROLES/         — Definisi role dinamis (template per role)
WORKFLOWS/     — AI Agent workflow (TACO protocol)
ACCESS/        — Access matrix & outsourced policy
docs/
  01-getting-started/  — Onboarding, environment, team roles
  02-workflow/         — Git, Trello, GitHub, komunikasi
  03-sop/              — Code review, deployment, testing
  04-templates/        — Issue, PR, sprint, user story
  05-adr/              — Architecture Decision Records
  06-learning-path/    — Junior dev roadmap
  07-project/          — MVP scope, sprint plans
```

## Proyek Saat Ini
- **SMART Absen SMA UII** (backend: core.git, entrypoint: aksesekolah.git, power-up: kaede-powerup.git)

## Aturan
1. Setiap role definition harus melalui review sebelum dianggap final
2. Update `docs/07-project/` setiap kali ada sprint baru
3. ADR harus ditulis untuk setiap keputusan arsitektur yang signifikan
4. Template di `docs/04-templates/` harus selalu up-to-date
