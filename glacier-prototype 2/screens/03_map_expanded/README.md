# 03 – Map expanded

![Screen](screen.jpg)

- **Description:** The map thumbnail from the top left is enlarged as an overlay above the chart. It shows the glacier outline drawn as several nested lines, with a pin marking the glacier's location.
- **Trigger:**
  - Click outside the map or on a close button
- **Response:**
  - Map shrinks back to the thumbnail → back to `01_overview` or `04_isotype_view`
- **Data:**
  - Outlines: `data/[inventory files].geojson` → [glacier ID, geometry]. GLAMOS provides shapefiles, convert to GeoJSON (e.g. mapshaper.org)
- **States:**
  - Thumbnail (small, in `01_overview`)
  - Expanded
  - No outline available for this glacier
- **Remarks:**
  - To confirm: are the nested lines outlines from different inventory years (showing shrinking) or terrain contours?
  - To confirm: does the map react to the year slider?
  - To confirm: what the pin marks
