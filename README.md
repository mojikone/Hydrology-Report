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

**Annual maxima** — the AMS is the **maximum annual rolling sum** for each duration
(5 min–96 h), on a water year (Oct–Sep). Years where a gauge was offline or clearly missed the
year's dominant regional storm are excluded (missing data, not low maxima).

**Gap filling** — genuine 10-minute gaps infilled by **3D inverse-distance weighting** (30 km
radius, vertical term for orography), only when a storm is active and **≥3 donors recorded
non-zero rain in the same 10-minute step**; single pass (filled values never reused), a recorded
zero is a real zero, observed values never overwritten, cyclone windows excluded from filling.

**Regional frequency analysis** — **Hosking & Wallis index-flood** with the **GEV distribution
by L-moments**; mean index; 5 fitting gauges (≥10 water years, 81 pooled station-years) form one
**homogeneous** region (24-h H1 = −1.6; no discordant sites, Dᵢ < 3).

**Distribution** — the unconstrained L-moment fit gives an unbounded tail (κ<0) that extrapolates
past the PMP; since Oman rainfall is **moisture-limited** (24-h PMP ≈ 1300 mm) the GEV shape is
constrained to the physically bounded case (**κ ≥ 0**). 24-h design depths: 2-yr 52, 100-yr 307,
10,000-yr 584 mm — below the PMP, ~1.5× the flood-mapping values at moderate RP and converging at
rare RP (a genuine local/Gonu-orographic finding). **IDF**: station and regional, all durations.

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
