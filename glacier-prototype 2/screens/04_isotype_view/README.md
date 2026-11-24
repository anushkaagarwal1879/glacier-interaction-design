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
- **Data:**
  - Mass (Loss): `data/[massbalance glacier-wide file].csv` → [annual balance]
  - Retreat: `data/[lengthchange file].csv` → [cumulative length change]
  - Area covered: `data/[inventory file].geojson` → [area]
  - Melt by Elevation: `data/[massbalance elevation-bin file].csv` → [elevation bin, balance]
  - Thickness: `data/[icethickness file]` → [thickness]
  - Equilibrium Line: `data/[massbalance glacier-wide file].csv` → [ELA column, if it exists]
- **States:**
  - Default metric shown on arrival
  - One state per metric (add a sketch per metric: `state_mass.jpg`, `state_retreat.jpg`, …)
  - Metric has no data for this glacier or year
- **Remarks:**
  - To confirm: which metric shows first (suggestion: Mass (Loss))
  - To confirm: symbol and unit per metric, chosen after looking at the real numbers so rows stay readable (roughly 5 to 50 symbols)
  - To confirm: where the menu sits on screen, and what the two empty rows at the top of the menu card are
  - To confirm: "Melt by Elevation" is here but not on the radar chart. Isotype only?
  - Thickness is not yearly, so a row per year may not be possible
