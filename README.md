# Australia Administrative Divisions / Australia



## Overview

| Item | Details |
|------|---------|
| State/Territory | 8 |
| Local Government Area | 550 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-07 |
| Website | [openadmindata.org/au](https://openadmindata.org/au/) |
| API | [openadmindata.org/api/au](https://openadmindata.org/api/au/) |

## Browse by State/Territory

| # | State/Territory | Local Government Areas | Link |
|---|----|----|------|
| 1 | Western Australia | 136 | [Browse](divisions/western-australia-au01/) |
| 2 | Queensland | 72 | [Browse](divisions/queensland-au02/) |
| 3 | Australian Capital Territory | 0 | [Browse](divisions/australian-capital-territory-au03/) |
| 4 | Victoria | 77 | [Browse](divisions/victoria-au04/) |
| 5 | South Australia | 69 | [Browse](divisions/south-australia-au05/) |
| 6 | Northern Territory | 16 | [Browse](divisions/northern-territory-au06/) |
| 7 | New South Wales | 151 | [Browse](divisions/new-south-wales-au07/) |
| 8 | Tasmania | 29 | [Browse](divisions/tasmania-au08/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-state.json](data/all-state.json) | JSON | All 8 state/territory records |
| [all-lga.json](data/all-lga.json) | JSON | All 550 local government area records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
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
console.log(`Total: ${data.length} state/territorys`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=state/territory, 2=local government area |
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
```

Local Government Areas are listed inline in each state/territory's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-state/territory links
- [Per-state/territory data](docs/llms-full/) — Full data by state/territory

## Citation

```
Australia Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/australia-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
