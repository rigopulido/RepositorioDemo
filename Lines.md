### L.ArcedPolyline

> Draws an arced polyline.  Rather than drawing a straight line from latlng1 to latlng2, this class draws an arced line from latlng1 to latlng2.  The height of the arc is proportional to the distance between latlng1 and latlng2 and defined by a customizable L.LinearFunction instance.  This is useful for illustrating spatial relationships, flight paths, etc.

#### Usage
`L.ArcedPolyline(<LatLng[]> latlngs, <ArcedPolyline options> options?);`

```javascript
var arcedPolyline = new L.ArcedPolyline([...], {
	distanceToHeight: new L.LinearFunction([0, 0], [4000, 400]),
	color: '#FF00000',
	weight: 4
});

map.addLayer(arcedPolyline);
```

#### Options (in addition to L.Path style options)
Option | Type | Default | Description
--- | --- | --- | ---
distanceToHeight | L.LinearFunction | new L.LinearFunction([0, 5], [1000, 200]) | An L.LinearFunction instance that maps the distance between two points to an arc height in pixels