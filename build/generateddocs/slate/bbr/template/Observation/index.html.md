---
title: SensorThings API Observation (Schema)

language_tabs:
  - json: JSON
  - jsonld: JSON-LD
  - turtle: RDF/Turtle

toc_footers:
  - Version 0.1
  - <a href='#'>SensorThings API Observation</a>
  - <a href='https://blocks.ogc.org/register.html'>Building Blocks register</a>

search: true

code_clipboard: true

meta:
  - name: SensorThings API Observation (Schema)
---


# SensorThings API Observation `ogc.bbr.template.Observation`

Representation of the result of act of measuring or otherwise determining the value of a property. [OGC 10-004r3 / ISO 19156:2011]

<p class="status">
    <span data-rainbow-uri="http://www.opengis.net/def/status">Status</span>:
    <a href="http://www.opengis.net/def/status/under-development" target="_blank" data-rainbow-uri>Under development</a>
</p>

<aside class="success">
This building block is <strong><a href="https://github.com/pzaborowski/bblocks-sta/blob/master/build/tests/bbr/template/Observation/" target="_blank">valid</a></strong>
</aside>

# Description

## What is represents

Observation is an act of measuring or otherwise determining the value of a property. [OGC 10-004r3 / ISO 19156:2011]


> Videri vias quid Ausoniae sua flores ante, reminiscitur fuit est. Semel
> [hectora](http://silvaque.org/) peregrinaeque rudem exercent in, Troiana si
> Asida instabilesque somno sed.

## References

Requirements: [http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel/observation](https://docs.ogc.org/is/18-088/18-088.html#observation)

# Examples

## Observation whose Datastream has an ObservationType of OM_Measurement. A result’s data type is defined by the observationType.



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

<blockquote class="lang-specific json">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/tests/bbr/template/Observation/example_1_1.json">Open in new window</a>
    <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=json&amp;dataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fpzaborowski%2Fbblocks-sta%2Fmaster%2Fbuild%2Ftests%2Fbbr%2Ftemplate%2FObservation%2Fexample_1_1.json&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on JSON Viewer</a></p>
</blockquote>




```jsonld
{
  "@iot.id": 1,
  "@iot.selfLink": "http://example.org/v1.1/Observations(1)",
  "FeatureOfInterest@iot.navigationLink": "Observations(1)/FeatureOfInterest",
  "Datastream@iot.navigationLink": "Observations(1)/Datastream",
  "phenomenonTime": "2014-12-31T11:59:59.00+08:00",
  "resultTime": "2014-12-31T11:59:59.00+08:00",
  "result": 70.4,
  "@context": "https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/annotated/bbr/template/Observation/context.jsonld"
}
```

<blockquote class="lang-specific jsonld">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/tests/bbr/template/Observation/example_1_1.jsonld">Open in new window</a>
    <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fraw.githubusercontent.com%2Fpzaborowski%2Fbblocks-sta%2Fmaster%2Fbuild%2Ftests%2Fbbr%2Ftemplate%2FObservation%2Fexample_1_1.jsonld">View on JSON-LD Playground</a>
</blockquote>




```turtle
@prefix sosa1: <https://www.w3.org/TR/vocab-ssn/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

[] sosa1:hasSimpleResult 7.04e+01 ;
    sosa1:phenomenonTime "2014-12-31T11:59:59.00+08:00" ;
    sosa1:resultTime "2014-12-31T11:59:59.00+08:00" .


```

<blockquote class="lang-specific turtle">
  <p class="example-links">
    <a target="_blank" href="https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/tests/bbr/template/Observation/example_1_1.ttl">Open in new window</a>
</blockquote>



# JSON Schema

```yaml--schema
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
  '@iot.selfLink':
    type: string
    description: The direct link to the entity
  parameters:
    type: object
  phenomenonTime:
    type: string
    description: The time when the observation happened. or Time Interval string (e.g.,
      2010-12-23T10:20:00.00-07:00 or 2010-12-23T10:20:00.00-07:00/2010-12-23T12:20:00.00-07:00)
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/phenomenonTime
  result:
    type:
    - string
    - number
    - boolean
    description: The estimated value of the observed property. Type depends on the
      observationType defined in the associated Datastream
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/hasSimpleResult
  resultQuality:
    type: string
    description: A description of the quality of the result. Type DQ_Element.
    x-jsonld-id: https://schemas.opengis.org/sta/def/core#resultQuality
  resultTime:
    type: string
    description: The time the result was generated. TM_Instant (ISO 8601 Time string)
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/resultTime
  validTime:
    type: string
    description: The time period during which the result can be used. TM_Period (ISO
      8601 Time Interval string)
    x-jsonld-id: https://schemas.opengis.org/sta/def/core#validTime
  Datastream@iot.navigationLink:
    type: string
    description: Reference link to the DataStream Definition.
  FeatureOfInterest@iot.navigationLink:
    type: string
    description: Reference link to the FeatureOfInterest.
x-jsonld-extra-terms:
  Datastream: https://schemas.opengis.org/sta/def/core#DataStrem
  FeatureOfInterest: https://www.w3.org/TR/vocab-ssn/hasFeatureOfInterest
x-jsonld-prefixes:
  sta: https://schemas.opengis.org/sta/def/core#
  sosa: https://www.w3.org/TR/vocab-ssn/
  rel: http://www.iana.org/assignments/relation/

```

> <a target="_blank" href="https://avillar.github.io/TreedocViewer/?dataParser=yaml&amp;dataUrl=https%3A%2F%2Fraw.githubusercontent.com%2Fpzaborowski%2Fbblocks-sta%2Fmaster%2Fbuild%2Fannotated%2Fbbr%2Ftemplate%2FObservation%2Fschema.yaml&amp;expand=2&amp;option=%7B%22showTable%22%3A+false%7D">View on YAML Viewer</a>

Links to the schema:

* YAML version: <a href="https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/annotated/bbr/template/Observation/schema.yaml" target="_blank">https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/annotated/bbr/template/Observation/schema.yaml</a>
* JSON version: <a href="https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/annotated/bbr/template/Observation/schema.json" target="_blank">https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/annotated/bbr/template/Observation/schema.json</a>


# JSON-LD Context

```json--ldContext
{
  "@context": {
    "phenomenonTime": "sosa:phenomenonTime",
    "result": "sosa:hasSimpleResult",
    "resultQuality": "sta:resultQuality",
    "resultTime": "sosa:resultTime",
    "validTime": "sta:validTime",
    "Datastream": "sta:DataStrem",
    "FeatureOfInterest": "sosa:hasFeatureOfInterest",
    "sta": "https://schemas.opengis.org/sta/def/core#",
    "sosa": "https://www.w3.org/TR/vocab-ssn/",
    "rel": "http://www.iana.org/assignments/relation/",
    "@version": 1.1
  }
}
```

> <a target="_blank" href="https://json-ld.org/playground/#json-ld=https%3A%2F%2Fraw.githubusercontent.com%2Fpzaborowski%2Fbblocks-sta%2Fmaster%2Fbuild%2Fannotated%2Fbbr%2Ftemplate%2FObservation%2Fcontext.jsonld">View on JSON-LD Playground</a>

You can find the full JSON-LD context here:
<a href="https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/annotated/bbr/template/Observation/context.jsonld" target="_blank">https://raw.githubusercontent.com/pzaborowski/bblocks-sta/master/build/annotated/bbr/template/Observation/context.jsonld</a>

# References

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: <a href="https://github.com/pzaborowski/bblocks-sta" target="_blank">https://github.com/pzaborowski/bblocks-sta</a>
* Path:
<code><a href="https://github.com/pzaborowski/bblocks-sta/blob/HEAD/_sources/Observation" target="_blank">_sources/Observation</a></code>

