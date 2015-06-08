---
layout: home
title: GeoJSON
---

# <span class="fkin">G</span>eo<span class="fkin">J</span>SON

GeoJSON is a format for encoding a variety of geographic data structures.

{% highlight javascript %}
{
  "type": "Feature",
  "geometry": {
    "type": "Point",
    "coordinates": [125.6, 10.1]
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

## Developments

The GeoJSON authors are writing an Internet-Draft that updates GeoJSON,
[draft-butler-geojson](https://tools.ietf.org/html/draft-butler-geojson-05),
and are working on the charter for a working group that would standardize
the format. Please see 
[https://github.com/geojson/draft-geojson](https://github.com/geojson/draft-geojson)
for details on each of these efforts.
