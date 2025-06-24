# Maplibre Thumbnails

### Demo 1: https://do-me.github.io/maplibre-thumbnails/

Create png thumbnails with maplibre, pmtiles and geometries of your choice!

![image](https://github.com/user-attachments/assets/18265def-7337-4b01-836c-f77b793f8628)

Maplibre renders the vector tiles on canvas, so you (via JS) or the browser can easily access them and generate a png for you. Try the live app in your browser!
Here you see 2x each: markers, lines, polygons or empty maps.

## Loading a different style

The style is currently simplified like this, so that the thumnbails render faster. For my personal use case, the thumbnails were rather decorative, so I did not need any other info:

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

You can however very well change it to the official protomaps style.json: 

### Demo 2: https://do-me.github.io/maplibre-thumbnails/load_style_from_file.html

![image](https://github.com/user-attachments/assets/d02cd994-49d4-429a-81ff-428bbf149fc2)

## Limitations 

This method can be used to "print" a map, e.g. for PDF reports. However, apparently something changed with protomaps sprites and glyphs recently so some small tweaks are required print everything 100% as displayed on the map. 

Meanwhile, you can see this demo for printing a map with geometries "as is" using openfreemap with: 

`style: 'https://tiles.openfreemap.org/styles/liberty'`

### Demo 3: https://do-me.github.io/maplibre-thumbnails/simple_print.html

This is the actual output you get when clicking the download button (on a wide screen):
![image](https://github.com/user-attachments/assets/b1be82f3-bc1a-4789-89b1-2904e17c55f0)



