---
title: SensorThings API Sensor (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 0.1
  - <a href='#'>SensorThings API Sensor</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: SensorThings API Sensor (Schema)
---


# SensorThings API Sensor `ogc.api.sta.Sensor`

A Sensor is an instrument that observes a property or phenomenon with the goal of producing an estimate of the value of the property.

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/ogcincubator/bblocks-sta/blob/master/build/tests/api/sta/Sensor/" target="_blank">valid</a></strong>
</aside>

# Description

## What is represents

A Sensor is an instrument that observes a property or phenomenon with the goal of producing an estimate of the value of the property.
STA sensor is based on the concept from [OGC and ISO 19156:2001, OGC 10-004r3 and ISO 19156:2011(E), OGC Abstract Specification: Geographic information — Observations and Measurements.](http://portal.opengeospatial.org/files/?artifact_id=41579)

### Limitations
For compliance with SwaggerHub where the schema can be referred:
- type of id is not specified, while it shall be string or number
- type of metadata property is not specified, while it shall be string or object

> Videri vias quid Ausoniae sua flores ante, reminiscitur fuit est. Semel
> [hectora](http://silvaque.org/) peregrinaeque rudem exercent in, Troiana si
> Asida instabilesque somno sed.

## References

Requirements: [http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel/sensor](https://docs.ogc.org/is/18-088/18-088.html#sensor)

# Examples

## Observation whose Datastream has an ObservationType of OM_Measurement. A result’s data type is defined by the observationType.



```json
{
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/Sensors(1)",
  "Datastreams@iot.navigationLink": "Sensors(1)/Datastreams",
  "name": "TMP36",
  "description": "TMP36 - Analog Temperature sensor",
  "encodingType": "application/pdf",
  "metadata": "http://example.org/TMP35_36_37.pdf"
}

```

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-sta/build/tests/api/sta/Sensor/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Ftests%2Fapi%2Fsta%2FSensor%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/Sensors(1)",
  "Datastreams@iot.navigationLink": "Sensors(1)/Datastreams",
  "name": "TMP36",
  "description": "TMP36 - Analog Temperature sensor",
  "encodingType": "application/pdf",
  "metadata": "http://example.org/TMP35_36_37.pdf",
  "@context": "https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-sta/build/tests/api/sta/Sensor/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Ftests%2Fapi%2Fsta%2FSensor%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix dcat1: <https://w3c.github.io/dxwg/dcat/> .
@prefix dcterms: <http://purl.org/dc/terms/> .

[] dcterms:description "TMP36 - Analog Temperature sensor" ;
    dcterms:title "TMP36" ;
    dcat1:mediaType "application/pdf" .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://ogcincubator.github.io/bblocks-sta/build/tests/api/sta/Sensor/example_1_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
$schema: http://json-schema.org/draft-04/schema#
title: Sensor object
description: Schema for Sensor things API 1.3 Observation
type: object
properties:
  '@iot.id':
    description: The Id of the sensor
  '@iot.selfLink':
    type: string
    description: The direct link to the entity
  properties:
    type: object
    description: A JSON Object containing user-annotated properties as key-value pairs.
  name:
    type: string
    description: A property provides a label for Sensor entity, commonly a descriptive
      name.
    x-jsonld-id: http://purl.org/dc/terms/title
  description:
    type: string
    description: The description of the Sensor entity.
    x-jsonld-id: http://purl.org/dc/terms/description
  encodingType:
    type: string
    description: The encoding type of the metadata property. Its value is one of the
      ValueCode enumeration (see Table 15 for the available ValueCode).
    x-jsonld-id: https://w3c.github.io/dxwg/dcat/mediaType
  metadata:
    description: The detailed description of the Sensor or system. The metadata type
      is defined by encodingType.
  Datastream@iot.navigationLink:
    type: string
    description: Reference link to the DataStream Definition.
x-jsonld-extra-terms:
  feature:
    x-jsonld-id: https://purl.org/geojson/vocab#Feature
    x-jsonld-context:
      type: '@type'
      coordinates:
        '@container': '@list'
        '@id': https://purl.org/geojson/vocab#coordinates
  LineString: https://purl.org/geojson/vocab#LineString
  MultiLineString: https://purl.org/geojson/vocab#MultiLineString
  MultiPoint: https://purl.org/geojson/vocab#MultiPoint
  MultiPolygon: https://purl.org/geojson/vocab#MultiPolygon
  Point: https://purl.org/geojson/vocab#Point
  Polygon: https://purl.org/geojson/vocab#Polygon
  geometry: https://purl.org/geojson/vocab#geometry
  Observations@iot.navigationLink: https://schemas.opengis.org/sta/def/core#Observation
x-jsonld-prefixes:
  orel: http://www.opengis.net/def/rel/
  dct: http://purl.org/dc/terms/
  dcat: https://w3c.github.io/dxwg/dcat/
  geojson: https://purl.org/geojson/vocab#
  sta: https://schemas.opengis.org/sta/def/core#
  sosa: https://www.w3.org/TR/vocab-ssn/#
  skos: http://www.w3.org/2004/02/skos/core#
  iana: https://www.iana.org/assignments/media-types/
  rel: http://www.iana.org/assignments/relation/

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Fannotated%2Fapi%2Fsta%2FSensor%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/schema.yaml" target="_blank">https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/schema.yaml</a>
* JSON version: <a href="https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/schema.json" target="_blank">https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "name": "dct:title",
    "description": "dct:description",
    "encodingType": "dcat:mediaType",
    "feature": {
      "@id": "geojson:Feature",
      "@context": {
        "type": "@type",
        "coordinates": {
          "@container": "@list",
          "@id": "geojson:coordinates"
        }
      }
    },
    "LineString": "geojson:LineString",
    "MultiLineString": "geojson:MultiLineString",
    "MultiPoint": "geojson:MultiPoint",
    "MultiPolygon": "geojson:MultiPolygon",
    "Point": "geojson:Point",
    "Polygon": "geojson:Polygon",
    "geometry": "geojson:geometry",
    "Observations@iot.navigationLink": "sta:Observation",
    "orel": "http://www.opengis.net/def/rel/",
    "dct": "http://purl.org/dc/terms/",
    "dcat": "https://w3c.github.io/dxwg/dcat/",
    "geojson": "https://purl.org/geojson/vocab#",
    "sta": "https://schemas.opengis.org/sta/def/core#",
    "sosa": "https://www.w3.org/TR/vocab-ssn/#",
    "skos": "http://www.w3.org/2004/02/skos/core#",
    "iana": "https://www.iana.org/assignments/media-types/",
    "rel": "http://www.iana.org/assignments/relation/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fogcincubator.github.io%2Fbblocks-sta%2Fbuild%2Fannotated%2Fapi%2Fsta%2FSensor%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/context.jsonld" target="_blank">https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/context.jsonld</a>

# References

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/ogcincubator/bblocks-sta" target="_blank">https://github.com/ogcincubator/bblocks-sta</a>
* Path:
<code><a href="https://github.com/ogcincubator/bblocks-sta/blob/HEAD/_sources/Sensor" target="_blank">_sources/Sensor</a></code>

