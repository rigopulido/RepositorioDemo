The Leaflet DVF is an extension to [CloudMade][]'s [Leaflet][] JavaScript mapping library.
The primary goal of the framework is to simplify data visualization and thematic mapping.

![Markers](http://humangeo.github.com/leaflet-dvf/images/markers.png "Markers")
![Election Mapping](http://humangeo.github.com/leaflet-dvf/images/electionmapping.png "Election Mapping")
![Country Data](http://humangeo.github.com/leaflet-dvf/images/countrydata.png "Country Data")

It includes:

New marker types (see the markers example below):

* MapMarker - create an SVG-based map marker similar to Leaflet's image-based marker, but fully customizable via L.Path style properties
* RegularPolygonMarker - create N-sided shapes like triangles, squares, hexagons, etc.
* StarMarker - create stars with N points
* ChartMarkers - useful for displaying multiple data properties at each location:
	* BarChartMarker
	* PieChartMarker
	* RadialBarChartMarker
	* CoxcombChartMarker
	* RadialMeterMarker
	* StackedRegularPolygonMarker - a variation on the bar chart

Functions for easily mapping data properties to Leaflet style values:

* LinearFunction
* Color functions:
	* HSLHueFunction - vary the output hue based on a data property
	* HSLSaturationFunction - vary the output saturation based on a data property
	* HSLLuminosityFunction - vary the output lightness/luminosity based on a data property
	* Various RGB functions
* PiecewiseFunction - use multiple LinearFunction classes in sequence (e.g. vary a color from white to yellow, yellow to red)

New layer types that simplify reading and visualizing any JSON-based data structure:

* DataLayer
* ChartDataLayer
* ChoroplethDataLayer
* Others

GeoJSON polygons for countries and US states to support Choropleth mapping.  Countries are generated from:  https://github.com/johan/world.geo.json.
Just include these JavaScript files if you plan to build a country or US state choropleth.  
Polygons are indexed via a state or country code and lookups are created to map various state/country code formats to the default index format.

Automatic legend generation and a simple legend control.
To generate a legend, just call getLegend on any DataLayer, or use the provided legend control and the legend will be displayed automatically.

Support for gradient fills and drop shadows.

*NOTE:  The dist folder includes a minified version of the full framework as well as a minified version of the code required to use the new markers*
*Use leaflet-dvf.markers.min.js if you want to use the new markers without the rest of the framework*