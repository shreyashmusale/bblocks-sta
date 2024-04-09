
# SensorThings API FeatureOfInterest (FOI) (Schema)

`ogc.api.sta.FeatureOfInterest` *v0.1*

Representation of the result of the FeatureOfInterest. 

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## What it represents

An Observation results in a value being assigned to a phenomenon. The phenomenon is a property of a feature, the latter being the FeatureOfInterest of the Observation [OGC and ISO 19156:2011]. In the context of the Internet of Things, many Observations’ FeatureOfInterest can be the Location of the Thing. For example, the FeatureOfInterest of a wifi-connect thermostat can be the Location of the thermostat (i.e., the living room where the thermostat is located in). In the case of remote sensing, the FeatureOfInterest can be the geographical area or volume that is being sensed.

### Limitations
For compliance with SwaggerHub where the schema can be referred:
- type of id is not specified, while it shall be string or number
- type of feature property is not specified, while it shall be string or object

> Videri vias quid Ausoniae sua flores ante, reminiscitur fuit est. Semel
> [hectora](http://silvaque.org/) peregrinaeque rudem exercent in, Troiana si
> Asida instabilesque somno sed.

## References

Requirements: [http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel/feature-of-interest](https://docs.ogc.org/is/18-088/18-088.html#featureofinterest)

## Examples

### FeatureOfInterest basic example.
#### json
```json
{
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/FeaturesOfInterest(1)",
  "Observations@iot.navigationLink": "FeaturesOfInterest(1)/Observations",

  "name": "Weather Station YYC.",
  "description": "This is a weather station located at the Calgary Airport.",
  "encodingType": "application/geo+json",
  "feature": {
    "type": "Feature",
    "geometry":{
      "type": "Point",
      "coordinates": [-114.06,51.05]
    }
  }
}

```

#### jsonld
```jsonld
{
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/FeaturesOfInterest(1)",
  "Observations@iot.navigationLink": "FeaturesOfInterest(1)/Observations",
  "name": "Weather Station YYC.",
  "description": "This is a weather station located at the Calgary Airport.",
  "encodingType": "application/geo+json",
  "feature": {
    "type": "Feature",
    "geometry": {
      "type": "Point",
      "coordinates": [
        -114.06,
        51.05
      ]
    }
  },
  "@context": "https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/context.jsonld"
}
```

#### ttl
```ttl
@prefix dcat1: <https://w3c.github.io/dxwg/dcat/> .
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix geojson: <https://purl.org/geojson/vocab#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix sta: <https://schemas.opengis.org/sta/def/core#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] dcterms:description "This is a weather station located at the Calgary Airport." ;
    dcterms:title "Weather Station YYC." ;
    geojson:Feature [ a <http://w3id.org/ogcincubator/bblocks-sta/Feature> ;
            geojson:geometry [ a geojson:Point ;
                    geojson:coordinates ( -1.1406e+02 5.105e+01 ) ] ] ;
    sta:Observation "FeaturesOfInterest(1)/Observations" ;
    dcat1:mediaType "application/geo+json" .


```

## Schema

```yaml
$schema: http://json-schema.org/draft-04/schema#
title: FeatureOfInterest object
description: Schema for Sensor things API 1.1 FeatureOfInterest
type: object
required:
- '@iot.id'
- '@iot.selfLink'
- name
- description
- encodingType
- feature
- Observations@iot.navigationLink
properties:
  '@iot.id':
    description: The Id of the Feature
    x-jsonld-id: '@id'
  '@iot.selfLink':
    type: string
    description: The direct link to the entity
    x-jsonld-id: https://schemas.opengis.org/sta/def/core#selfLink
  name:
    type: string
    description: A property provides a label for FeatureOfInterest entity, commonly
      a descriptive name.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: The description about the FeatureOfInterest.
    x-jsonld-id: http://purl.org/dc/terms/description
  encodingType:
    type: string
    description: The encoding type of the feature property. Its value is one of the
      ValueCode enumeration (see https://docs.ogc.org/is/18-088/18-088.html#tab-encodingtype-codes
      for the available ValueCode)..
    const: application/geo+json
    x-jsonld-id: https://w3c.github.io/dxwg/dcat/mediaType
  feature:
    description: The detailed description of the feature. The data type is defined
      by encodingType.
    x-jsonld-id: https://purl.org/geojson/vocab#Feature
    x-jsonld-extra-terms:
      type: '@type'
      coordinates:
        x-jsonld-container: '@list'
        x-jsonld-id: https://purl.org/geojson/vocab#coordinates
  properties:
    type: object
    description: optional properties for the feature.
  Observations@iot.navigationLink:
    type: string
    description: Reference link to the Observations.
    x-jsonld-id: https://schemas.opengis.org/sta/def/core#Observation
x-jsonld-extra-terms:
  LineString: https://purl.org/geojson/vocab#LineString
  MultiLineString: https://purl.org/geojson/vocab#MultiLineString
  MultiPoint: https://purl.org/geojson/vocab#MultiPoint
  MultiPolygon: https://purl.org/geojson/vocab#MultiPolygon
  Point: https://purl.org/geojson/vocab#Point
  Polygon: https://purl.org/geojson/vocab#Polygon
  geometry: https://purl.org/geojson/vocab#geometry
x-jsonld-prefixes:
  sta: https://schemas.opengis.org/sta/def/core#
  dct: http://purl.org/dc/terms/
  dcat: https://w3c.github.io/dxwg/dcat/
  geojson: https://purl.org/geojson/vocab#
  sosa: https://www.w3.org/TR/vocab-ssn/#
  skos: http://www.w3.org/2004/02/skos/core#
  iana: https://www.iana.org/assignments/media-types/
  rel: http://www.iana.org/assignments/relation/

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@iot.id": "@id",
    "@iot.selfLink": "sta:selfLink",
    "name": "dct:title",
    "description": "dct:description",
    "encodingType": "dcat:mediaType",
    "feature": {
      "@context": {
        "type": "@type",
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      },
      "@id": "geojson:Feature"
    },
    "Observations@iot.navigationLink": "sta:Observation",
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "geometry": "geojson:geometry",
    "sta": "https://schemas.opengis.org/sta/def/core#",
    "dct": "http://purl.org/dc/terms/",
    "dcat": "https://w3c.github.io/dxwg/dcat/",
    "geojson": "https://purl.org/geojson/vocab#",
    "sosa": "https://www.w3.org/TR/vocab-ssn/#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "iana": "https://www.iana.org/assignments/media-types/",
    "rel": "http://www.iana.org/assignments/relation/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/context.jsonld)

## Sources

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-sta](https://github.com/ogcincubator/bblocks-sta)
* Path: `_sources/FeatureOfInterest`

