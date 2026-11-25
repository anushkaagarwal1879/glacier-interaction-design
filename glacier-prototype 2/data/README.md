# Data

Put the data files you downloaded from GLAMOS (https://doi.glamos.ch/index.html) here.

Refer to these files by their exact names in the screen descriptions.

All data: GLAMOS, Glacier Monitoring Switzerland, licence CC BY 4.0. Show the credit in the About panel.

## Files used

| File | Used for |
|---|---|
| `massbalance_fixdate_2025_r2025.csv` | Glacier list, Mass (Loss), ELA, Area, per year |
| `massbalance_fixdate_elevationbins_2025_r2025.csv` | Melt by Elevation |
| `lengthchange_2025_r2025.csv` | Retreat |
| `volumechange_2025_r2025_series.csv` | Thinning (mean surface lowering) |
| `SGI_2016_glaciers.json` | Map outline and pin (GeoJSON, converted from the 2016 inventory shapefile, WGS84) |
| `icethickness_2020_r2020/<glacier id>_<name>_<source>.txt` | Ice thickness (radar points), optional |

Not used: `massbalance_observation_*` (same data on exact field dates, the `fixdate` files use the hydrological year 1 Oct to 30 Sep, which is easier to compare) and `volumechange_2025_r2025_allcombinations.csv` (overlapping periods).

## How to read the CSV files

**The CSV files do not start with the column names.**

Mass balance and length change files:
- Lines 1 to 6: citation and title text, skip
- Line 7: long column names
- Line 8: short column codes (use these)
- Line 9: units
- Line 10 onwards: data

Volume change file:
- Lines 1 to 6: citation and title text, skip
- Line 7: column codes
- Line 8: units
- Line 9 onwards: data

The last column (`observer`) sometimes contains commas without quotes, so some rows have extra columns. Read columns by position and ignore everything after the last needed column.

## Columns

### `massbalance_fixdate_2025_r2025.csv` (one row per glacier per year)

| Column | Code | Unit |
|---|---|---|
| glacier name | | |
| glacier id | (SGI id, e.g. `B36-26`) | |
| start date of observation | date_start | yyyy-mm-dd |
| end date of winter observation | date_end_winter | yyyy-mm-dd |
| end date of observation | date_end | yyyy-mm-dd (year of this date = the year shown) |
| winter mass balance | Bw | mm w.e. |
| summer mass balance | Bs | mm w.e. |
| annual mass balance | Ba | mm w.e. |
| equilibrium line altitude | ELA | m asl. |
| accumulation area ratio | AAR | % |
| glacier area | area | km² |
| minimum elevation of glacier | h_min | m asl. |
| maximum elevation of glacier | h_max | m asl. |
| observer | | |

### `massbalance_fixdate_elevationbins_2025_r2025.csv` (one row per glacier per year per 100 m band)

glacier name, glacier id, date_start, date_end_winter, date_end, Bw, Bs, Ba (mm w.e.), area of bin (km²), h_min of bin (m asl.), h_max of bin (m asl.), observer

### `lengthchange_2025_r2025.csv` (one row per glacier per measurement period)

| Column | Code | Unit |
|---|---|---|
| glacier name | | |
| glacier id | | |
| start date of observation | date_start | yyyy-mm-dd |
| quality of start date | x = not exactly known | |
| end date of observation | date_end | yyyy-mm-dd |
| quality of end date | x = not exactly known | |
| length change | dL | m (change in that period, not cumulative) |
| elevation of glacier tongue | h_min | m asl. (often empty) |
| observer | | |

### `volumechange_2025_r2025_series.csv` (one row per glacier per period, periods of 3+ years)

SGI-ID, source_start, source_end, date_start (yyyymmdd, 9999 = unknown day/month), date_end, A_start (km²), outline_start (yyyy), A_end (km²), outline_end (yyyy), dV (km³), dh_mean (m), Bgeod (m w.e. per year), sigma, covered (%), rho_dv (kg/m³), Name

### `SGI_2016_glaciers.json` (GeoJSON, one polygon feature per glacier, 1,400 features)

Converted with mapshaper from `inventory_sgi2016_r2020/SGI_2016_glaciers.shp` (`-proj wgs84 init=EPSG:2056`). Coordinates are longitude/latitude (WGS84).

Properties per feature: `sgi-id` (e.g. `A10g-04`), `name`, `area_km2`, `length_km`, `masl_min`, `masl_max`, `masl_mean`, `masl_med`, `slope_deg`, `aspect_deg`, `year_acq`, `year_rel`, `gid`, `pk_glacier`, `i_code`, `rl_0` to `rl_3`

Note: the field name `sgi-id` has a hyphen, so in JavaScript use `feature.properties["sgi-id"]`.

## Joining files

`glacier id` (mass balance, length change) = `SGI-ID` (volume change) = `sgi-id` (GeoJSON) = the ID at the start of the ice thickness file names (e.g. `B82-14`). Join on this ID, not on the name.

## Glaciers

43 glaciers have mass balance data. Records with at least 29 years and length change + volume change data:

| Glacier | ID | Mass balance years |
|---|---|---|
| Silvrettagletscher | A10g-05 | 1915–2025 |
| Grosser Aletschgletscher | B36-26 | 1915–2025 |
| Claridenfirn | A50i-19 | 1915–2025 |
| Schwarzberggletscher | B52-24 | 1956–2025 |
| Allalingletscher | B52-29 | 1956–2025 |
| Hohlaubgletscher | B52-32 | 1956–2025 |
| Griesgletscher | B45-04 | 1962–2025 |
| Glacier du Giétro | B82-14 | 1967–2025 |
| Rhonegletscher | B43-03 | 1885–2025 (44 years, with gaps) |
| Ghiacciaio del Basòdino | C14-10 | 1992–2025 |
| Glacier de Corbassière | B83-03 | 1997–2025 |
