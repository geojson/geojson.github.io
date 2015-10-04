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

See the [full specification](geojson-spec.html) for more detail.

See also
[https://datatracker.ietf.org/doc/draft-butler-geojson/](https://datatracker.ietf.org/doc/draft-butler-geojson/),
an Internet-Draft updating and clarifying the original specification.

## IETF Geographic JSON Working Group

The Internet Engineering Task Force, in conjunction with the original
specification authors, has formed the [Geographic JSON
WG](https://datatracker.ietf.org/wg/geojson/charter/), geojson for short, to
standardize the format. Work continues on GitHub at
[https://github.com/geojson/draft-geojson](https://github.com/geojson/draft-geojson).

