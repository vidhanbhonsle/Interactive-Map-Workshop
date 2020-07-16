# Search for all hospitals around us and place markers on them
Add the following code before </script> tag

```javascript

            function drawCircle(){
                var circle = new H.map.Circle(myPos,5000);
                map.addObject(circle);
            }

            drawCircle();
```
</br> Double-click on saved file to view on browser


[![Foo](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/img/s4.png)](https://github.com/vidhanbhonsle/Interactive-Map-Workshop/blob/master/Step4.md) 
