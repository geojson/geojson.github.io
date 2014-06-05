---
layout: home
title: Proposed GeoJSON-LD Vocabulary
---

# Proposed GeoJSON-LD Vocabulary

See [https://github.com/geojson/geojson-ld](https://github.com/geojson/geojson-ld)
for vocabulary developments.

This document refers often to the [JSON-LD 1.0](http://www.w3.org/TR/json-ld/) W3C
Recommendation.

The *example.com* domain and *example.com/vocab#* URIs are used deliberately to 
dissuade you from using the vocabulary terms before the work is finished.


## Core Types

Below are linked data identifiers for the core GeoJSON types found in the [GeoJSON
1.0 Specification](geojson-spec.md).

### <a name="FeatureCollection">FeatureCollection</a>

*http://example.com/vocab#FeatureCollection*

Description: See [GeoJSON Section 2.3](geojson-spec.html#feature-collection-objects).

### <a name="Feature">Feature</a>

*http://example.com/vocab#Feature*

Description: See [GeoJSON Section 2.2](geojson-spec.html#feature-objects).

### <a name="Point">Point</a>

*http://example.com/vocab#Point*

Description: See [GeoJSON Section 2.1.2](geojson-spec.html#point).

### <a name="LineString">LineString</a>

*http://example.com/vocab#LineString*

Description: See [GeoJSON Section 2.1.4](geojson-spec.html#linestring).

### <a name="Polygon">Polygon</a>

*http://example.com/vocab#Polygon*

Description: See [GeoJSON Section 2.1.6](geojson-spec.html#polygon).

### <a name="MultiPoint">MultiPoint</a>

*http://example.com/vocab#MultiPoint*

Description: See [GeoJSON Section 2.1.3](geojson-spec.html#multipoint).

### <a name="MultiLineString">MultiLineString</a>

*http://example.com/vocab#MultiLineString*

Description: See [GeoJSON Section 2.1.5](geojson-spec.html#multilinestring).

### <a name="MultiPolygon">MultiPolygon</a>

*http://example.com/vocab#MultiPolygon*

Description: See [GeoJSON Section 2.1.7](geojson-spec.html#multipolygon).

### <a name="GeometryCollection">GeometryCollection</a>

*http://example.com/vocab#GeometryCollection*

Description: See [GeoJSON Section 2.1.8](geojson-spec.html#geometry-collection).


## Core Properties

Below are linked data identifiers for the core GeoJSON properties found in the
[GeoJSON 1.0 Specification](geojson-spec.html).

### <a name="bbox">bbox</a>

*http://example.com/vocab#bbox*

Description: See [GeoJSON Section 4](geojson-spec.html#bounding-boxes).

### <a name="coordinates">coordinates</a>

*http://example.com/vocab#coordinates*

Description: See [GeoJSON Section 2.1.1](geojson-spec.html#positions).

### <a name="features">features</a>

*http://example.com/vocab#features*

Description: See [GeoJSON Section 2.3](geojson-spec.html#feature-collection-objects).

### <a name="geometry">geometry</a>

*http://example.com/vocab#geometry*

Description: See [GeoJSON Section 2.1](geojson-spec.html#geometry-objects).

### <a name="id">id</a>

*http://example.com/vocab#id*

Description: See [GeoJSON Section 2.2](geojson-spec.html#feature-objects).

In the base GeoJSON-LD context, [http://geojson.org/contexts/geojson-base.jsonld](http://geojson.org/contexts/geojson-base.jsonld), **id** is declared to be an alias for the JSON-LD [**@id** keyword](http://www.w3.org/TR/json-ld/#node-identifiers).

### <a name="properties">properties</a>

*http://example.com/vocab#properties*

Description: See [GeoJSON Section 2.2](geojson-spec.html#feature-objects). These
are properties of a **Feature** that are bounded by its spatial and temporal
extents.

### <a name="type">type</a>

*http://example.com/vocab#type*

Description: See [GeoJSON Section 2](geojson-spec.html#geojson-objects).

In the base GeoJSON-LD context, [http://geojson.org/contexts/geojson-base.jsonld](http://geojson.org/contexts/geojson-base.jsonld), **type** is declared to be an alias for
`rdf:type`.

## Extension Types

Below are identifiers and descriptions of types not in the core GeoJSON
specification.

### <a name="Instant">Instant</a>

*http://www.w3.org/2006/time#Instant*

Description: Denotes a temporal entity with zero length, having only
a [**datetime**](#datetime) property.

### <a name="Interval">Interval</a>

*http://www.w3.org/2006/time#Interval*

Description: Denotes a temporal entity with non-zero length. Closed intervals
have [**start**](#start) and [**stop**](#stop) properties, while open ended
intervals may have one or the other.


## Extension Properties

### <a name="circa">circa</a>

*http://example.com/vocab#circa*

Description: The temporal bounding "box" of a GeoJSON object. Its domain is
[**FeatureCollection**](#FeatureCollection) and [**Feature**](#Feature). Its
range is [**Interval**](#Interval) (see above). Publishers are free to pad the
interval of **circa**; it does not have to exactly match the extent of 
[**when**](#when).

### <a name="datetime">datetime</a>

*http://www.w3.org/2006/time#inXSDDateTime*

Description: A moment in a common era calendar using astronomical years (0
indexed) using the ISO 8601 (or equivalently, [RFC
3339](http://www.ietf.org/rfc/rfc3339.txt)) format. The day before "1-01-01"
would be "0-12-31". No time interval is implied by an imprecise datetime value
such as "1000". The domain of this property is [**Instant**](#Instant).

### <a name="description">description</a>

*http://purl.org/dc/terms/description*

Description: Summary text or content. [**Feature**](#Feature) descriptions are
useful in popups.

### <a name="start">start</a>

*http://www.w3.org/2006/time#hasBeginning*

Description: A moment (as in [**datetime**](#datetime) above) at the beginning
of a time interval.  The domain of this property is [**Interval**](#Interval).

### <a name="stop">stop</a>

*http://www.w3.org/2006/time#hasEnding*

Description: A moment (as in [**datetime**](#datetime) above) at the end of
a time interval.  The domain of this property is [**Interval**](#Interval).

### <a name="title">title</a>

*http://purl.org/dc/terms/title*

Description: [**Feature**](#Feature) titles are useful in popups.

### <a name="when">when</a>

*http://example.com/vocab#when*

Description: The temporal extent of a Feature. Its domain is
[**Feature**](#Feature). Its range is [**Instant**](#Instant) or
[**Interval**](#Interval) (see above).

