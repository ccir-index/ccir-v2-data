# ccir-v2-data

Public data repository for CCIR v2.0 — the Intelligence Factory rebuild of the Compute Rate Index.

**Methodology:** see [ccir-methodology](https://github.com/ccir-index/ccir-methodology) (v2.0 methodology forthcoming).

## Structure

- `indices/daily/` — one CSV per published daily series (see naming below)
- `indices/snapshots/{as_of_date}/` — dated all-indices snapshots with `manifest.json`
- `coverage/` — daily per-factory coverage stats
- `methodology/` — versioned methodology documents and registries (factory, silicon)

## Naming convention

Index series follow `CRI-{gen}-{factory}-{form}-{term}`:

- `{gen}` — H100, H200, B200, GB200, A100, etc.
- `{factory}` — HIF (hyperscale), IIF (integrated), SIF (specialty), DIF (distributed), Composite (IIF+SIF median), All (all including HIF)
- `{form}` — 8G (8-GPU node), 1G (single GPU), NVL72 (rack-scale), PCIe
- `{term}` — OD (on-demand), Spot, 1M, 3M, 1Y, 3Y

Examples:
- `CRI-H100-IIF-8G-OD.csv` — H100 on 8-GPU node from integrated neoclouds, on-demand
- `CRI-GB200-IIF-NVL72-OD.csv` — GB200 rack-scale from integrated neoclouds, on-demand
- `CRI-H100-Composite-8G-OD.csv` — venue-weighted across IIF+SIF (excludes HIF)
- `CRI-H100-All-8G-OD.csv` — includes HIF (backwards-compat with legacy `CRI-H100`)

## Status

v2.0 successor to [ccir-data](https://github.com/ccir-index/ccir-data). During parallel production (≥30 days), both repos publish. At cutover v1 (`ccir-data`) freezes and v2 becomes primary.
