# AISHub (aishub)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
