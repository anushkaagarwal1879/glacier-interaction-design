# 04 – Isotype view

![Screen](screen.jpg)

- **Description:** Reached by clicking "Isotype" in the toggle. Same layout as `01_overview`, but the radar chart is replaced by an Isotype pictogram chart for one metric, and a metric menu appears (`state_metric-menu.jpg`) with:
  1. Mass (Loss)
  2. Retreat
  3. Area covered
  4. Melt by Elevation
  5. Thickness
  6. Equilibrium Line

  Isotype rules: one symbol always stands for the same amount, more = more symbols in a row (never a bigger symbol), flat colours, simple silhouettes, rows read left to right. One row per selected year, so years compare by row length. A key under the chart says what one symbol equals.
- **Trigger:**
  - Click a metric in the menu
  - Drag the year slider
  - Click "Regular" in the toggle
  - Click the glacier dropdown or map thumbnail
- **Response:**
  - Metric → that metric is highlighted in the menu, chart redraws with its symbols, key updates
  - Slider → symbols animate in or out per year
  - "Regular" → pictograms gather back into polygons → back to `01_overview`
  - Dropdown → `02_glacier_dropdown`, map → `03_map_expanded`
- **Data:** (filter by `glacier id`; "year" = year of `date_end`)
  - Mass (Loss): `massbalance_fixdate_2025_r2025.csv` → `Ba` (mm w.e.) × `area` (km²), as m³ of water lost, same formula as `01_overview`
  - Retreat: `lengthchange_2025_r2025.csv` → running sum of `dL` (m)
  - Area covered: `massbalance_fixdate_2025_r2025.csv` → `area` (km²)
  - Melt by Elevation: `massbalance_fixdate_elevationbins_2025_r2025.csv` → `Ba` (mm w.e.) per 100 m band (`h_min` to `h_max`, m asl.). One row per band instead of per year, for the selected year
  - Thickness: `volumechange_2025_r2025_series.csv` → `dh_mean` (m surface lowering per period)
  - Equilibrium Line: `massbalance_fixdate_2025_r2025.csv` → `ELA` (m asl.)
- **States:**
  - Default metric shown on arrival
  - One state per metric (add a sketch per metric: `state_mass.jpg`, `state_retreat.jpg`, …)
  - Metric has no data for this glacier or year
- **Remarks:**
  - To confirm: which metric shows first (suggestion: Mass (Loss))
  - To confirm: symbol and unit per metric, chosen after looking at the real numbers so rows stay readable (roughly 5 to 50 symbols)
  - To confirm: where the menu sits on screen, and what the two empty rows at the top of the menu card are
  - To confirm: "Melt by Elevation" is here but not on the radar chart. Isotype only?
  - Thickness uses volume change periods (3+ years each), so rows follow those periods, not single years
