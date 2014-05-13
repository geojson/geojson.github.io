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
dissuade you from publishing GeoJSON-LD until we publish a final vocabulary.

## Types

Below are linked data identifiers for the GeoJSON types.

### FeatureCollection

*http://example.com/vocab#FeatureCollection*

To explain to JSON-LD readers that a node is a GeoJSON FeatureCollection, assign
this URI to the node's [``@type`` item](http://www.w3.org/TR/json-ld/#specifying-the-type).

```
{ "type": "FeatureCollection",
  "@type": "http://example.com/vocab#FeatureCollection",
  "features": [ ... ] }
```

### Feature

*http://example.com/vocab#Feature*

### Point

*http://example.com/vocab#Point*

### LineString

*http://example.com/vocab#LineString*

### Polygon

*http://example.com/vocab#Polygon*

### MultiPoint

*http://example.com/vocab#MultiPoint*

### MultiLineString

*http://example.com/vocab#MultiLineString*

### MultiPolygon

*http://example.com/vocab#MultiPolygon*

### GeometryCollection

*http://example.com/vocab#GeometryCollection*

## Properties

Below are linked data identifiers for the properties of GeoJSON types.

### bbox

*http://example.com/vocab#bbox*

### coordinates

*http://example.com/vocab#coordinates*

### datetime

*http://www.w3.org/2006/time#inXSDDateTime*

### description

*http://purl.org/dc/terms/description*

### earliest

*http://example.com/vocab#earliest*

### features

*http://example.com/vocab#features*

### geometry

*http://example.com/vocab#geometry*

### id

*http://example.com/vocab#id*

### latest

*http://example.com/vocab#latest*

### properties

*http://example.com/vocab#properties*

### start

*http://www.w3.org/2006/time#hasBeginning*

### stop

*http://www.w3.org/2006/time#hasEnding*

### title

*http://purl.org/dc/terms/title*

### type

*http://example.com/vocab#type*

### when

*http://example.com/vocab#when*
