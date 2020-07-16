# Render a Map
Open your favourite IDE or a simple code editor like notepad or notepad++

Copy the code below into your editor.

``` html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Smart Cities</title>
        <!-- SCRIPTS -->
        <meta name="viewport" charset="UTF-8" content="initial-scale=1.0, width=device-width" />
        <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-core.js"></script>
        <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-service.js"></script>
        <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-ui.js"></script>
        <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-mapevents.js"></script>
        <link rel="stylesheet" type="text/css" href="https://js.api.here.com/v3/3.1/mapsjs-ui.css"/> 
    </head>
    <body>
        <div id="map" style="width: 100vw; height: 100vh; background: #39B6B3;" ></div> 
        <script>
            var platform = new H.service.Platform({
                apikey: "YOUR_JS_APIKEY"
            });

            // Obtain the default map types from the platform object:

            var defaultLayers = platform.createDefaultLayers();
            var myPos = {lat: 48.69429, lng: 9.1866};

            // Instantiate (and display) a map object:

            var map = new H.Map(
                document.getElementById('map'),
                defaultLayers.vector.normal.map,
                {
                    zoom: 11,
                    center: myPos
                });

            var ui = H.ui.UI.createDefault(map, defaultLayers);

            var mapEvents = new H.mapevents.MapEvents(map);

            var behavior = new H.mapevents.Behavior(mapEvents);
        </script>
    </body>
</html>
```
## Save the file as HERE_JS_Workshop.html

</br> Double-click on saved file to view on browser

## Add a position marker using map object of Interactive maps API
Add the following code before </script> tag

```javascript
            // create a marker object 

            var posMarker = new H.map.Marker(myPos);
            
            // Add the marker to the map 

            map.addObject(posMarker);
```
</br> Double-click on saved file to view on browser

## Add multiple marker
Add the following code before </script> tag

```javascript
           let locations = [
			{ lat: 31.22, lng: -91.02 },
			{ lat: 30.22, lng: -88.02 },
			{ lat: 29.22, lng: -89.02 },
			{ lat: 28.22, lng: -88.02 },
			{ lat: 27.22, lng: -94.02 },
		];

		locations.forEach(l => {
			map.addObject(new H.map.Marker(l));
		});
```
</br> Double-click on saved file to view on browser

[![Foo](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/img/s3.png)](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/Step3.md) 

