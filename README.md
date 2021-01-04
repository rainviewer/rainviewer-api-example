# RainViewer API Example
Easy to understand HTML + JS code, which displays weather radar (past and future) and infrared satellite tiles on the map. The main using the [Leaflet.js](https://leafletjs.com) library with [OpenStreetMap](https://openstreetmap.org) as a base map solution. Version for [Google Maps](https://developers.google.com/maps/documentation/javascript/overview) and [MapBox GL JS](https://docs.mapbox.com/mapbox-gl-js/api/) also available in a separate files.

Check it in your browser: [rainviewer-api-example.html](https://rainviewer.github.io/rainviewer-api-example/rainviewer-api-example.html)

### What covered here
* How to download the latest available API JSON with the available map products and frames.
* How to add tiled layers into the mapping library.
* How to animate, move forward or backward in the animation.
* How to display frame time.
* How to change options and map products.

### What does not covered here
* How to update the API JSON periodically and add new frames or replace completely outdated forecast.
* Memory and performance optimizations.

## Mapbox and Google Maps examples
For MapBox and Google Maps, you need to use a pretty similar code, but you need to put your API key in that examples to display the base map. Search for YOUR_API_KEY_HERE in the source code and replace it with your own key. These files will not display the map until you put your API KEY in it.