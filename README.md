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
    cobalt.log('status', data.status, data);
});
```

Here is what the native side is doing next :

- If no location is selected: Maps is displayed on default location, with Instructions label on "How to select a location". User can long press on map to add a Marker, Instruction label disappears, and current address and Clear button are displayed.
- If a location is selected: Maps is displayed centered on location's coordinates with a Marker on it, with Address label and Clear button. User can long press on map to change Marker location, address in label is also changed.
- Clicking on "Clear" button remove Maps Marker, remove address and clear button, and display Instructions label.
- Clicking on "Save", close `MapActivity` and send callback to web with Marker's `location` and `address` into the `data` object.


```
{ 
    location: "48.758405, -3.470589", 
    address: "Kristal, 3 Rue Fulgence Bienvenue, 22300 Lannion"
}
```
