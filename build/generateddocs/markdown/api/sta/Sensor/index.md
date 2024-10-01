
# SensorThings API Sensor (Schema)

`ogc.api.sta.Sensor` *v0.1*

A Sensor is an instrument that observes a property or phenomenon with the goal of producing an estimate of the value of the property.

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## Sensor

A Sensor is an instrument that observes a property or phenomenon with the goal of producing an estimate of the value of the property.
STA sensor is based on the concept from [OGC and ISO 19156:2001, OGC 10-004r3 and ISO 19156:2011(E), OGC Abstract Specification: Geographic information — Observations and Measurements.](http://portal.opengeospatial.org/files/?artifact_id=41579)

### Limitations
For compliance with SwaggerHub where the schema can be referred:
- type of id is not specified, while it shall be string or number
- type of metadata property is not specified, while it shall be string or object


## References

Requirements: [http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel/sensor](https://docs.ogc.org/is/18-088/18-088.html#sensor)

## Examples

### Observation whose Datastream has an ObservationType of OM_Measurement. A result’s data type is defined by the observationType.
#### json
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

#### jsonld
```jsonld
{
  "@context": "https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/context.jsonld",
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/Sensors(1)",
  "Datastreams@iot.navigationLink": "Sensors(1)/Datastreams",
  "name": "TMP36",
  "description": "TMP36 - Analog Temperature sensor",
  "encodingType": "application/pdf",
  "metadata": "http://example.org/TMP35_36_37.pdf"
}
```

#### ttl
```ttl
@prefix dcat1: <https://w3c.github.io/dxwg/dcat/> .
@prefix dcterms: <http://purl.org/dc/terms/> .

<http://w3id.org/ogcincubator/bblocks-sta/1> dcterms:description "TMP36 - Analog Temperature sensor" ;
    dcterms:title "TMP36" ;
    dcat1:mediaType "application/pdf" .


```

## Schema

```yaml
$schema: http://json-schema.org/draft-04/schema#
title: Sensor object
description: Schema for Sensor things API 1.3 Observation
type: object
properties:
  '@iot.id':
    description: The Id of the sensor
    x-jsonld-id: '@id'
  '@iot.selfLink':
    type: string
    description: The direct link to the entity
    x-jsonld-id: http://www.opengis.net/def/rel/iana/1.0/self
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
  Observations@iot.navigationLink: https://www.w3.org/TR/vocab-ssn/#madeObservation
x-jsonld-prefixes:
  orel: http://www.opengis.net/def/rel/
  dct: http://purl.org/dc/terms/
  dcat: https://w3c.github.io/dxwg/dcat/
  sosa: https://www.w3.org/TR/vocab-ssn/#
  sta: https://schemas.opengis.org/sta/def/core#
  iana: https://www.iana.org/assignments/media-types/
  rel: http://www.iana.org/assignments/relation/
  geojson: https://purl.org/geojson/vocab#

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@iot.id": "@id",
    "@iot.selfLink": "orel:iana/1.0/self",
    "name": "dct:title",
    "description": "dct:description",
    "encodingType": "dcat:mediaType",
    "Observations@iot.navigationLink": "sosa:madeObservation",
    "orel": "http://www.opengis.net/def/rel/",
    "dct": "http://purl.org/dc/terms/",
    "dcat": "https://w3c.github.io/dxwg/dcat/",
    "sosa": "https://www.w3.org/TR/vocab-ssn/#",
    "sta": "https://schemas.opengis.org/sta/def/core#",
    "iana": "https://www.iana.org/assignments/media-types/",
    "rel": "http://www.iana.org/assignments/relation/",
    "geojson": "https://purl.org/geojson/vocab#",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Sensor/context.jsonld)

## Sources

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html#sensor)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-sta](https://github.com/ogcincubator/bblocks-sta)
* Path: `_sources/Sensor`

