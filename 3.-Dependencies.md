Required:
* [Leaflet](http://leafletjs.com/)

Optional - required for particular classes to work:
* [Underscore JS](http://underscorejs.org/)
* [Moment JS](http://momentjs.com/)
* [geohash.js](https://github.com/davetroy/geohash-js)
* [JavaScript Topology Suite (JSTS)](https://github.com/bjornharrtell/jsts)
* [Core Framework SVG Utilities](https://code.google.com/p/core-framework/source/browse/trunk/plugins/svg.js) *Required for full functionality in archaic browsers (see note below)*
* [TopoJSON](https://github.com/mbostock/topojson) *Recommended/required for US county lookups*

Using the framework in IE8 and below:

**Special thanks to Keith Chew of [e3solutions](http://www.e3solutions.net) for testing and getting things working in IE8 and below.  This is still an on-going effort, so additional bug fixes may be forthcoming.  The examples provided here may need some tweaking to work in IE8 and below**

As you may or may not be aware, IE8 and below do not support SVG.  Leaflet and most SVG frameworks mitigate this problem by using Vector Markup Language (VML) instead of SVG when rendering custom shapes and paths.
With the latest version of the framework, most of the components will work without requiring any extra dependencies.  However, L.RadialBarChartMarker and L.PieChartMarker will require including the [Core Framework SVG Utilities](https://code.google.com/p/core-framework/source/browse/trunk/plugins/svg.js).  These utilities can convert more complex SVG shapes into corresponding VML shapes.
