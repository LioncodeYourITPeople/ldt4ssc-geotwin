# Data models

GeoTwin ELBG publishes NGSI-LD entities through Scorpio using
[FIWARE Smart Data Models](https://www.fiware.org/smart-data-models/).
The model notes and the Python schemas live in the
[implementation repository](https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/tree/main/docs/smart-data-models).
They are not copied here.

## Models in use

| Model | Role | Main sources |
| --- | --- | --- |
| AirQualityObserved | CAMS observations, EEA comparison, LSTM 48–72 h forecasts | Copernicus CAMS, Sentinel-5P, forecast pipeline |
| WeatherObserved | Weather covariates for downscaling and scenarios | CAMS meteorology |
| PointOfInterest | Vulnerable facilities and Random Forest risk scores | Municipal GIS, OSM, INSPIRE |

WaterLevelObserved (Nestos river sensors) is deferred. The current
services do not require a new local sensor network.

## GeoTwin extension

Extra attributes use the namespace `https://geotwin-elbg.example/ns#`.

| Attribute | Type | Meaning |
| --- | --- | --- |
| `municipality` | string | Municipality name |
| `pilotCase` | `nestos` or `sandanski` | Which pilot the entity belongs to |
| `countryCode` | `GR` or `BG` | Country |
| `dataSource` | `CAMS`, `EEA`, `forecast`, `municipal`, or `iot` | Where the value came from |
| `isForecast` | boolean | `true` on LSTM outputs |
| `forecastHorizonHours` | integer | Lead time, for example 48 or 72 |
| `facilityType` | `school`, `hospital`, `care_home`, `park`, or `monitoring_station` | Kind of place |
| `vulnerabilityScore` | float from 0 to 1 | Random Forest score |

Entity ids follow `urn:ngsi-ld:{type}:GeoTwin:local:{local_id}`.

Definitions and validation rules:
[extensions](https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/storage/broker/extensions.py),
[AirQualityObserved](https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/smart-data-models/AirQualityObserved.md),
[WeatherObserved](https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/smart-data-models/WeatherObserved.md),
[PointOfInterest](https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/smart-data-models/PointOfInterest.md),
[validation rules](https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/smart-data-models/validation-rules.md).
