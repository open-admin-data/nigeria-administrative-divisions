# Nigeria Administrative Divisions / Nigeria



## Overview

| Item | Details |
|------|---------|
| State | 37 |
| Local Government Area | 774 |
| Ward | 8,799 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-26 |

## Browse by State

| # | State | Local Government Areas | Wards | Link |
|---|----|----|----|------|
| 1 | Abia | 17 | 184 | [Browse](divisions/abia-ng001/) |
| 2 | Adamawa | 21 | 226 | [Browse](divisions/adamawa-ng002/) |
| 3 | Akwa Ibom | 31 | 329 | [Browse](divisions/akwa-ibom-ng003/) |
| 4 | Anambra | 21 | 326 | [Browse](divisions/anambra-ng004/) |
| 5 | Bauchi | 20 | 212 | [Browse](divisions/bauchi-ng005/) |
| 6 | Bayelsa | 8 | 105 | [Browse](divisions/bayelsa-ng006/) |
| 7 | Benue | 23 | 264 | [Browse](divisions/benue-ng007/) |
| 8 | Borno | 27 | 302 | [Browse](divisions/borno-ng008/) |
| 9 | Cross River | 18 | 193 | [Browse](divisions/cross-river-ng009/) |
| 10 | Delta | 25 | 270 | [Browse](divisions/delta-ng010/) |
| 11 | Ebonyi | 13 | 171 | [Browse](divisions/ebonyi-ng011/) |
| 12 | Edo | 18 | 192 | [Browse](divisions/edo-ng012/) |
| 13 | Ekiti | 16 | 177 | [Browse](divisions/ekiti-ng013/) |
| 14 | Enugu | 17 | 260 | [Browse](divisions/enugu-ng014/) |
| 15 | Federal Capital Territory | 6 | 62 | [Browse](divisions/federal-capital-territory-ng015/) |
| 16 | Gombe | 11 | 114 | [Browse](divisions/gombe-ng016/) |
| 17 | Imo | 27 | 305 | [Browse](divisions/imo-ng017/) |
| 18 | Jigawa | 27 | 287 | [Browse](divisions/jigawa-ng018/) |
| 19 | Kaduna | 23 | 255 | [Browse](divisions/kaduna-ng019/) |
| 20 | Kano | 44 | 473 | [Browse](divisions/kano-ng020/) |
| 21 | Katsina | 34 | 361 | [Browse](divisions/katsina-ng021/) |
| 22 | Kebbi | 21 | 225 | [Browse](divisions/kebbi-ng022/) |
| 23 | Kogi | 21 | 229 | [Browse](divisions/kogi-ng023/) |
| 24 | Kwara | 16 | 164 | [Browse](divisions/kwara-ng024/) |
| 25 | Lagos | 20 | 233 | [Browse](divisions/lagos-ng025/) |
| 26 | Nasarawa | 13 | 170 | [Browse](divisions/nasarawa-ng026/) |
| 27 | Niger | 25 | 274 | [Browse](divisions/niger-ng027/) |
| 28 | Ogun | 20 | 236 | [Browse](divisions/ogun-ng028/) |
| 29 | Ondo | 18 | 203 | [Browse](divisions/ondo-ng029/) |
| 30 | Osun | 30 | 361 | [Browse](divisions/osun-ng030/) |
| 31 | Oyo | 33 | 363 | [Browse](divisions/oyo-ng031/) |
| 32 | Plateau | 17 | 217 | [Browse](divisions/plateau-ng032/) |
| 33 | Rivers | 23 | 319 | [Browse](divisions/rivers-ng033/) |
| 34 | Sokoto | 23 | 244 | [Browse](divisions/sokoto-ng034/) |
| 35 | Taraba | 16 | 168 | [Browse](divisions/taraba-ng035/) |
| 36 | Yobe | 17 | 178 | [Browse](divisions/yobe-ng036/) |
| 37 | Zamfara | 14 | 147 | [Browse](divisions/zamfara-ng037/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-state.json](data/all-state.json) | JSON | All 37 state records |
| [all-lga.json](data/all-lga.json) | JSON | All 774 local government area records |
| [all-ward.json](data/all-ward.json) | JSON | All 8,799 ward records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-state.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['lga']} local government areas")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-state.json", "utf-8"));
console.log(`Total: ${data.length} states`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=state, 2=local government area, 3=ward |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{state-slug}/
divisions/{state-slug}/{lga-slug}/
```

Wards are listed inline in each local government area's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-state links
- [Per-state data](docs/llms-full/) — Full data by state

## Citation

```
Nigeria Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/nigeria-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
