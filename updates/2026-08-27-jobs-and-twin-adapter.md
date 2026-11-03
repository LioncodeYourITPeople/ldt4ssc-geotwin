---
schema_version: 1
type: milestone
date: 2026-08-27
title: "Scenario runs go through a job queue, and the twin adapter speaks v2"
tags:
  - air-quality
  - urban-planning
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/jobs/README.md"
---

August connected the platform to the twin-manager contract and stopped
scenario runs from blocking the API process.

## Twin adapter

An adapter module, brought across from twin-manager, implements the v1
contract and then the v2 contract: platform options, analytics, and map
selection. The dashboard ML pages were rebuilt around that contract.

## Job queue

Scenario runs are deferred to a Procrastinate worker backed by
Postgres (pull request #4). The same queue is visible from the
dashboard. A setup script starts the API, the worker, and the
dashboard together.

## Alerts

The alerts page was removed and then restored in the same month, with
a governance seed for alert rules. Active alerts can be joined onto
vulnerability facilities on the map.
