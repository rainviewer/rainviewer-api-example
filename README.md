# Rain Viewer API Example

Simple HTML + JS examples demonstrating the Rain Viewer Weather Maps API for personal use.

## Personal Use API Limitations

- **Max zoom:** Level 7 (512px tiles)
- **Color scheme:** Universal Blue only
- **Data:** Past radar data only (no forecast/nowcast, no satellite)
- **Format:** PNG only

## Examples

### Leaflet + OpenStreetMap
[rainviewer-api-example.html](https://rainviewer.github.io/rainviewer-api-example/rainviewer-api-example.html)

Uses [Leaflet.js](https://leafletjs.com) with [OpenStreetMap](https://openstreetmap.org) as a base map.

### MapLibre GL JS
[rainviewer-maplibre-example.html](https://rainviewer.github.io/rainviewer-api-example/rainviewer-maplibre-example.html)

Uses [MapLibre GL JS](https://maplibre.org) with Rain Viewer vector base map.

## What's Covered

- Downloading the latest API JSON with available map frames
- Adding tiled radar layers to mapping libraries
- Animating through frames (play/stop, prev/next)
- Displaying frame timestamps

## What's Not Covered

- Periodic API JSON updates for new frames
- Memory and performance optimizations

