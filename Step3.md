# Search for all hospitals around us and place markers on them

Add the following code before </script> tag

```javascript
           
            function showHospitals(){

                let param = {
                    at : myPosition.lat+','+myPosition.lng,
                    q: "hospital",
                    limit:10
                }; 

                service.browse(param,displayHospitals,alert);
            }
```
</br> 

# Lets add nice markers to display these hospitals

Add the following code before </script> tag

```javascript
        function displayHospitals(response){

            var takeOutIcon = new H.map.Icon('img/takeout.png');

            var restGroup = new H.map.Group();

            for(let i = 0; i<response.items.length; i++){
                let restPosition = response.items[i].position; 
              
                let data = response.items[i].title;
              
                let restMarker = new H.map.Marker(restPosition,{icon: takeOutIcon} );

                restGroup.addObject(restMarker);
            }

            map.addObject(restGroup);
        }
```

[![Foo](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/img/s4.png)](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/Step4.md) 
