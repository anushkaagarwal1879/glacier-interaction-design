# 02 – Glacier dropdown

![Screen](screen.jpg)

- **Description:** The glacier dropdown at the top centre is open. A list below it shows all available glaciers, each with name and location. The rest of the screen stays as in `01_overview` (or `04_isotype_view`, if opened from there).
- **Trigger:**
  - Click a glacier in the list
  - Click outside the list
- **Response:**
  - Click a glacier → list closes, title updates, map thumbnail updates, the current chart (Regular or Isotype) redraws for the new glacier, slider range updates to the years this glacier has data for → back to `01_overview` or `04_isotype_view`
  - Click outside → list closes, nothing changes
- **Data:**
  - Glacier names and IDs: `data/[massbalance glacier-wide file].csv` → [glacier name, glacier ID]
  - Location: `data/[inventory file].geojson` → [location / canton column]
- **States:**
  - List open
  - Glacier hovered (highlighted)
  - Glacier with incomplete data (greyed out or marked)
- **Remarks:**
  - To confirm: list only glaciers that have data for all metrics, or list all and mark missing ones
  - To confirm: what "Location" shows (canton, valley, coordinates)
