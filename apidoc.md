# EUVD API Documentation

All endpoints are `GET`, require no authentication, no custom headers, and no request body.

Base URL: `https://euvdservices.enisa.europa.eu`

Errors are returned as JSON: `{"error": "..."}`. A path that does not exist returns `404`.

## Frontpage

### Show latest vulnerabilities

| Field | Value |
|---|---|
| Endpoint | `/api/lastvulnerabilities` |
| Response limit | Maximum 8 records |

```bash
curl -X GET https://euvdservices.enisa.europa.eu/api/lastvulnerabilities
```

### Show latest exploited vulnerabilities

| Field | Value |
|---|---|
| Endpoint | `/api/exploitedvulnerabilities` |
| Response limit | Maximum 8 records |

```bash
curl -X GET https://euvdservices.enisa.europa.eu/api/exploitedvulnerabilities
```

### Show latest critical vulnerabilities

| Field | Value |
|---|---|
| Endpoint | `/api/criticalvulnerabilities` |
| Response limit | Maximum 8 records |

```bash
curl -X GET https://euvdservices.enisa.europa.eu/api/criticalvulnerabilities
```

## Scores & Filters

### Query vulnerabilities with flexible filters

| Field | Value |
|---|---|
| Endpoint | `/api/search` |
| Response limit | Maximum 100 records per request |

**Parameters:**

- `fromScore` (0–10, e.g. `fromScore=7.5`)
- `toScore` (0–10, e.g. `toScore=10`)
- `fromEpss` (0–100, e.g. `fromEpss=20`)
- `toEpss` (0–100, e.g. `toEpss=90`)
- `fromDate` (YYYY-MM-DD, e.g. `fromDate=2023-01-14`)
- `toDate` (YYYY-MM-DD, e.g. `toDate=2025-01-14`)
- `fromUpdatedDate` (YYYY-MM-DD, e.g. `fromUpdatedDate=2023-01-14`)
- `toUpdatedDate` (YYYY-MM-DD, e.g. `toUpdatedDate=2025-01-14`)
- `product` (string, one product name, e.g. `product=Windows`). Every word must appear in the name, and the last word also matches longer words (`product=Win` finds Windows).
- `vendor` (string, one vendor name, e.g. `vendor=Microsoft`). Matched like `product`. Not a list: `vendor=Siemens,Schneider` looks for a single vendor whose name contains both words.
- `advisory` (string, an advisory ID, e.g. `advisory=cisco-sa-ata19x-multi-RDTEqRsy`). Matched like `product`.
- `assigner` (comma-separated list, e.g. `assigner=mitre` or `assigner=mitre,redhat`)
- `exploited` (true/false, e.g. `exploited=true`)
- `fromKEVDate` (YYYY-MM-DD, e.g. `fromKEVDate=2024-01-01`). Date added to a Known Exploited Vulnerabilities catalogue.
- `toKEVDate` (YYYY-MM-DD, e.g. `toKEVDate=2024-12-31`)
- `text` (keywords, e.g. `text=vulnerability`) — searches across description, EUVD ID, aliases, product name, and vendor name.
- `page` (integer, starts at 0, e.g. `page=2`)
- `size` (integer, default 10, e.g. `size=100` — max)

An invalid parameter returns `400`.

```bash
curl -X GET "https://euvdservices.enisa.europa.eu/api/search?fromScore=0&toScore=10"
```

## Specific Resources

### Show EUVD by ID

| Field | Value |
|---|---|
| Endpoint | `/api/enisaid` |

**Parameters:**

- `id` (string, an EUVD ID or a vulnerability ID such as a CVE, e.g. `id=EUVD-2025-4893` or `id=CVE-2024-3400`)

Returns `404` if no EUVD matches the ID.

```bash
curl -X GET "https://euvdservices.enisa.europa.eu/api/enisaid?id=CVE-2024-3400"
```

### Show advisory by ID

| Field | Value |
|---|---|
| Endpoint | `/api/advisory` |

**Parameters:**

- `id` (string, e.g. `id=oxas-adv-2024-0002`)

Returns `404` if no advisory matches the ID.

```bash
curl -X GET "https://euvdservices.enisa.europa.eu/api/advisory?id=cisco-sa-ata19x-multi-RDTEqRsy"
```

## Data Downloads

### Download CVE-to-EUVD ID Mapping (CSV)

| Field | Value |
|---|---|
| Endpoint | `/api/dump/cve-euvd-mapping` |
| Response limit | Full dataset (CSV with columns: `euvd_id`, `cve_id`). Contains only records linked to published CVEs. Updated daily at 07:00 UTC. |

```bash
curl -X GET https://euvdservices.enisa.europa.eu/api/dump/cve-euvd-mapping
```

[Download Latest CSV](https://euvdservices.enisa.europa.eu/api/dump/cve-euvd-mapping)

### Download KEV Dump (JSON)

| Field | Value |
|---|---|
| Endpoint | `/api/kev/dump` |
| Response limit | Full dataset (JSON). Consolidated Known Exploited Vulnerabilities from CISA KEV and ENISA EU KEV sources. Updated daily at 07:00 UTC. |

**Response fields:**

- `cveId` — CVE identifier (e.g. `CVE-2021-22555`)
- `euvdId` — EUVD identifier (e.g. `EUVD-2021-9696`)
- `dateAdded` — Earliest date the CVE was added across all KEV sources (format: YYYY-MM-DD)
- `sources` — List of KEV sources that include this CVE (e.g. `cisa_kev`, `eukev_kev`)

```bash
curl -X GET https://euvdservices.enisa.europa.eu/api/kev/dump
```

[Download Latest JSON](https://euvdservices.enisa.europa.eu/api/kev/dump)
