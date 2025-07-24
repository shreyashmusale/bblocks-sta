
# STA Observation (Schema)

`ogc.api.sta.Observation` *v0.1*

Representation of the result of act of measuring or otherwise determining the value of a property. [OGC 10-004r3 / ISO 19156:2011]

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## What is represents

Observation is an act of measuring or otherwise determining the value of a property. [OGC 10-004r3 / ISO 19156:2011].

### Limitations
For compliance with SwaggerHub where the schema can be referred:
- type of id is not specified, while it shall be string or number


## References

Requirements: [http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel/observation](https://docs.ogc.org/is/18-088/18-088.html#observation)

## Examples

### Observation whose Datastream has an ObservationType of OM_Measurement. A result’s data type is defined by the observationType.
#### json
```json
{
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/Observations(1)",
  "FeatureOfInterest@iot.navigationLink": "Observations(1)/FeatureOfInterest",
  "Datastream@iot.navigationLink":"Observations(1)/Datastream",
  "phenomenonTime": "2014-12-31T11:59:59.00+08:00",
  "resultTime": "2014-12-31T11:59:59.00+08:00",
  "result": 70.4
}

```

#### jsonld
```jsonld
{
  "@context": "https://shreyashmusale.github.io/bblocks-sta/build/annotated/api/sta/Observation/context.jsonld",
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/Observations(1)",
  "FeatureOfInterest@iot.navigationLink": "Observations(1)/FeatureOfInterest",
  "Datastream@iot.navigationLink": "Observations(1)/Datastream",
  "phenomenonTime": "2014-12-31T11:59:59.00+08:00",
  "resultTime": "2014-12-31T11:59:59.00+08:00",
  "result": 70.4
}
```

#### ttl
```ttl
@prefix sosa1: <https://www.w3.org/TR/vocab-ssn/#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://w3id.org/ogcincubator/bblocks-sta/1> sosa1:hasFeatureOfInterest "Observations(1)/FeatureOfInterest" ;
    sosa1:hasSimpleResult 7.04e+01 ;
    sosa1:isMemberOf "Observations(1)/Datastream" ;
    sosa1:phenomenonTime "2014-12-31T11:59:59.00+08:00" ;
    sosa1:resultTime "2014-12-31T11:59:59.00+08:00" .


```

## Schema

```yaml
$schema: http://json-schema.org/draft-04/schema#
title: Observation object
description: Schema for Sensor things API 1.3 Observation
type: object
properties:
  '@iot.id':
    type:
    - string
    - number
    description: The Id of the observation
    x-jsonld-id: '@id'
  '@iot.selfLink':
    type: string
    description: The direct link to the entity
    x-jsonld-id: http://www.opengis.net/def/rel/iana/1.0/self
  parameters:
    type: object
  phenomenonTime:
    type: string
    description: The time when the observation happened. or Time Interval string (e.g.,
      2010-12-23T10:20:00.00-07:00 or 2010-12-23T10:20:00.00-07:00/2010-12-23T12:20:00.00-07:00)
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#phenomenonTime
  result:
    description: The estimated value of the observed property. Type depends on the
      observationType defined in the associated Datastream
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#hasSimpleResult
  resultQuality:
    type: string
    description: A description of the quality of the result. Type DQ_Element.
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#resultQuality
  resultTime:
    type: string
    description: The time the result was generated. TM_Instant (ISO 8601 Time string)
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#resultTime
  validTime:
    type: string
    description: The time period during which the result can be used. TM_Period (ISO
      8601 Time Interval string)
    x-jsonld-id: https://schemas.opengis.org/sta/def/core#validTime
  Datastream@iot.navigationLink:
    type: string
    description: Reference link to the DataStream Definition.
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#isMemberOf
  FeatureOfInterest@iot.navigationLink:
    type: string
    description: Reference link to the FeatureOfInterest.
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#hasFeatureOfInterest
x-jsonld-prefixes:
  orel: http://www.opengis.net/def/rel/
  sosa: https://www.w3.org/TR/vocab-ssn/#
  sta: https://schemas.opengis.org/sta/def/core#
  rel: http://www.iana.org/assignments/relation/

```

Links to the schema:

* YAML version: [schema.yaml](https://shreyashmusale.github.io/bblocks-sta/build/annotated/api/sta/Observation/schema.json)
* JSON version: [schema.json](https://shreyashmusale.github.io/bblocks-sta/build/annotated/api/sta/Observation/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@iot.id": "@id",
    "@iot.selfLink": "orel:iana/1.0/self",
    "phenomenonTime": "sosa:phenomenonTime",
    "result": "sosa:hasSimpleResult",
    "resultQuality": "sosa:resultQuality",
    "resultTime": "sosa:resultTime",
    "validTime": "sta:validTime",
    "Datastream@iot.navigationLink": "sosa:isMemberOf",
    "FeatureOfInterest@iot.navigationLink": "sosa:hasFeatureOfInterest",
    "orel": "http://www.opengis.net/def/rel/",
    "sosa": "https://www.w3.org/TR/vocab-ssn/#",
    "sta": "https://schemas.opengis.org/sta/def/core#",
    "rel": "http://www.iana.org/assignments/relation/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://shreyashmusale.github.io/bblocks-sta/build/annotated/api/sta/Observation/context.jsonld)

## Sources

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html#observation)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/shreyashmusale/bblocks-sta](https://github.com/shreyashmusale/bblocks-sta)
* Path: `_sources/Observation`

