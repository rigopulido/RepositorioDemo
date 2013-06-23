## Markers

> The framework adds several new marker types geared towards dynamic data visualization.  See the [Markers](http://humangeo.github.com/leaflet-dvf/examples/html/markers.html) example for an illustration of each of these markers.

### L.MapMarker

> Creates an SVG-based map marker, similar to the default Leaflet image-based marker but fully customizable using the basic L.Path properties

#### Usage
`L.MapMarker(<LatLng> LatLng, <Marker options> options?);`

```javascript
var marker = new L.MapMarker(new L.LatLng(0, 0), {
	radius: 10,
	// L.Path style options
	...
});

map.addLayer(marker);
```

#### Options
Option | Type | Default | Description
--- | --- | --- | ---
numberOfSides | Number | 3 | If an inner radius is specified, then the marker will have a hole in center.  This property determines the shape of the hole.
rotation | Number | 0 | If an inner radius is specified, this controls the rotation of the hole in the center.
radius OR radiusX, radiusY | Number | 10 | The radius of the circular part of the marker, also adjusts the height of the marker
innerRadius OR innerRadiusX, innerRadiusY | Number | null | The inner radius of the marker hole in pixels.

### L.RegularPolygonMarker

<img alt="Bar Chart Marker" src="http://humangeo.github.com/leaflet-dvf/images/regularpolygonmarkers.png" width="290" height="72" style="width: 290px; height: 72px;"/>

> Creates an N-sided marker

#### Usage
`L.RegularPolygonMarker(<LatLng> LatLng, <Marker options> options?);`

```javascript
var marker = new L.RegularPolygonMarker(new L.LatLng(0, 0), {
	numberOfSides: 3,
	rotation: 60.0,
	radius: 10,
	// L.Path style options
	...
});

map.addLayer(marker);
```

#### Options
Option | Type | Default | Description
--- | --- | --- | ---
numberOfSides | Number | 3 | The number of sides the marker should have
rotation | Number | 0.0 | The angle in degrees that the marker should be rotated
radius OR radiusX, radiusY | Number | 10 | The radius of the marker in pixels 
innerRadius OR innerRadiusX, innerRadiusY | Number | null | The inner radius of the marker in pixels.  Specifying an innerRadius will produce a regular polygon with a hole in the middle.

### L.StarMarker

<img alt="Star Marker" src="http://humangeo.github.com/leaflet-dvf/images/stars.png" width="83" height="87" style="width: 83px; height: 87px;"/>

> Creates a star-shaped marker with N-points

#### Usage
`L.StarMarker(<LatLng> LatLng, <StarMarker options> options?);`

#### Options (in addition to the L.RegularPolygonMarker options defined above)
Option | Type | Default | Description
--- | --- | --- | ---
numberOfPoints | Number | 5 | The number of points the star should have

### ChartMarkers

<img alt="Bar Chart Marker" src="http://humangeo.github.com/leaflet-dvf/images/barchartmarker.png" width="83" height="87" style="width: 83px; height: 87px;"/><img alt="Radial Bar Chart Marker" src="http://humangeo.github.com/leaflet-dvf/images/radialbarchartmarker.png" width="83" height="87" style="width: 83px; height: 87px;"/><img alt="Pie Chart Marker" src="http://humangeo.github.com/leaflet-dvf/images/piechartmarker.png" width="83" height="87" style="width: 83px; height: 87px;"/><img alt="Coxcomb Chart Marker" src="http://humangeo.github.com/leaflet-dvf/images/coxcombchartmarker.png" width="83" height="87" style="width: 83px; height: 87px;"/><img alt="Stacked Regular Polygon Marker" src="http://humangeo.github.com/leaflet-dvf/images/stackedregularpolygon.png" width="83" height="87" style="width: 83px; height: 87px;"/><img alt="Radial Meter Marker" src="http://humangeo.github.com/leaflet-dvf/images/radialmetermarker.png" width="83" height="87" style="width: 83px; height: 87px;"/>

> Display dynamic charts (bar chart, radial bar chart, pie chart, coxcomb chart, etc.) as markers

#### Usage
`L.BarChartMarker(<LatLng> LatLng, <Chart options> options?);`
`L.RadialBarChartMarker(<LatLng> LatLng, <Chart options> options?);`
`L.PieChartMarker(<LatLng> LatLng, <Chart options> options?);`
`L.CoxcombChartMarker(<LatLng> LatLng, <Chart options> options?);`
`L.StackedRegularPolygonMarker(<LatLng> LatLng, <Chart options> options?);`
`L.RadialMeterMarker(<LatLng> LatLng, <Chart options> options?);`

```javascript
var options = {
	data: {
		'dataPoint1': Math.random() * 20,
		'dataPoint2': Math.random() * 20,
		'dataPoint3': Math.random() * 20,
		'dataPoint4': Math.random() * 20
	},
	chartOptions: {
		'dataPoint1': {
			fillColor: '#FEE5D9',
			minValue: 0,
			maxValue: 20,
			maxHeight: 20,
			displayText: function (value) {
				return value.toFixed(2);
			}
		},
		'dataPoint2': {
			fillColor: '#FCAE91',
			minValue: 0,
			maxValue: 20,
			maxHeight: 20,
			displayText: function (value) {
				return value.toFixed(2);
			}
		},
		'dataPoint3': {
			fillColor: '#FB6A4A',
			minValue: 0,
			maxValue: 20,
			maxHeight: 20,
			displayText: function (value) {
				return value.toFixed(2);
			}
		},
		'dataPoint4': {
			fillColor: '#CB181D',
			minValue: 0,
			maxValue: 20,
			maxHeight: 20,
			displayText: function (value) {
				return value.toFixed(2);
			}
		}
	},
	weight: 1,
	color: '#000000',
	... // Other L.Path style options
}

var barChartMarker = new L.BarChartMarker(new L.LatLng(0, 0), options);
```

#### Options (in addition to the *L.Path* style options)

Option | Type | Default | Description
--- | --- | --- | ---
data | Object | null | A set of key/value pairs that provides a data value for each property displayed by the marker 
chartOptions | Object | null | A set of key/value pairs that defines the options associated with each data property displayed by the marker.
