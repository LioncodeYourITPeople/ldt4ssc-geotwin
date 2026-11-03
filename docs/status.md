# Status as of 6 October 2026

Snapshot of GeoTwin ELBG development. The dated record is in
[`updates/`](../updates/). The implementation is
[GeoTwin-ELBG](https://github.com/LioncodeYourITPeople/GeoTwin-ELBG),
with history from 18 June 2026 to 6 October 2026.

The pilot itself runs until 30 November 2027. This page describes the
software, not a production service in Nestos or Sandanski.

## What the platform contains

Both services run on a local Docker Compose stack.

**Shared platform.** Postgres with TimescaleDB and PostGIS, Garage
object storage, Scorpio as the NGSI-LD broker, Keycloak realms
`nestos` and `sandanski`, a FastAPI API, and a Next.js dashboard.
Ingestion is Bonobo graphs (CAMS air quality, CAMS weather, Sentinel
STAC, openEO indicators, EEA, OSM, Eurostat, reference geodata) plus
cron. A Procrastinate worker runs scenario jobs. The catalog speaks
DCAT-AP 3.0. Satellite series have LDES views. Datasets and inference
entities carry a compact PROV-O bundle.

**Service 1 — predictive environmental health.** LSTM forecasts at a
48–72 hour horizon, Random Forest risk scores, statistical
downscaling, SHAP attributions, model cards on the catalog, a fairness
check, and vulnerability facilities on the map. The EEA comparison
report still uses synthetic references until live station measurements
are connected.

**Service 2 — policy what-if.** Scenarios, sensitivity studies with
confidence intervals, and a human review step before a recommendation
is treated as a decision. The dashboard is available in English, Greek,
and Bulgarian, with manuals in those languages.

**Interoperability evidence.** An internal MIMs Plus review on
5–6 October 2026 marked MIM0 (accessing data) and MIM2 (representing
data) as met. Other MIMs are not closed in that tracker.

NGSI-LD entities use AirQualityObserved, WeatherObserved, and
PointOfInterest, plus a small GeoTwin extension. See
[`data-models/README.md`](../data-models/README.md).

## What is not live

- No IONOS deployment and no municipal acceptance test.
- No co-design workshop or citizen consultation is recorded in the
  repository.
- Production disaster recovery is still open: off-site backups,
  monitoring alerts, Keycloak production mode, and a stated recovery
  point and recovery time.
- CAMS backfill inside one time slot is still sequential.
- Loading an incompatible older model file does not yet return a clear
  error.
- The later communication and sustainability report is not written.

Open engineering items are listed in the implementation repository
`TODO`.
