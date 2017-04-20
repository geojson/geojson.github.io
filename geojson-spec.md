---
layout:  nav
title:   Obsolete
---
<!-- NAV -->
<nav id="nav">
### Contents

* [1\. Introduction](#introduction)
  * [1\.1\. Examples](#examples)
  * [1\.2\. Definitions](#definitions)
* [2\. GeoJSON Objects](#geojson-objects)
  * [2\.1\. Geometry Objects](#geometry-objects)
    * [2\.1\.1\. Positions](#positions)
    * [2\.1\.2\. Point](#point)
    * [2\.1\.3\. MultiPoint](#multipoint)
    * [2\.1\.4\. LineString](#linestring)
    * [2\.1\.5\. MultiLineString](#multilinestring)
    * [2\.1\.6\. Polygon](#polygon)
    * [2\.1\.7\. MultiPolygon](#multipolygon)
    * [2\.1\.8\. Geometry Collection](#geometry-collection)
  * [2\.2\. Feature Objects](#feature-objects)
  * [2\.3\. Feature Collection Objects](#feature-collection-objects)
* [3\. Coordinate Reference System Objects](#coordinate-reference-system-objects)
  * [3\.1\. Named CRS](#named-crs)
  * [3\.2\. Linked CRS](#linked-crs)
    * [3\.2\.1\. Link Objects](#link-objects)
* [4\. Bounding Boxes](#bounding-boxes)
* [Appendix A\. Geometry Examples](#appendix-a-geometry-examples)
  * [Point](#id2)
  * [LineString](#id3)
  * [Polygon](#id4)
  * [MultiPoint](#id5)
  * [MultiLineString](#id6)
  * [MultiPolygon](#id7)
  * [GeometryCollection](#geometrycollection)
* [Appendix B\. Contributors](#appendix-b-contributors)
</nav>

# This document is obsolete.  Please see [RFC 7946](https://tools.ietf.org/html/rfc7946) instead.

<!-- Document Info -->
<table class="docinfo">
  <tr>
    <th>Authors</th>
    <td>
      Howard Butler (Hobu Inc.),
      Martin Daly (Cadcorp),
      Allan Doyle (MIT),
      Sean Gillies (UNC-Chapel Hill),
      Tim Schaub (OpenGeo),
      Christopher Schmidt (MetaCarta)
    </td>
  </tr>
  <tr>
    <th>Revision</th>
    <td>1.0</td>
  </tr>
  <tr>
    <th>Date</th>
    <td>16 June 2008</td>
  </tr>
  <tr>
    <th>Abstract</th>
    <td>
      GeoJSON is a geospatial data interchange format based on JavaScript
      Object Notation (JSON).
    </td>
  </tr>
  <tr>
    <th>Copyright</th>
    <td>
      Copyright &copy; 2008 by the Authors. This work is licensed under a
      <a href="http://creativecommons.org/licenses/by/3.0/us/">
        Creative Commons Attribution 3.0 United States License</a>.
    </td>
  </tr>
  <tr>
    <th>Status</th>
    <td>
      Obsolete. Replaced by <a href="https://tools.ietf.org/html/rfc7946">RFC 7946</a>.
    </td>
  </tr>
</table>

## <a id="introduction" href="#introduction">1. Introduction</a>

GeoJSON is a format for encoding a variety of geographic data structures.  A
GeoJSON object may represent a geometry, a feature, or a collection of
features.  GeoJSON supports the following geometry types: Point, LineString,
Polygon, MultiPoint, MultiLineString, MultiPolygon, and GeometryCollection.
Features in GeoJSON contain a geometry object and additional properties, and a
feature collection represents a list of features.

A complete GeoJSON data structure is always an object (in JSON terms). In
GeoJSON, an object consists of a collection of name/value pairs -- also called
members. For each member, the name is always a string. Member values are either
a string, number, object, array or one of the literals: `true`, `false`, and
`null`. An array consists of elements where each element is a value as
described above. 


### <a id="examples" href="#examples">1.1. Examples</a>

A GeoJSON feature collection:

{% highlight javascript %}
  { "type": "FeatureCollection",
    "features": [
      { "type": "Feature",
        "geometry": {"type": "Point", "coordinates": [102.0, 0.5]},
        "properties": {"prop0": "value0"}
        },
      { "type": "Feature",
        "geometry": {
          "type": "LineString",
          "coordinates": [
            [102.0, 0.0], [103.0, 1.0], [104.0, 0.0], [105.0, 1.0]
            ]
          },
        "properties": {
          "prop0": "value0",
          "prop1": 0.0
          }
        },
      { "type": "Feature",
         "geometry": {
           "type": "Polygon",
           "coordinates": [
             [ [100.0, 0.0], [101.0, 0.0], [101.0, 1.0],
               [100.0, 1.0], [100.0, 0.0] ]
             ]
         },
         "properties": {
           "prop0": "value0",
           "prop1": {"this": "that"}
           }
         }
       ]
     }
{% endhighlight %}


### <a id="definitions" href="#definitions">1.2. Definitions</a>

* JavaScript Object Notation (JSON), and the terms object, name, value, array,
  and number, are defined in [IETF RFC 4627](http://www.ietf.org/rfc/rfc4627.txt).

* The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
  "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be
  interpreted as described in [IETF RFC 2119](http://www.ietf.org/rfc/rfc2119.txt).


## <a id="geojson-objects" href="#geojson-objects">2. GeoJSON Objects</a>

GeoJSON always consists of a single object. This object (referred to as the
GeoJSON object below) represents a geometry, feature, or collection of
features.

* The GeoJSON object may have any number of members (name/value pairs).

* The GeoJSON object must have a member with the name `"type"`. This member's
  value is a string that determines the type of the GeoJSON object.

* The value of the type member must be one of: `"Point"`, `"MultiPoint"`,
  `"LineString"`, `"MultiLineString"`, `"Polygon"`, `"MultiPolygon"`,
  `"GeometryCollection"`, `"Feature"`, or `"FeatureCollection"`. The case of the
  type member values must be as shown here.

* A GeoJSON object may have an optional `"crs"` member, the value of which must
  be a coordinate reference system object (see 
  [3. Coordinate Reference System Objects](#coordinate-reference-system-objects)).

* A GeoJSON object may have a `"bbox"` member, the value of which must be a
  bounding box array (see [4. Bounding Boxes](#bounding-boxes)).

### <a id="geometry-objects" href="#geometry-objects">2.1 Geometry Objects</a>

A geometry is a GeoJSON object where the type member's value is one of the
following strings: `"Point"`, `"MultiPoint"`, `"LineString"`,
`"MultiLineString"`, `"Polygon"`, `"MultiPolygon"`, or `"GeometryCollection"`.

A GeoJSON geometry object of any type other than `"GeometryCollection"` must
have a member with the name `"coordinates"`. The value of the coordinates member
is always an array. The structure for the elements in this array is determined
by the type of geometry.

#### <a id="positions" href="#positions">2.1.1. Positions</a>

A position is the fundamental geometry construct. The `"coordinates"` member of
a geometry object is composed of one position (in the case of a Point geometry),
an array of positions (LineString or MultiPoint geometries), an array of arrays
of positions (Polygons, MultiLineStrings), or a multidimensional array of
positions (MultiPolygon).

A position is represented by an array of numbers. There must be at least two
elements, and may be more. The order of elements must follow x, y, z order
(easting, northing, altitude for coordinates in a projected coordinate
reference system, or longitude, latitude, altitude for coordinates in a
geographic coordinate reference system). Any number of additional elements are
allowed -- interpretation and meaning of additional elements is beyond the
scope of this specification.

Examples of positions and geometries are provided in
[Appendix A. Geometry Examples](#appendix-a-geometry-examples).

#### <a id="point" href="#point">2.1.2. Point</a>

For type `"Point"`, the `"coordinates"` member must be a single position.

#### <a id="multipoint" href="#multipoint">2.1.3. MultiPoint</a>

For type `"MultiPoint"`, the `"coordinates"` member must be an array of
positions.

#### <a id="linestring" href="#linestring">2.1.4. LineString</a>

For type `"LineString"`, the `"coordinates"` member must be an array of two or
more positions.

A LinearRing is closed LineString with 4 or more positions. The first and last
positions are equivalent (they represent equivalent points). Though a
LinearRing is not explicitly represented as a GeoJSON geometry type, it is
referred to in the Polygon geometry type definition.

#### <a id="multilinestring" href="#multilinestring">2.1.5. MultiLineString</a>

For type `"MultiLineString"`, the `"coordinates"` member must be an array of
LineString coordinate arrays.

#### <a id="polygon" href="#polygon">2.1.6. Polygon</a>

For type `"Polygon"`, the `"coordinates"` member must be an array of LinearRing
coordinate arrays. For Polygons with multiple rings, the first must be the
exterior ring and any others must be interior rings or holes.

#### <a id="multipolygon" href="#multipolygon">2.1.7. MultiPolygon</a>

For type `"MultiPolygon"`, the `"coordinates"` member must be an array of
Polygon coordinate arrays.

#### <a id="geometry-collection" href="#geometry-collection">2.1.8 Geometry Collection</a>

A GeoJSON object with type `"GeometryCollection"` is a geometry object which
represents a collection of geometry objects.

A geometry collection must have a member with the name `"geometries"`. The value
corresponding to `"geometries"` is an array. Each element in this array is a
GeoJSON geometry object.

### <a id="feature-objects" href="#feature-objects">2.2. Feature Objects</a>

A GeoJSON object with the type `"Feature"` is a feature object.

* A feature object must have a member with the name `"geometry"`. The value of
  the geometry member is a geometry object as defined above or a JSON null
  value.

* A feature object must have a member with the name `"properties"`. The value of
  the properties member is an object (any JSON object or a JSON null value).

* If a feature has a commonly used identifier, that identifier should be
  included as a member of the feature object with the name `"id"`.

### <a id="feature-collection-objects" href="#feature-collection-objects">2.3. Feature Collection Objects</a>

A GeoJSON object with the type `"FeatureCollection"` is a feature collection
object.

An object of type `"FeatureCollection"` must have a member with the name
`"features"`. The value corresponding to `"features"` is an array. Each element
in the array is a feature object as defined above.

## <a id="coordinate-reference-system-objects" href="#coordinate-reference-system-objects">3. Coordinate Reference System Objects</a>

The coordinate reference system (CRS) of a GeoJSON object is determined by its
`"crs"` member (referred to as the CRS object below). If an object has no crs
member, then its parent or grandparent object's crs member may be acquired. If
no crs member can be so acquired, the default CRS shall apply to the GeoJSON
object.

* The default CRS is a geographic coordinate reference system, using the WGS84
  datum, and with longitude and latitude units of decimal degrees.

* The value of a member named `"crs"` must be a JSON object (referred to as the
  CRS object below) or JSON null. If the value of CRS is null, no CRS can be
  assumed.

* The crs member should be on the top-level GeoJSON object in a hierarchy (in
  feature collection, feature, geometry order) and should not be repeated or
  overridden on children or grandchildren of the object.

* A non-null CRS object has two mandatory members: `"type"` and `"properties"`.

* The value of the type member must be a string, indicating the type of CRS
  object.

* The value of the properties member must be an object.

* CRS shall not change coordinate ordering (see [2.1.1. Positions](#positions)).

### <a id="named-crs" href="#named-crs">3.1. Named CRS</a>

A CRS object may indicate a coordinate reference system by name. In this case,
the value of its `"type"` member must be the string `"name"`. The value of its
`"properties"` member must be an object containing a `"name"` member. The value
of that `"name"` member must be a string identifying a coordinate reference
system.  OGC CRS URNs such as `"urn:ogc:def:crs:OGC:1.3:CRS84"` shall be
preferred over legacy identifiers such as `"EPSG:4326"`:

{% highlight javascript %}
  "crs": {
    "type": "name",
    "properties": {
      "name": "urn:ogc:def:crs:OGC:1.3:CRS84"
      }
    }
{% endhighlight %}

### <a id="linked-crs" href="#linked-crs">3.2. Linked CRS</a>

A CRS object may link to CRS parameters on the Web. In this case, the value of
its `"type"` member must be the string `"link"`, and the value of its
`"properties"` member must be a Link object (see
[3.2.1. Link Objects](#link-objects)).

#### <a id="link-objects" href="#link-objects">3.2.1. Link Objects</a>

A link object has one required member: `"href"`, and one optional member:
`"type"`.

The value of the required `"href"` member must be a dereferenceable URI.

The value of the optional `"type"` member must be a string that hints at the
format used to represent CRS parameters at the provided URI. Suggested values
are: `"proj4"`, `"ogcwkt"`, `"esriwkt"`, but others can be used:

{% highlight javascript %}
  "crs": {
    "type": "link", 
    "properties": {
      "href": "http://example.com/crs/42",
      "type": "proj4"
      }
    }
{% endhighlight %}
    
Relative links may be used to direct processors to CRS parameters in an
auxiliary file:

{% highlight javascript %}
  "crs": {
    "type": "link",
    "properties": {
      "href": "data.crs",
      "type": "ogcwkt"
      }
    }
{% endhighlight %}

## <a id="bounding-boxes" href="#bounding-boxes">4. Bounding Boxes</a>

To include information on the coordinate range for geometries, features, or
feature collections, a GeoJSON object may have a member named `"bbox"`. The
value of the bbox member must be a 2\*n array where n is the number of
dimensions represented in the contained geometries, with the lowest values for
all axes followed by the highest values. The axes order of a bbox follows the
axes order of geometries. In addition, the coordinate reference system for the
bbox is assumed to match the coordinate reference system of the GeoJSON object
of which it is a member.

Example of a bbox member on a feature:

{% highlight javascript %}
  { "type": "Feature",
    "bbox": [-10.0, -10.0, 10.0, 10.0],
    "geometry": {
      "type": "Polygon",
      "coordinates": [[
        [-10.0, -10.0], [10.0, -10.0], [10.0, 10.0], [-10.0, 10.0]
        ]]
      }
    ...
    }
{% endhighlight %}

Example of a bbox member on a feature collection:

{% highlight javascript %}
  { "type": "FeatureCollection",
    "bbox": [100.0, 0.0, 105.0, 1.0],
    "features": [
      ...
      ] 
    }
{% endhighlight %}

## <a id="appendix-a-geometry-examples" href="#appendix-a-geometry-examples">Appendix A. Geometry Examples</a>

Each of the examples below represents a complete GeoJSON object. Note that
unquoted whitespace is not significant in JSON. Whitespace is used in the
examples to help illustrate the data structures, but is not required.

### <a id="id2" href="#id2">Point</a>

Point coordinates are in x, y order (easting, northing for projected
coordinates, longitude, latitude for geographic coordinates):

{% highlight javascript %}
  { "type": "Point", "coordinates": [100.0, 0.0] }
{% endhighlight %}

### <a id="id3" href="#id3">LineString</a>

Coordinates of LineString are an array of positions (see [2.1.1. Positions](#positions)):

{% highlight javascript %}
  { "type": "LineString",
    "coordinates": [ [100.0, 0.0], [101.0, 1.0] ]
    }
{% endhighlight %}

### <a id="id4" href="#id4">Polygon</a>

Coordinates of a Polygon are an array of LinearRing coordinate arrays. The
first element in the array represents the exterior ring. Any subsequent
elements represent interior rings (or holes).

No holes:

{% highlight javascript %}
  { "type": "Polygon",
    "coordinates": [
      [ [100.0, 0.0], [101.0, 0.0], [101.0, 1.0], [100.0, 1.0], [100.0, 0.0] ]
      ]
   }
{% endhighlight %}

With holes:

{% highlight javascript %}
  { "type": "Polygon",
    "coordinates": [
      [ [100.0, 0.0], [101.0, 0.0], [101.0, 1.0], [100.0, 1.0], [100.0, 0.0] ],
      [ [100.2, 0.2], [100.8, 0.2], [100.8, 0.8], [100.2, 0.8], [100.2, 0.2] ]
      ]
   }
{% endhighlight %}

### <a id="id5" href="#id5">MultiPoint</a>

Coordinates of a MultiPoint are an array of positions:

{% highlight javascript %}
  { "type": "MultiPoint",
    "coordinates": [ [100.0, 0.0], [101.0, 1.0] ]
    }
{% endhighlight %}

### <a id="id6" href="#id6">MultiLineString</a>

Coordinates of a MultiLineString are an array of LineString coordinate arrays:

{% highlight javascript %}
  { "type": "MultiLineString",
    "coordinates": [
        [ [100.0, 0.0], [101.0, 1.0] ],
        [ [102.0, 2.0], [103.0, 3.0] ]
      ]
    }
{% endhighlight %}

### <a id="id7" href="#id7">MultiPolygon</a>

Coordinates of a MultiPolygon are an array of Polygon coordinate arrays:

{% highlight javascript %}
  { "type": "MultiPolygon",
    "coordinates": [
      [[[102.0, 2.0], [103.0, 2.0], [103.0, 3.0], [102.0, 3.0], [102.0, 2.0]]],
      [[[100.0, 0.0], [101.0, 0.0], [101.0, 1.0], [100.0, 1.0], [100.0, 0.0]],
       [[100.2, 0.2], [100.8, 0.2], [100.8, 0.8], [100.2, 0.8], [100.2, 0.2]]]
      ]
    }
{% endhighlight %}

### <a id="geometrycollection" href="#geometrycollection">GeometryCollection</a>

Each element in the geometries array of a GeometryCollection is one of the
geometry objects described above:

{% highlight javascript %}
  { "type": "GeometryCollection",
    "geometries": [
      { "type": "Point",
        "coordinates": [100.0, 0.0]
        },
      { "type": "LineString",
        "coordinates": [ [101.0, 0.0], [102.0, 1.0] ]
        }
    ]
  }
{% endhighlight %}

## <a id="appendix-b-contributors" href="#appendix-b-contributors">Appendix B. Contributors</a>

The GeoJSON format specification is the product of discussion on the GeoJSON
list: <http://lists.geojson.org/listinfo.cgi/geojson-geojson.org>
