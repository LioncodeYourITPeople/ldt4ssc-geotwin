---
schema_version: 1
type: milestone
date: 2026-11-18
title: "Validation steps 1–2: API smoke, performance budgets, Playwright path"
tags:
  - air-quality
  - interoperability
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/Validation.md"
---

Before municipal deployment, the programme asks for integration testing
and performance checks. Those steps are now spelled out and automated
in the implementation repository.

## What we added

- Hot-endpoint smoke tests for catalog, map, LDES, health, and JSON-LD.
- Scripts and Make targets for live-stack smoke and median latency
  budgets on critical routes.
- Playwright critical-path and accessibility suites for the dashboard,
  wired into CI with mock authentication.
- A sign-off checklist that still leaves step 3 — Hetzner production
  deploy and UAT — open.

## What this does not prove

Passing CI does not replace a full Compose stack on staging or a
municipal user-acceptance test. Disaster recovery and production
monitoring remain on the `TODO` list.