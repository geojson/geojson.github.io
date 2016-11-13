---
layout: home
title: GeoJSON-LD
---

# GeoJSON-LD 1.0

A vocabulary and JSON-LD context for GeoJSON

GeoJSON-LD 1.0 defines a base context for processing GeoJSON according
to the [JSON-LD](https://www.w3.org/TR/json-ld/) processing model. When
a JSON-LD processor encounters a GeoJSON document with the
`application/geo+json` media type that does not contain a `@context` member, it
may use the context defined here. JSON-LD implementations may add to the
context defined here but MUST NOT override or change the meaning of its terms.

The vocabulary is published at [http://geojson.org/vocab#](http://geojson.org/vocab#) and the context is
published at [http://geojson.org/geojson-context.jsonld](http://geojson.org/geojson-context.jsonld).

## Example

Pasting the following GeoJSON-LD document

```json
{
  "@context": {
    "geojson": "http://geojson.org/vocab#",
    "Feature": "geojson:Feature",
    "FeatureCollection": "geojson:FeatureCollection",
    "GeometryCollection": "geojson:GeometryCollection",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "bbox": {
      "@container": "@list",
      "@id": "geojson:bbox"
    },
    "coordinates": "geojson:coordinates",
    "description": "http://purl.org/dc/terms/description",
    "features": {
      "@container": "@set",
      "@id": "geojson:features"
    },
    "geometry": "geojson:geometry",
    "id": "@id",
    "properties": "geojson:properties",
    "type": "@type",
    "description": "http://purl.org/dc/terms/description",
    "title": "http://purl.org/dc/terms/title"
  },
  "type": "Feature",
  "id": "http://example.com/features/1",
  "geometry": {"type": "Point", "coordinates": [0.0, 0.0]},
  "properties": {
    "title": "Null Island",
    "description": "A fictional island in the Gulf of Guinea"
  }
}
```

into the [JSON-LD Playground](http://json-ld.org/playground/) form yields
the following compacted JSON-LD.

```json
{
  "@id": "http://example.com/features/1",
  "@type": "http://geojson.org/vocab#Feature",
  "http://geojson.org/vocab#geometry": {
    "@type": "http://geojson.org/vocab#Point",
    "http://geojson.org/vocab#coordinates": [
      0,
      0
    ]
  },
  "http://geojson.org/vocab#properties": {
    "http://purl.org/dc/terms/description": "A fictional island in the Gulf of Guinea",
    "http://purl.org/dc/terms/title": "Null Island"
  }
}
```

## See Also

Activity Streams 2.0: https://www.w3.org/TR/activitystreams-core/, from which
GeoJSON-LD gets the idea of a normative, default context.
