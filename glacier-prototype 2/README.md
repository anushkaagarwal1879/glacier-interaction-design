# Prototype Specification: Swiss Glaciers

## General

- **Project:** Interactive visualisation showing how a single Swiss glacier has changed over the years. The user picks a glacier and a range of years. The same data can be shown in two modes, switched with a toggle in the top right:
  - **Regular:** a radar chart comparing five metrics (total mass, retreat, ELA, thickness, area), one polygon per year
  - **Isotype:** pictogram charts in the style of Otto Neurath's Isotype, one metric at a time (one symbol = a fixed amount, more = more symbols, never bigger symbols)
  The flip between the two modes is the core idea: abstract numbers first, then something people can count and relate to.
- **Technology:** Web prototype using **d3.js** (plain HTML, CSS and JavaScript, no build tools). Single page, landscape layout. Mode changes and year changes animate (around 1 second), they do not jump.
- **Data:** All data files are in the `data/` folder. Use only this data; do not invent values. If a value is missing for a glacier or year, show it as missing.

## Layout

| Position | Element |
|---|---|
| Top left | Glacier map thumbnail with location pin |
| Top centre | Dropdown: "Name of the glacier" "Location" ˅ |
| Top right | Toggle: Regular \| Isotype |
| Centre | Main chart (radar chart or Isotype chart) |
| Bottom left | About / explanation text |
| Bottom centre | Year legend (colour per year) |
| Bottom right | Year slider with one tick per year |

## How this specification is organized

- Every screen of the prototype has its own folder in `screens/`, numbered in the order a user sees them (`01_overview`, `02_glacier_dropdown`, …).
- Each screen folder contains a `README.md` with the description of that screen, plus one or more photos of the paper prototype.
- **All images in a screen folder belong to that screen.** `screen.jpg` is the main photo; additional photos show other states of the same screen (e.g. `state_no-data.jpg`).
