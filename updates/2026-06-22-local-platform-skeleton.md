---
schema_version: 1
type: milestone
date: 2026-06-22
title: "Local platform skeleton is running"
tags:
  - air-quality
  - data-integration
  - interoperability
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG"
---

The first working stack for GeoTwin ELBG is up in local Docker. It is
the base both municipalities will share: storage, identity, a context
broker, an API, and a dashboard.

## What is in place

- Postgres with TimescaleDB and PostGIS, Garage for object storage, and
  the Scorpio NGSI-LD broker.
- Keycloak for sign-in, a FastAPI service, and a Next.js dashboard.
- Bonobo graphs for external data, plus a small cron runner for
  scheduled jobs.
- Backup scripts for Postgres, Scorpio, and Garage.

## What we left out

The first sketches included Apache NiFi, Apache Superset, CKAN, the
Eclipse Dataspace Connector, and Kubernetes. Those came out in the same
week. Ingestion is Bonobo graphs run as jobs. Sharing and maps are
handled inside the API, which we describe in later updates.

The stack is for local development. It is not deployed for Nestos or
Sandanski yet.
