---
layout: home
title: GeoJSON
---

# GeoJSON

GeoJSON is a format for encoding a variety of geographic data structures.

{% highlight javascript %}
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [-125.6, 10.1]
  },
  "properties": {
    "name": "Dinagat Islands"
  }
}
{% endhighlight %}

GeoJSON supports the following geometry types: `Point`, `LineString`, `Polygon`,
`MultiPoint`, `MultiLineString`,  and `MultiPolygon`.  Lists of geometries are
represented by a `GeometryCollection`.  Geometries with additional properties
are `Feature` objects.  And lists of features are represented by a
`FeatureCollection`.

## Learn More

See the [full specification](geojson-spec.html) for more
detail.
