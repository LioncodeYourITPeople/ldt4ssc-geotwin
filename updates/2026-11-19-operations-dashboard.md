---
schema_version: 1
type: milestone
date: 2026-11-19
title: "Operations console: jobs, health, audit logs, backup from the UI"
tags:
  - air-quality
  - urban-planning
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/Backup-Retention-DR.md"
---

A concentrated dashboard release turns day-two operations into
first-class UI instead of shell-only Makefile targets.

## What operators can do now

- Inspect Procrastinate job logs, durations, and repo-relative paths;
  cancel long-running jobs when needed.
- Read audit logs and see a colour-coded system health indicator in
  the navigation.
- Launch map workflows, catalog browsing, and an MLOps-style model
  registry view from consolidated tools and home pages.
- Trigger backup and restore flows that were previously documented only
  in the backup runbook.

## Still manual or open

Off-site retention, encryption policy, and production monitoring alerts
are described in the backup document but not signed off for go-live.
Disaster recovery on Hetzner remains a `TODO` item.