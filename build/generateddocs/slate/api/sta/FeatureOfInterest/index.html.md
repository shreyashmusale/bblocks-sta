---
title: SensorThings API FeatureOfInterest (FOI) (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 0.1
  - <a href='#'>SensorThings API FeatureOfInterest (FOI)</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: SensorThings API FeatureOfInterest (FOI) (Schema)
---


# SensorThings API FeatureOfInterest (FOI) `ogc.api.sta.FeatureOfInterest`

Representation of the result of the FeatureOfInterest. 

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/bblocks-sta/blob/master/build/tests/api/sta/FeatureOfInterest/" target="_blank">valid</a></strong>
</aside>

# Description

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

# Examples

## FeatureOfInterest basic example.



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

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-sta/build/tests/api/sta/FeatureOfInterest/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Ftests%2Fapi%2Fsta%2FFeatureOfInterest%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




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

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-sta/build/tests/api/sta/FeatureOfInterest/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Ftests%2Fapi%2Fsta%2FFeatureOfInterest%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
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

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-sta/build/tests/api/sta/FeatureOfInterest/example_1_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
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

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Fannotated%2Fapi%2Fsta%2FFeatureOfInterest%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/schema.yaml" target="_blank">https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/schema.json" target="_blank">https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/schema.json</a>


# JSON-LD Context

```json--ldContext
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

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Fannotated%2Fapi%2Fsta%2FFeatureOfInterest%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/context.jsonld" target="_blank">https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/FeatureOfInterest/context.jsonld</a>

# References

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/bblocks-sta" target="_blank">https://github.com/ogcincubator/bblocks-sta</a>
* Path:
<code><a href="https://github.com/ogcincubator/bblocks-sta/blob/HEAD/_sources/FeatureOfInterest" target="_blank">_sources/FeatureOfInterest</a></code>

