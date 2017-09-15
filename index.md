---
layout: home
title: GeoJSON
---

# <span class="fkin">G</span>eo<span class="fkin">J</span>SON

GeoJSON is a format for encoding a variety of geographic data structures.

{% highlight json %}
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

GeoJSON supports the following geometry types: `Point`, `LineString`,
`Polygon`, `MultiPoint`, `MultiLineString`, and `MultiPolygon`. Geometric
objects with additional properties are `Feature` objects. Sets of features are
contained by `FeatureCollection` objects.

## [The GeoJSON Specification (RFC 7946)](https://tools.ietf.org/html/rfc7946)

In 2015, the Internet Engineering Task Force (IETF), in conjunction with the
original specification authors, formed a [GeoJSON
WG](https://datatracker.ietf.org/wg/geojson/charter/) to standardize GeoJSON.
[RFC 7946](https://tools.ietf.org/html/rfc7946) was published in August 2016
and is the new standard specification of the GeoJSON format, replacing the
2008 GeoJSON specification.
