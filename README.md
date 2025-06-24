# Maplibre Thumbnails

Create png thumbnails with maplibre, pmtiles and geometries of your choice!

![image](https://github.com/user-attachments/assets/18265def-7337-4b01-836c-f77b793f8628)

Maplibre renders the vector tiles on canvas, so you (via JS) or the browser can easily access them and generate a png for you. Try the live app in your browser!
Here you see 2x each: markers, lines, polygons or empty maps.

The style is currently simplified but you can very well change it to the official protomaps style.json by simply exchaning it here or loading it from a file: 

```javascript
const style = {
    version: 8,
    sources: { "protomaps": { type: "vector", url: `pmtiles://${PMTILES_URL}` } },
    layers: [
        { "id": "background", "type": "background", "paint": { "background-color": "#f0f2f5" } },
        { "id": "water", "source": "protomaps", "source-layer": "water", "type": "fill", "paint": { "fill-color": "#aadaff" } },
        { "id": "roads", "source": "protomaps", "source-layer": "roads", "type": "line", "paint": { "line-color": "#e0e0e0", "line-width": 1 } },
        { "id": "buildings", "source": "protomaps", "source-layer": "buildings", "type": "fill", "paint": { "fill-color": "#cccccc" } }
    ]
};
```
