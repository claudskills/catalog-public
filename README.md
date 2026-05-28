# ClaudSkills — Open Catalog (auto-generated)

> **Machine-readable mirror of the ClaudSkills catalog.** Daily auto-export from
> [claudskills.com](https://claudskills.com) — the open registry of
> Claude Code / Claude Skills `SKILL.md` files.

[![CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-blue.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Daily refresh](https://img.shields.io/badge/refresh-daily%2003%3A00%20UTC-green)](https://github.com/claudskills/catalog-public/actions)
[![Total skills](https://img.shields.io/badge/skills-72,693-brightgreen)](https://claudskills.com)

## What's here

| File | Format | Use |
|---|---|---|
| [`skills.json`](skills.json) | JSON array | General-purpose, easy to grep |
| [`skills.parquet`](skills.parquet) | Apache Parquet | Fast analytics (pandas, DuckDB, Polars, Arrow) |
| [`skills.csv`](skills.csv) | CSV (tags `\|`-joined) | Spreadsheets, ad-hoc tools |
| [`skills.ndjson`](skills.ndjson) | Newline-delimited JSON | Streaming consumers, `jq`, line-by-line |
| [`feed.atom`](feed.atom) | Atom 1.0 | Readers (Feedly, Inoreader, NetNewsWire) |
| [`CITATION.cff`](CITATION.cff) | Citation File Format | Academic citation metadata |

## Quick start

```bash
# Grep for all "deployment"-related skills via jq:
curl -sL https://github.com/claudskills/catalog-public/raw/main/skills.ndjson \
  | jq 'select(.category == "ops" or (.tags | index("type:deployment")))'

# Load into DuckDB:
duckdb -c "SELECT category, COUNT(*) FROM read_parquet('https://github.com/claudskills/catalog-public/raw/main/skills.parquet') GROUP BY 1 ORDER BY 2 DESC"

# pip install + pandas:
python -c "import pandas as pd; df = pd.read_parquet('https://github.com/claudskills/catalog-public/raw/main/skills.parquet'); print(df.describe())"
```

## Catalog snapshot

| Field | Value |
|---|---|
| Total skills | **72,693** |
| Featured | 20 |
| Daily-eligible (quality ≥ 80) | 7,386 |
| Unique authors with ≥1 admitted skill | 5,518 |
| Categories | 10 |
| Rows dropped this run (no attribution) | 0 |
| Last refresh | **2026-05-28 06:42 UTC** |

### Top categories

| Category | Skills |
|---|---:|
| general | 39,264 |
| engineering | 13,896 |
| security | 3,956 |
| content | 3,355 |
| tools | 3,263 |
| science | 2,945 |
| product | 2,701 |
| growth | 1,793 |
| sales | 1,302 |
| ads | 218 |

### Top licenses

| License | Skills |
|---|---:|
| `(unspecified)` | 49,729 |
| `MIT` | 18,050 |
| `Apache-2.0` | 3,621 |
| `AGPL-3.0` | 256 |
| `NOASSERTION` | 122 |
| `CC-BY-4.0` | 107 |
| `Complete terms in LICENSE.txt` | 91 |
| `MIT + Commons Clause` | 85 |
| `GPL-3.0` | 73 |
| `BSD-3-Clause` | 65 |

### Top authors

| Author | Skills |
|---|---:|
| [Jeremy Longshore <jeremy@intentsolutions.io>](https://claudskills.com/author/) | 3,310 |
| [Klotzkette](https://claudskills.com/author/) | 1,792 |
| [mahipal](https://claudskills.com/author/) | 715 |
| [diegosouzapw](https://claudskills.com/author/) | 695 |
| [majiayu000](https://claudskills.com/author/) | 665 |
| [Pranav Nagrecha](https://claudskills.com/author/) | 664 |
| [aiskillstore](https://claudskills.com/author/) | 362 |
| [Raishin](https://claudskills.com/author/) | 355 |
| [aipoch](https://claudskills.com/author/) | 334 |
| [onfire7777](https://claudskills.com/author/) | 287 |

## Schema

Each row carries the following fields. Fields marked **required** are
present on 100% of rows; the rest depend on what the upstream source
disclosed.

| Field | Type | Required | Description |
|---|---|---|---|
| `slug` | string | ✓ | URL-safe identifier, unique across the catalog |
| `name` | string | ✓ | Human-friendly display name |
| `description` | string | ✓ | One-paragraph summary (from `SKILL.md` frontmatter) |
| `category` | string | ✓ | Top-level taxonomy (`engineering`, `sales`, `science`, …) |
| `subcategory` | string | ✓ | Refined category (~118 sub-topics) |
| `tags` | string[] | ✓ | Orthogonal labels (`lang:python`, `ai:claude`, …) |
| `featured` | bool | ✓ | Editorial selection flag |
| `daily_eligible` | bool | ✓ | `true` if Pro quality_score ≥ 80 (top ~12%) |
| `lastmod` | YYYY-MM-DD | ✓ | Last meaningful change to the skill |
| `catalog_url` | URL | ✓ | Canonical home of this row on claudskills.com |
| `author` | string | — | Best-effort author/maintainer name |
| `author_url` | string | — | Canonical author page (GitHub profile, blog, etc.) |
| `source_url` | string | — | Where the `SKILL.md` was harvested from upstream |
| `homepage` | string | — | Project website if separate from the source repo |
| `license` | string | — | SPDX identifier or free-text license name |

## Attribution

Every row in this catalog carries `catalog_url` — the row's canonical
home on claudskills.com — as the floor attribution. Where the upstream
source disclosed it, we additionally preserve `author`, `author_url`,
`source_url`, `homepage`, and `license` verbatim from the upstream
`SKILL.md` frontmatter.

Current upstream-attribution coverage (rows with at least one of
`author`/`author_url`/`source_url`/`homepage`):

| Field | Rows | % |
|---|---:|---:|
| `author` | 38,779 | 53.3% |
| `source_url` | 37,824 | 52.0% |
| `author_url` | 32,863 | 45.2% |
| `license` | 22,964 | 31.6% |

Upstream coverage grows organically each miner cycle as the
`SKILL.md`-frontmatter backfill picks up newly-disclosed metadata.

If you're an author and want your credit corrected, added, or
withdrawn, open an issue on this repo or email
`acreatorstore@translatea.com` — we honour every opt-out within one
miner cycle (~12 h).

## License

This dataset is published under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
You may use, redistribute, and build on it (including for training
machine-learning models or commercial products) as long as you
**attribute** ClaudSkills.com as the source. Per-skill licenses
(visible in the `license` field of each row) are preserved verbatim
from the upstream `SKILL.md` files and apply to the skill content
itself — independently of the catalog's CC BY 4.0 wrapper.

## How to cite

```bibtex
@misc{claudskills_2026,
  author = {ClaudSkills},
  title  = {ClaudSkills Open Catalog of Claude Code Skills},
  year   = {2026},
  url    = {https://claudskills.com},
  note   = {Dataset mirror: \url{https://github.com/claudskills/catalog-public}}
}
```

See [`CITATION.cff`](CITATION.cff) for the machine-readable version.

## Refresh schedule

- **Source** auto-mined twice daily (02:00 + 14:00 local time) at
  [claudskills.com](https://claudskills.com).
- **This mirror** refreshed daily at 03:00 UTC (after the nightly
  miner pass settles).
- **Mirrors on HuggingFace** at
  [`huggingface.co/datasets/claudskills/skills`](https://huggingface.co/datasets/claudskills/skills)
  refresh on the same cadence.

If the refresh has been stale for >36 hours, check
[GitHub Actions](https://github.com/claudskills/catalog-public/actions).

## Privacy + opt-out

ClaudSkills is an **open** registry. Skills are mined from public
sources only (GitHub, GitLab, awesome-lists, Reddit, Bluesky, etc.) and
all attribution is preserved. If you are an author and want your skill
*removed* (not just credit-corrected), open an issue on this repo or
email `acreatorstore@translatea.com` — we honour every opt-out request
within one miner cycle.

---
*This file is regenerated on every export pass. Don't hand-edit — edit
[`workflows/W1_export.py`](https://github.com/claudskills/automation/blob/main/workflows/W1_export.py)
in the automation repo instead.*
