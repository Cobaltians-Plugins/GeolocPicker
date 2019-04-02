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

- `location` : (optional, string) The coordinates "latitude, longitude" of current location.
- `address` : (optional, string) The address related to current location.

If `location` is null, the map opens without marker, on a default location, with instructions on bottom of the screen.

If `location` has a valid value, the map opens, zoomed on marker location, with related address on bottom of the screen.

User can long-press the map to select a new location :
- marker is displayed on new location
- address is displayed on the bottom of the screen.

Pressing `Clear` button, next to address, unselect the location:
- marker is removed
- address is removed (displaying default instructions)

Pressing `Save` button sends callback to web with selected location's `location` and `address` into the `data` object.

```
{ 
    location: "48.758405, -3.470589", 
    address: "Kristal, 3 Rue Fulgence Bienvenue, 22300 Lannion"
}
```

If there's no selected location, callback sends an empty data object.

Pressing `Back` button closes the map and does not send anything to the web.
