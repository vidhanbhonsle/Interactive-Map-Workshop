# Render a Map and place a marker on our current position with a custom image

## Copy the code below in the file 'index.html'

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

# Changing the language of the map
- To change the language, change the 'en-US' to the language code you want:
- en-US – English (United States)
- de-DE – German
- es-ES – Spanish
- fi-FI – Finnish
- fr-FR – French
- it-IT – Italian
- nl-NL – Dutch
- pl-PL – Polish
- pt-BR – Portuguese (Brazil)
- pt-PT – Portuguese (Portugal)
- ru-RU – Russian
- tr-TR – Turkish
- zh-CN – Chinese (China)

# Adding a position marker using map object of Interactive maps API
- Add a folder named img inside the folder Food_Delivery_With_HERE
- Inside the folder img, save the image you want as the icon for restaurants and home
- You can also download the ones I used for [home](img/home.png) and [restaurants](img/takeout.png)
- Add the following code before </script> tag


```javascript
            // create an icon for the marker. Choose any image you want. I created mine using draw.io 
            
            var homeIcon = new H.map.Icon('img/home.png'); 
            
            var posMarker = new H.map.Marker(myPosition,{icon:homeIcon});
                
            // Add the marker to the map 

        map.addObject(posMarker);
```
### Click on the 'Go Live' button on the bottom right of your VSCODE application window and see your application open in your default browser

[![Foo](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/img/s3.png)](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/Step3.md) 

