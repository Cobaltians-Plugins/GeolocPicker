# Geoloc Picker Plugin

Geoloc plugin allows to select a location using GoogleMaps (for Android) or Plans (for iOS).

### How to use

* import the plugin to your project as explained [here](https://github.com/cobaltians/cobalt/wiki/Plugins-usage)
* Add the cobalt.geolocpicker.js to your web JS folder
* Add an html link to the cobalt.geolocpicker.js plugin script after the cobalt link in the HEAD tag

## cobalt.geolocPicker

Use the `cobalt.geolocPicker()` method like this


```
cobalt.geolocPicker({
    location: "48.758405, -3.470589", 
    address: "Kristal, 3 Rue Fulgence Bienvenue, 22300 Lannion"
  }, function(data){
    cobalt.log('location changed to', data);
});
```

Here is the detail of data sent by the web :

location : (string) The coordinates "latitude, longitude" of current location (it can be null).
address : (string) The address related to current location (it can be null).

If `location` is null, maps opens without Marker, on a default location, with instructions on bottom of the screen.
If `location` has a valid value, maps opens zoomed on Marked location, with related address on bottom of the screen.

User can long-press the map to select a new location :
- Marker is displayed on new location
- Address is displayed on the bottom of the screen.

Pressing `Clear` button, next to address, unselect the location:
- Marker is removed
- Address is removed (displaying default instructions)

Pressing `Save` button send callback to web with selected location's `location` and `address` into the `data` object.
If there's no selected location, callback send an empty data object, and location is changed to "Empty".

```
{ 
    location: "48.758405, -3.470589", 
    address: "Kristal, 3 Rue Fulgence Bienvenue, 22300 Lannion"
}
```
Pressing `Back` button close Maps with no change to the web.
