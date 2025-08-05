---
{"dg-publish":true,"permalink":"/locations/the-amber-realms/","tags":["Display"],"updated":"2025-06-10T19:11:11.145+01:00"}
---

### Static Map
![ZoomedOutMapOfAmberRealms.jpg](/img/user/Admin/Attachments/ZoomedOutMapOfAmberRealms.jpg)

### Interactive Map (Unavailable Online)

```leaflet  
id: TheAmberRealmsMap ### Must be unique with no spaces  
image: [[ZoomedOutMapOfAmberRealms.jpg]] ### Link to the map image file  
bounds: [[0,0], [3072, 4096]] ### Size of the map in px Width_x, Height_y  
height: 56% ### Size of the leaflet embed in px on your screen  
width: 100% ### Size of the leaflet embed in your note  
lat: 1800 ### To center the map, make this half of the map width.  
long: 1700 ### To center the map, make this half of the map height.  
minZoom: -3 ### Controls how far away from the map you can zoom out. Hover over the target icon to see the current level.  
maxZoom: 1 ### Controls how far towards the map you can zoom in. Hover over the target icon to see the current level.  
defaultZoom: -1.5 ### Sets the default zoom level when the map loads. Hover over the target icon to see the current level.  
zoomDelta: 0.5 ### Adjust how much the zoom changes when you zoom in or out. 
```
