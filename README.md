# Wadi Majlas Flood Protection Dam — Hydrology Report

Updated hydrological study for the **Wadi Majlas Flood Protection Dam**, Wilayat Qurayat,
Muscat Governorate, Sultanate of Oman. This report supersedes the hydrology chapter of the
previous design report.

## Deliverables

| File | Description |
|------|-------------|
| `Wadi Majlas Hydrology Report.docx` | Final report (Word, editable; open and update fields with Ctrl+A → F9 to refresh the TOC/lists) |
| `Wadi Majlas Hydrology Report.pdf` | Final report (PDF, fields updated) |
| `figures/` | All report figures (maps, IDF, comparison, reservoir routing, etc.) |
| `data/` | Clean result tables (CSV) behind the report |

## Scope

- Catchment and physiography from the 5 m NSA DTM (571 km² to the dam; 604 km² with the
  downstream sub-catchments added for the dyked-channel design).
- Regional rainfall frequency analysis (RFA) — **GEV distribution, L-moments only**, with
  annual maxima extracted directly from the observed records (no gap-filling).
- Intensity–Duration–Frequency (IDF) relationships (single regional growth curve — no
  post-1-hour divergence).
- Comparison of local 24-h design rainfall with the Oman Flood-Mapping design rainfall
  (used to drive the HEC-HMS runs).
- Probable Maximum Precipitation (PMP) — moisture-maximisation/transposition; catchment maps.
- SCS curve-number rainfall–runoff model (GCN250 grid), Kirpich lag times, depth–area ARF.
- Review of the previous calibration: one of three observed Gonu (2007) hydrographs near the
  dam is shown to be erroneous (reproducible only with physically implausible rainfall
  reductions) and was excluded.
- Design flood peaks and hydrographs (2–10,000-yr + PMP), with and without the Majlas
  reservoir routing.

## Key results (headline)

- Catchment-average CN ≈ 89; time of concentration ≈ 400 min.
- Local RFA and Flood-Mapping 24-h rainfall agree at 2-yr (27.9 vs 27.6 mm) but the local
  short records (dominated by Cyclone Gonu 2007) give a much heavier tail at rare RPs; the
  Flood-Mapping depths were adopted for design.
- Majlas reservoir stores the full inflow up to ~200-yr and attenuates the 10,000-yr peak
  from 14,166 to 8,749 m³/s (≈38 %).

## Notes on reproducibility

Analysis scripts and intermediate data are kept in the project working folder (`W1/`) and are
not part of this published set. Figures were generated with Python (rasterio/geopandas/
matplotlib); the report was assembled on the approved project template.
