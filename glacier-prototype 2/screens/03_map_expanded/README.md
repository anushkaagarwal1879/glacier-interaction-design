# 03 – Map expanded

![Screen](screen.jpg)

- **Description:** The map thumbnail from the top left is enlarged as an overlay above the chart. It shows the glacier outline drawn as several nested lines, with a pin marking the glacier's location.
- **Trigger:**
  - Click outside the map or on a close button
- **Response:**
  - Map shrinks back to the thumbnail → back to `01_overview` or `04_isotype_view`
- **Data:**
  - Outline: `inventory_sgi2016_r2020/SGI_2016_glaciers.shp` → [ID field, check `ReadMe.txt`], geometry. Convert to GeoJSON first (mapshaper.org) and filter to the listed glaciers to keep the file small
  - Pin: `inventory_sgi2016_r2020/SGI_2016_glacier_locations.shp` → geometry
  - Coordinates are Swiss LV95, not latitude/longitude. Reproject to WGS84 when converting (in mapshaper: `-proj wgs84`)
- **States:**
  - Thumbnail (small, in `01_overview`)
  - Expanded
- **Remarks:**
  - To confirm: are the nested lines outlines from different years? Only the 2016 inventory is downloaded. Older outlines need the other inventory releases (1850, 1931, 1973, 2010) or the 2023 one
  - To confirm: does the map react to the year slider?
  - To confirm: what the pin marks
