# 03 – Map expanded

![Screen](screen.jpg)

- **Description:** The map thumbnail from the top left is enlarged as an overlay above the chart. It shows the glacier outline drawn as several nested lines, with a pin marking the glacier's location.
- **Trigger:**
  - Click outside the map or on a close button
- **Response:**
  - Map shrinks back to the thumbnail → back to `01_overview` or `04_isotype_view`
- **Data:**
  - Outline: `SGI_2016_glaciers.json` → the feature whose `sgi-id` equals the selected `glacier id`. Already in WGS84 (longitude/latitude), draw with `d3.geoPath` and a projection fitted to that one glacier (`projection.fitSize`)
  - Pin: the centre of that outline, from `d3.geoCentroid(feature)`
- **States:**
  - Thumbnail (small, in `01_overview`)
  - Expanded
- **Remarks:**
  - To confirm: are the nested lines outlines from different years? Only the 2016 outline is in the data. Older outlines would need other inventory releases (1850, 1931, 1973, 2010, 2023)
  - To confirm: does the map react to the year slider?
  - The pin marks the centre of the glacier outline
