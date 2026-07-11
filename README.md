# AISHub (aishub)

AISHub is a cooperative AIS (Automatic Identification System) data sharing network for vessel tracking. Members who contribute a raw NMEA AIS feed from their own receiver (via UDP) get free access in return - a real-time aggregated feed from 1,500+ stations across 80 countries, plus an HTTP web service that returns vessel positions and station metadata as XML, JSON, or CSV. There is no pay-for-access tier; API credentials are earned by sharing a feed that meets coverage and uptime quality thresholds.

**Access model (important):** this is not an open or paid public API. To get a username for the web service you must operate an AIS receiver and stream at least one raw NMEA feed to AISHub over UDP. API credentials are granted once your feed demonstrates coverage of at least 10 vessels and at least 90% uptime over a rolling 7-day period, with message delays under 10 seconds. In exchange, access to the aggregated data is free.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/aishub/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/aishub/refs/heads/main/apis.yml)

## Tags

- Vessel Tracking
- Maritime
- AIS
- Shipping
- Geospatial
- Data Sharing

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### AISHub Vessel Positions API

Returns the latest known position and voyage data for vessels tracked by the AISHub network - MMSI, coordinates, course, speed, heading, navigational status, IMO, name, callsign, ship type, dimensions, draught, destination, and ETA. Supports bounding box (`latmin`/`latmax`/`lonmin`/`lonmax`), MMSI and IMO filters, a maximum position age `interval`, XML/JSON/CSV output, and optional ZIP/GZIP/BZIP2 compression. Authenticated by member `username`.

- **Human URL:** [https://www.aishub.net/api](https://www.aishub.net/api)
- **Base URL:** `https://data.aishub.net`
- **Endpoint:** `GET /ws.php`

#### Tags

- Vessel Tracking
- AIS
- Positions
- Maritime

#### Properties

- [Documentation](https://www.aishub.net/api)
- [OpenAPI](openapi/aishub-openapi.yml)
- [Postman Collection](collections/aishub.postman_collection.json)

### AISHub Stations API

Returns metadata about the receiving stations that make up the AISHub network, filterable by station `id`, with the same XML/JSON/CSV output and compression options as the vessel positions endpoint. Authenticated by member `username`.

- **Human URL:** [https://www.aishub.net/api](https://www.aishub.net/api)
- **Base URL:** `https://data.aishub.net`
- **Endpoint:** `GET /stations.php`

#### Tags

- Stations
- Receivers
- AIS
- Network

#### Properties

- [Documentation](https://www.aishub.net/api)
- [Stations Portal](https://www.aishub.net/stations)
- [OpenAPI](openapi/aishub-openapi.yml)
- [Postman Collection](collections/aishub.postman_collection.json)

## Other Data Surfaces (not modeled as APIs)

- **Raw NMEA aggregated feed** - contributors can receive the aggregated raw AIS stream in NMEA format over TCP/UDP socket connections. This is a raw protocol feed, not an HTTP or WebSocket API, so it is noted here and in `review.yml` but not modeled in the OpenAPI.
- **AIS Dispatcher** - AISHub's free Windows/Linux application for forwarding receiver data to the network.

## Common Properties

- [Website](https://www.aishub.net/)
- [Documentation](https://www.aishub.net/api)
- [Join / Sign Up](https://www.aishub.net/join-us)
- [Coverage Map](https://www.aishub.net/coverage)
- [Plans](plans/aishub-plans-pricing.yml)
- [Rate Limits](rate-limits/aishub-rate-limits.yml)
- [Fin Ops](finops/aishub-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
