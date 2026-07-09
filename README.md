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

**Rainfall data analysis** — annual maxima (10 min–24 h) extracted from nine gauges on a
10-minute grid; inter-station consistency checked by double-mass analysis; high-outlier
screening by the Grubbs–Beck test (the 2007 Cyclone Gonu maxima are genuine extremes, retained).

**Gap filling** — internal record gaps infilled by the **normal-ratio method**, single pass
from observed values only (filled values never reused) with recorded zeros preserved as real
zeros — correcting the two errors in the earlier analysis.

**Regional frequency analysis** — **Hosking & Wallis index-flood** procedure with the **GEV
distribution fitted by L-moments**: discordancy Dᵢ (no discordant sites), heterogeneity
H = −1.1 (homogeneous region), goodness-of-fit, regional dimensionless growth curve.

**IDF curves** — station-based (per gauge) and regional (pooled), via one regional growth curve
applied to each duration's index rainfall (parallel curves, no post-1 h crossing). Regional IDF
fitted by `i = 111.8·T^0.706 / (D + 5.04)^0.684` (R² = 0.999; i mm/h, T yr, D min).

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
