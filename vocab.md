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


## Extension Properties

### <a name="description">description</a>

*http://purl.org/dc/terms/description*

Description: Summary text or content. [**Feature**](#Feature) descriptions are
useful in popups.

### <a name="title">title</a>

*http://purl.org/dc/terms/title*

Description: [**Feature**](#Feature) titles are useful in popups.

