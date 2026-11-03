---
schema_version: 1
type: lesson
date: 2026-07-17
title: "A small cross-border pilot did not need the full integration stack"
tags:
  - interoperability
  - data-integration
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/Services.md"
---

We started from a familiar digital-twin bill of materials: NiFi for
ingestion, GeoServer for maps, CKAN for the catalog, the Eclipse
Dataspace Connector for sharing, and Kubernetes for deployment. Within
the first month each of those was removed. The pilot still covers
NGSI-LD, a catalog, cross-border grants, and maps.

## What replaced them

- Bonobo graphs, run as command-line jobs and from cron, ingest CAMS,
  Sentinel, EEA, OSM, and Eurostat. There is no separate ETL service.
- The catalog is a DCAT-AP 3.0 export from the FastAPI app.
- Cross-border sharing is an ODRL policy check and a grant table in
  Postgres, not a second connector runtime.
- Map layers are PostGIS tables and a small tile endpoint. GeoServer
  was not earning its operational cost for two municipalities.
- Docker Compose and a setup script are the deployment unit. Kubernetes
  is not in the repository.

## What we would repeat

Pick the interoperability surface first (NGSI-LD, DCAT-AP, ODRL,
OAuth2), then the smallest process that implements it. Add a dedicated
product only when that process cannot do the job. For Nestos and
Sandanski, the smaller stack has been enough to build both services.
