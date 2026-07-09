# Wadi Majlas Flood Protection Dam — Hydrology Report

Updated hydrological study for the **Wadi Majlas Flood Protection Dam**, Wilayat Qurayat,
Muscat Governorate, Sultanate of Oman. Supersedes the hydrology chapter of the previous
design report.

## Deliverables

| File | Description |
|------|-------------|
| `Wadi Majlas Hydrology Report.docx` | Final report (Word; open and press Ctrl+A → F9 to refresh the TOC / figure & table lists) |
| `Wadi Majlas Hydrology Report.pdf` | Final report (PDF, fields updated) |
| `figures/` | Report figures — QGIS maps, RFA/IDF plots, reservoir routing |
| `data/` | Result tables (CSV) behind the report |

## Methodology (this revision)

**Method** — the **region-of-influence** regional frequency analysis used by the Oman
Flood-Mapping study (not single-region Hosking–Wallis). From the 421-gauge national archive,
**106 gauges within 80 km** of the catchment form the data pool and the **47 within 40 km** are
the IDF target sites (numbered 1–106, top-left → bottom-right).

**Pre-processing** — each record disaggregated to a **5-min grid**; depths < 0.5 mm → 0; **AMS =
max annual rolling sum** per duration (5 min–24 h, water year Oct–Sep); zero-maximum years dropped.

**Gap filling** — missed-storm days infilled by **3D inverse-distance weighting** (30 km, vertical
term), only where **≥3 donors recorded rain** (storm active); single pass, 0≠gap, observed never
overwritten, cyclones excluded — 6,029 station-days recovered.

**Outliers** — **log-domain Grubbs** (13 non-cyclone outliers removed; Gonu/Phet extremes kept).

**Frequency** — for each target site, GEV/L-moments is fitted to every gauge within 40 km and the
**ξ, α, κ parameters are averaged**, giving that site's IDF. Averaging stabilises the shape
(catchment 24-h κ ≈ −0.32). Result — 24-h catchment depths **reproduce flood mapping**: 2-yr 23,
100-yr 186, 1,000-yr 426, 10,000-yr 929 mm (0.9–1.1× in the design range, ~1.3× at 10,000-yr),
below the PMP — independently validating the analysis. 47 target IDFs + catchment IDF produced.

**PMP** — deterministic moisture-maximisation / storm-transposition (Gonu 2007); Majlas-specific
24-h PMP map.

**Rainfall–runoff model** — HEC-HMS, SCS curve number (GCN250, catchment CN ≈ 89), Kirpich lag,
depth–area ARF; 20 sub-basins (571 km² to dam, 604 km² with downstream reaches).

**Calibration review** — the previous study's observed Gonu hydrograph at the Majlass gauge is
shown to be erroneous (reproducible only with physically implausible rainfall reductions) and is
excluded; Hayfadh was reproduced well and Phet 2010 used for validation.

**Design floods** — 2–10,000-yr and PMP, with/without Majlas reservoir routing (10,000-yr peak
attenuated ~38 %, 14,166 → 8,749 m³/s).

## Maps

All maps (`figures/map1–4`) were produced in **QGIS** (print-layout export with hillshade,
colour ramps, legend, scale bar and north arrow) from the project GIS layers.

## Notes

Analysis scripts and intermediate data are kept in the project working folders (`W1/`, `W2/`)
and are not part of this published set.
