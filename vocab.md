---
layout: home
title: Proposed GeoJSON-LD Vocabulary
---

# Proposed GeoJSON-LD Vocabulary

See [https://github.com/geojson/geojson-ld](https://github.com/geojson/geojson-ld)
for vocabulary developments.

This document refers often to the [JSON-LD 1.0](http://www.w3.org/TR/json-ld/) W3C
Recommendation.

The example.com domain and example.com/vocab# URIs are used deliberately to 
dissuade you from publishing GeoJSON-LD until this is finalized.


## Core Types

Below are linked data identifiers for the core GeoJSON types found in the [GeoJSON
1.0 Specification](geojson-spec.md).

### FeatureCollection

*http://example.com/vocab#FeatureCollection*

#### Description

See [GeoJSON Section 2.3](geojson-spec.html#feature-collection-objects).

### Feature

*http://example.com/vocab#Feature*

#### Description

See [GeoJSON Section 2.2](geojson-spec.html#feature-objects).

### Point

*http://example.com/vocab#Point*

#### Description

See [GeoJSON Section 2.1.2](geojson-spec.html#point).

### LineString

*http://example.com/vocab#LineString*

#### Description

See [GeoJSON Section 2.1.4](geojson-spec.html#linestring).

### Polygon

*http://example.com/vocab#Polygon*

#### Description

See [GeoJSON Section 2.1.6](geojson-spec.html#polygon).

### MultiPoint

*http://example.com/vocab#MultiPoint*

#### Description

See [GeoJSON Section 2.1.3](geojson-spec.html#multipoint).

### MultiLineString

*http://example.com/vocab#MultiLineString*

#### Description

See [GeoJSON Section 2.1.5](geojson-spec.html#multilinestring).

### MultiPolygon

*http://example.com/vocab#MultiPolygon*

#### Description

See [GeoJSON Section 2.1.7](geojson-spec.html#multipolygon).

### GeometryCollection

*http://example.com/vocab#GeometryCollection*

#### Description

See [GeoJSON Section 2.1.8](geojson-spec.html#geometry-collection).


## Core Properties

Below are linked data identifiers for the core GeoJSON properties found in the
[GeoJSON 1.0 Specification](geojson-spec.html).

### bbox

*http://example.com/vocab#bbox*

#### Description

See [GeoJSON Section 4](geojson-spec.html#bounding-boxes).

### coordinates

*http://example.com/vocab#coordinates*

#### Description

See [GeoJSON Section 2.1.1](geojson-spec.html#positions).

### features

*http://example.com/vocab#features*

#### Description

See [GeoJSON Section 2.3](geojson-spec.html#feature-collection-objects).

### geometry

*http://example.com/vocab#geometry*

#### Description

See [GeoJSON Section 2.1](geojson-spec.html#geometry-objects).

### id

*http://example.com/vocab#id*

#### Description

See [GeoJSON Section 2.2](geojson-spec.html#feature-objects).

### properties

*http://example.com/vocab#properties*

#### Description

See [GeoJSON Section 2.2](geojson-spec.html#feature-objects).

### type

*http://example.com/vocab#type*

#### Description

See [GeoJSON Section 2](geojson-spec.html#geojson-objects).


## Extension Types

### Instant

*http://www.w3.org/2006/time#Instant*

#### Description

A temporal entity with zero length, having only a "datetime" property.

### Interval

*http://www.w3.org/2006/time#Interval*

#### Description

A temporal entity with non-zero length. Closed intervals have "start" and "stop"
properties, while open ended intervals may have one or the other.


## Extension Properties

### datetime

*http://www.w3.org/2006/time#inXSDDateTime*

#### Description

TODO

### description

*http://purl.org/dc/terms/description*

#### Description

TODO

### earliest

*http://example.com/vocab#earliest*

#### Description

TODO

### latest

*http://example.com/vocab#latest*

#### Description

TODO

### start

*http://www.w3.org/2006/time#hasBeginning*

#### Description

TODO

### stop

*http://www.w3.org/2006/time#hasEnding*

#### Description

TODO

### title

*http://purl.org/dc/terms/title*

#### Description

TODO

### when

*http://example.com/vocab#when*

#### Description

The temporal extent of a Feature.

