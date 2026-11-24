# 02 – Glacier dropdown

![Screen](screen.jpg)

- **Description:** The glacier dropdown at the top centre is open. A list below it shows the available glaciers, each with name and location. The rest of the screen stays as in `01_overview` (or `04_isotype_view`, if opened from there).
- **Trigger:**
  - Click a glacier in the list
  - Click outside the list
- **Response:**
  - Click a glacier → list closes, title updates, map thumbnail updates, the current chart (Regular or Isotype) redraws for the new glacier, slider range updates to the years this glacier has data for → back to `01_overview` or `04_isotype_view`
  - Click outside → list closes, nothing changes
- **Data:**
  - Glacier names, IDs and year range: `massbalance_fixdate_2025_r2025.csv` → `glacier name`, `glacier id`, year of `date_end`
  - Location: `inventory_sgi2016_r2020/SGI_2016_glacier_locations.shp` → [field name for location, check `ReadMe.txt` in that folder], joined on SGI id
- **States:**
  - List open
  - Glacier hovered (highlighted)
- **Remarks:**
  - To confirm: which glaciers to list. Suggestion: the 11 glaciers with long records listed in `data/README.md`, sorted by name. All 43 would include glaciers with only 3 to 6 years of data
  - To confirm: what "Location" shows (canton, valley, coordinates)
