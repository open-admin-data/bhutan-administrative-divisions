# Bhutan Administrative Divisions / འབྲུག

Open dataset of Bhutan's administrative hierarchy — 20 dzongkhags (districts) and 205 gewogs (sub-districts). This repository provides structured, bilingual (Dzongkha + English) reference data with geographic coordinates and postal codes at every level. Designed for developers, researchers, government agencies, and AI agents.

Licensed under CC-BY-4.0. Browse the hierarchy through GitHub's folder navigation, download aggregate files in JSON/CSV/NDJSON, or integrate directly via raw URLs.

## Overview

| Item | Details |
|------|---------|
| District | 20 |
| Sub-district | 205 |
| Coordinates | ✅ Included (all levels) |
| Postal Codes | ✅ Included (sub-district level) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-19 |

## Browse by District

| # | District | Sub-districts | Link |
|---|----|----|------|
| 1 | བུམ་ཐང་ (Bumthang) | 4 | [Browse](divisions/bumthang-bt001/) |
| 2 | ཆུ་ཁ (Chhukha) | 11 | [Browse](divisions/chhukha-bt002/) |
| 3 | དར་དཀར་ན་ (Dagana) | 14 | [Browse](divisions/dagana-bt003/) |
| 4 | མགར་ས་ (Gasa) | 4 | [Browse](divisions/gasa-bt004/) |
| 5 | ཧཱ་ (Haa) | 6 | [Browse](divisions/haa-bt005/) |
| 6 | ལྷུན་རྩེ (Lhuentse) | 8 | [Browse](divisions/lhuentse-bt006/) |
| 7 | མོང་སྒར (Monggar) | 17 | [Browse](divisions/monggar-bt007/) |
| 8 | སྤ་རོ་ (Paro) | 10 | [Browse](divisions/paro-bt008/) |
| 9 | པདྨ་དགའ་ཚལ་ (Pemagatshel) | 11 | [Browse](divisions/pemagatshel-bt009/) |
| 10 | སྤུ་ན་ཁ་ (Punakha) | 11 | [Browse](divisions/punakha-bt010/) |
| 11 | བསམ་གྲུབ་ལྗོངས་མཁར (Samdrupjongkhar) | 11 | [Browse](divisions/samdrupjongkhar-bt011/) |
| 12 | བསམ་རྩེ་ (Samtse) | 15 | [Browse](divisions/samtse-bt012/) |
| 13 | གསར་སྤང་ (Sarpang) | 12 | [Browse](divisions/sarpang-bt013/) |
| 14 | ཐིམ་ཕུ་ (Thimphu) | 8 | [Browse](divisions/thimphu-bt014/) |
| 15 | བཀྲིས་སྒང་ (Trashigang) | 15 | [Browse](divisions/trashigang-bt015/) |
| 16 | ཀྲོང་གསར་ (Trongsa) | 5 | [Browse](divisions/trongsa-bt017/) |
| 17 | རྩི་རང་ (Tsirang) | 12 | [Browse](divisions/tsirang-bt018/) |
| 18 | དབང་འདུས་ཕོ་བྲང (Wangduephodrang) | 15 | [Browse](divisions/wangduephodrang-bt019/) |
| 19 | བཀྲིས་གཡང་རྩེ (Yangtse) | 8 | [Browse](divisions/yangtse-bt016/) |
| 20 | གཞལམ་སྒང་ (Zhemgang) | 8 | [Browse](divisions/zhemgang-bt020/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-dzongkhag.json](data/all-dzongkhag.json) | JSON | All 20 district records |
| [all-gewog.json](data/all-gewog.json) | JSON | All 205 sub-district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-dzongkhag.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['gewog']} sub-districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-dzongkhag.json", "utf-8"));
console.log(`Total: ${data.length} districts`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=district, 2=sub-district |
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
divisions/{dzongkhag-slug}/
```

Sub-districts are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-district links
- [Per-district data](docs/llms-full/) — Full data by district

## Citation

```
Bhutan Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/bhutan-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
