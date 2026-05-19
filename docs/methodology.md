# Methodology

## Data Sources

- **OCHA COD-AB Bhutan** (CC BY-IGO) — 20 dzongkhags + 205 gewogs with P-codes and centroid coordinates
- **Wikidata** (CC0) — Dzongkha (Tibetan script) names for all 20 dzongkhags
- **Bhutan Post** (bhutanpost.bt) — Postal codes for all gewogs

## Processing

1. Dzongkhag and gewog records from OCHA COD-AB XLSX gazetteer
2. Dzongkha script names merged from Wikidata (100% dzongkhag coverage)
3. Postal codes scraped from Bhutan Post official search (100% gewog coverage)
4. Multi-format export: JSON, NDJSON, CSV

## Accuracy

- Coordinates: 100% at all levels (from OCHA COD-AB centroids)
- Dzongkha names: 100% at dzongkhag level; gewog level uses romanized names (official usage)
- Postal codes: 100% at gewog level (from Bhutan Post)
- Build script is idempotent: same input always produces same output