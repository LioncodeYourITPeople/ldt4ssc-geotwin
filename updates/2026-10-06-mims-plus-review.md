---
schema_version: 1
type: milestone
date: 2026-10-06
title: "MIMs Plus review: accessing and representing data are met"
tags:
  - interoperability
  - data-integration
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/MIMs-Compliance.md"
---

We reviewed the platform against MIMs Plus and recorded the evidence
in the implementation repository (pull request #5). The review uses
the Living-in.EU MIMs Plus checklist (version 8, 2025).

## What is met

MIM0, Accessing Data, is met: JSON over HTTP, a public OpenAPI
description, query parameters on the open endpoints, and NGSI-LD
subscriptions for change notification.

MIM2, Representing Data, is met: documented Smart Data Models
(AirQualityObserved, WeatherObserved, PointOfInterest) with a small
GeoTwin extension, JSON-LD and GeoJSON serialisations, and validation
rules in the broker schemas.

## What this review does not cover

Other MIMs are not marked in that tracker yet. Provenance is still the
partial PROV-O bundle described in July. This is an internal evidence
log. It is not the consortium interoperability self-assessment, and it
does not claim a score.
