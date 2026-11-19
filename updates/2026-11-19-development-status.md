---
schema_version: 1
type: general
date: 2026-11-19
title: "Five months on: validation wired, PD3 in repo, production still ahead"
tags:
  - air-quality
  - urban-planning
  - interoperability
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/TODO"
  - "https://github.com/LioncodeYourITPeople/ldt4ssc-geotwin/blob/main/docs/status.md"
---

Since the October status note, engineering focused on programme
deliverables, operator UX, and pre-production hardening. An updated
snapshot is in [docs/status.md](../docs/status.md).

## Landed in the repository

- PD3 scope and architecture under `docs/pd3/`, with EU (Hetzner)
  hosting written into platform docs.
- Validation steps 1–2: smoke, performance budgets, Playwright critical
  path, and CI coverage.
- Email delivery module queued beside scenario jobs; SMTP for
  municipalities still to be switched on in production.
- Vulnerable facilities from municipal GIS; CAMS backfill quality fixes;
  admin user management; full-dashboard accessibility audit path.
- Operations UI for jobs, audit, health, tools, catalog, MLOps, and
  backup or restore.

## Not claimed

- No Hetzner production stack and no municipal user-acceptance test.
- No citizen consultation or co-design workshop in repository history.
- Production DR, parallel CAMS slot retrieves, and clear errors on
  incompatible model files remain open.
- Optional migration from the custom model registry to MLflow is still
  a future decision, not an active cut-over.

Open items stay in the implementation repository `TODO`.