# Wadi Majlas Flood Protection Dam — Hydrology Report (Review)

Updated hydrological study for the **Wadi Majlas Flood Protection Dam**, Wilayat Qurayat,
Muscat Governorate, Sultanate of Oman. This revision is a **review of the previous design
hydrology**: each section compares the updated values against the earlier report and explains
where and why they differ. It also covers the upstream **Haifaz dam** (Subbasin-1, inflow only).

## Deliverables

| File | Description |
|------|-------------|
| `Wadi Majlas Hydrology Report.docx` | Final report (Word). Open and press **Ctrl+A → F9** to refresh the TOC / figure & table lists, then export a PDF if needed |
| `figures/` | Report figures — QGIS maps, RFA/IDF plots, reservoir routing, meteorology |
| `data/` | Result tables (CSV) behind the report |

> A PDF is not committed: Word COM export hangs on this document and no LibreOffice is available
> in the build environment. Export the PDF from Word after refreshing fields (Ctrl+A → F9).

## Methodology (this revision)

**Design rainfall** — **region-of-influence** regional frequency analysis (GEV fitted by
L-moments). From the 421-gauge national archive, **106 gauges within 80 km** form the analysis
pool and the **47 within 40 km** are the IDF target sites (numbered 1–106, top-left → bottom-right).
For each site the GEV **ξ, α, κ parameters are averaged over all gauges within 40 km**, which
stabilises the shape (catchment 24-h κ ≈ −0.35).

**Pre-processing** — each record disaggregated to a **5-min grid**; **AMS = max annual rolling sum**
per duration (5 min–24 h, water year Oct–Sep). The **0.5 mm floor is applied to the annual maxima
only** (not to raw records, which may be sub-mm at 1-min resolution); zero-maximum years dropped.
Gauges with **< 10 years** of record are excluded from fitting.

**Gap filling** — missed-storm days infilled by **3D inverse-distance weighting** (30 km, vertical
term), only where **≥ 3 donors recorded rain**; single pass, 0 ≠ gap, observed never overwritten,
cyclones excluded — ~13,700 station-days recovered.

**Outliers** — **log-domain Grubbs** (13 non-cyclone outliers removed; Gonu/Phet extremes kept).

**Design 24-h depths** — 100-yr **239 mm**, 1,000-yr **571 mm**, 10,000-yr **1,314 mm** — below the
PMP (≈ 1,300 mm). Lower than the previous report at moderate return periods (100-yr 239 vs 384 mm)
but converging at 10,000-yr (1,314 vs 1,270 mm). Design-storm temporal patterns and the ARF are
taken from the Oman **Flood-Mapping** study (`FM rainfall 2-PMP.xlsx`), which is retained as the
design basis.

**PMP** — deterministic moisture-maximisation / storm-transposition (Gonu 2007); catchment-average
24-h PMP ≈ **1,300 mm**, highest near the coast at lower elevation.

**Meteorology** — the site has **no representative nearby station** (nearest are 80 km+ across the
Hajar range). Temperature and wind are taken from **NASA POWER / MERRA-2 reanalysis at the dam axis
(23.255°N, 58.872°E)**: annual mean ≈ 28 °C; prevailing wind SW–SSW, mean ≈ 3.2 m/s. A brief
**climate-change** allowance (+10–15 % on extreme rainfall over 50 yr) is included as a sensitivity.

**Rainfall–runoff model** — HEC-HMS, SCS curve number (GCN250, catchment CN ≈ 89), Kirpich lag,
**Muskingum-Cunge** channel routing, Depth-Area ARF; 20 sub-basins (571 km² to the Majlas dam,
604 km² with the Haifaz and downstream catchments).

**Calibration review** — the previous study's observed Gonu hydrograph at the **Majlass gauge is
shown to be erroneous** (reproducible only with physically implausible rainfall reductions) and is
excluded; **Hayfadh** was reproduced well and **Phet 2010** used for validation.

**Design floods** — 2–10,000-yr and PMP. Majlas dam peak inflow: 100-yr ≈ 3,450, 1,000-yr ≈ 8,290,
10,000-yr ≈ 14,170 m³/s (PMF inflow ≈ 18,700). The reservoir stores the full inflow to ~200-yr and
attenuates the 10,000-yr peak ~38 % (14,166 → 8,749 m³/s). Haifaz dam inflow: 100-yr ≈ 800,
10,000-yr ≈ 2,510, PMP ≈ 3,220 m³/s. Downstream channel design flows (J10/J11/J12/O1) provided.

## Maps

All maps (`figures/map*`) were produced in **QGIS** (print-layout export with hillshade, colour
ramps, legend, scale bar and north arrow) from the project GIS layers.

## Notes

Analysis scripts and intermediate data are kept in the project working folders (`W1/`…`W5/`) and are
not part of this published set.
