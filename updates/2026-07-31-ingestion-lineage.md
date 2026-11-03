---
schema_version: 1
type: general
date: 2026-07-31
title: "Ingestion, LDES views, and provenance tightened up"
tags:
  - air-quality
  - data-integration
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/ingestion/README.md"
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/LDES.md"
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/Provenance.md"
---

The last week of July was spent making the open-data path something we
can trust and trace, rather than adding a new service.

## Ingestion

- CAMS air quality and CAMS weather are separate graphs, so a weather
  failure does not block pollutant history.
- Sentinel STAC metadata and openEO indicator composites (NDVI, NO2,
  aerosol, land surface temperature) have a path through CDSE.
- Reference geodata (OSM roads, EEA, INSPIRE boundaries) lands in
  PostGIS, with an OSM fallback when a source is awkward.
- Scorpio entity locations sync into PostGIS for the map.

## Traceability

- Sentinel STAC sidecars and indicator rasters are exposed as
  TREE-fragmented Linked Data Event Streams.
- Catalog datasets expose a compact W3C PROV-O bundle: the dataset, the
  pipeline activity, the upstream source, and the platform as agent.
- Inference entities carry the run id, model version, and a short
  provenance summary.

This is partial lineage, not a triple store and not a finished MIM8
implementation.
