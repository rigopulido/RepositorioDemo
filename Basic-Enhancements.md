> Two new optional properties have been added to the basic L.Path properties to enable for a gradient fill and drop shadow.  For now, these properties are boolean values, but in the future, support might be added for fine-grained control over the appearance of gradients/drop shadows.

#### Usage
```javascript
var layer = new <Leaflet Path-based Layer (e.g. L.Polygon)>(<Constructor inputs>, {
	// L.Path style options
	...
	gradient: true,
	dropShadow: true
});
```

#### Options
Option | Type | Default | Description
--- | --- | --- | ---
gradient | Boolean | differs depending on the layer class (most new marker types use a gradient by default) | Specifying a value of true will fill the path with a gradient from white to the specified fillColor (top left - bottom right)
dropShadow | Boolean | false | Specifying a value of true will add a dropShadow to the path