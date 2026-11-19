---
schema_version: 1
type: milestone
date: 2026-11-18
title: "Portable email layer for alerts and governance events"
tags:
  - air-quality
  - urban-planning
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/tree/main/vendor/messaging"
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/Services.md"
---

Both municipalities asked for email in addition to in-app alerts. The
platform now ships a generic messaging module and GeoTwin wiring that
queues delivery through the same Procrastinate worker as scenarios.

## Behaviour

- In-app notifications remain the default path.
- Email jobs mirror selected events when SMTP is configured (Mailtrap
  defaults in local `.env.example`).
- PD3 notes describe production SMTP activation with the municipalities
  during UAT; it is not enabled end-to-end in a live pilot deploy yet.