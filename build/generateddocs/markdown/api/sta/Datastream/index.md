
# SensorThings API Datastream (Schema)

`ogc.api.sta.Datastream` *v0.1*

Metadata about a coherent set of observations, linked to value stream. [OGC 10-004r3 / ISO 19156:2011]

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## What is represents

A Datastream groups a collection of Observations measuring the same ObservedProperty and produced by the same Sensor. [https://docs.ogc.org/is/18-088/18-088.html#datastream].

### Limitations

Observations navigation link is to an array of observation properties. This requires an extra schema element to navigate the relationship between OMS/SOSA ObservationCollection and the set of observations as direct members. 

## References

Requirements: [http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel#datastream](https://docs.ogc.org/is/18-088/18-088.html#datastream)

## Examples

### Observation whose Datastream has an ObservationType of OM_Measurement. A result’s data type is defined by the observationType.
#### json
```json
    {
      "unitOfMeasurement": {
        "name": "Unitless",
        "definition": "http://qudt.org/schema/qudt/UNITLESS"
      },
      "description": "The datastream of jf2024 by sensor: 2e92962c0b6996add9517e4242ea9bdc for observed property: Jelly Fish Abundance Property",
      "name": "2e92962c0b6996add9517e4242ea9bdc:d2511e0ff7ac61981c6051a52b51f05c",
      "observationType": "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",
      "@iot.id": "2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c",
      "@iot.selfLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)",
      "Observations@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Observations",
      "ObservedProperty@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/ObservedProperty",
      "Sensor@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Sensor",
      "Thing@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Thing"
    }

```

#### jsonld
```jsonld
{
  "unitOfMeasurement": {
    "name": "Unitless",
    "definition": "http://qudt.org/schema/qudt/UNITLESS"
  },
  "description": "The datastream of jf2024 by sensor: 2e92962c0b6996add9517e4242ea9bdc for observed property: Jelly Fish Abundance Property",
  "name": "2e92962c0b6996add9517e4242ea9bdc:d2511e0ff7ac61981c6051a52b51f05c",
  "observationType": "http://www.opengis.net/def/observationType/OGC-OM/2.0/OM_Measurement",
  "@iot.id": "2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c",
  "@iot.selfLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)",
  "Observations@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Observations",
  "ObservedProperty@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/ObservedProperty",
  "Sensor@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Sensor",
  "Thing@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Thing",
  "@context": "https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream/context.jsonld"
}
```

#### ttl
```ttl
@prefix ns1: <https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/> .
@prefix ns2: <dct:> .
@prefix sosa1: <https://www.w3.org/TR/vocab-ssn/#> .

<http://w3id.org/ogcincubator/bblocks-sta/2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c> ns2:description "The datastream of jf2024 by sensor: 2e92962c0b6996add9517e4242ea9bdc for observed property: Jelly Fish Abundance Property" ;
    ns2:title "2e92962c0b6996add9517e4242ea9bdc:d2511e0ff7ac61981c6051a52b51f05c" ;
    ns1:ObservedProperty "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/ObservedProperty" ;
    ns1:Sensor "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Sensor" ;
    ns1:Thing "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Thing" ;
    sosa1:hasMember "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Observations" .


```

## Schema

```yaml
$schema: http://json-schema.org/draft-04/schema#
title: Datastream object
description: Schema for Sensor things API 1.3 Datastream
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
  Observations@iot.navigationLink:
    type: string
    description: Reference link to stream of Observations.
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#hasMember
x-jsonld-extra-terms:
  phenomenonTime: https://www.w3.org/TR/vocab-ssn/#phenomenonTime
  name: dct:title
  description: dct:description
  resultQuality: https://www.w3.org/TR/vocab-ssn/#resultQuality
  resultTime: https://www.w3.org/TR/vocab-ssn/#resultTime
  validTime: https://schemas.opengis.org/sta/def/core#validTime
  ObservedProperty@iot.navigationLink: https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/ObservedProperty
  Sensor@iot.navigationLink: https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Sensor
  Thing@iot.navigationLink: https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Thing
x-jsonld-prefixes:
  orel: http://www.opengis.net/def/rel/
  sosa: https://www.w3.org/TR/vocab-ssn/#
  sta: https://schemas.opengis.org/sta/def/core#
  rel: http://www.iana.org/assignments/relation/

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@iot.id": "@id",
    "@iot.selfLink": "orel:iana/1.0/self",
    "Observations@iot.navigationLink": "sosa:hasMember",
    "phenomenonTime": "sosa:phenomenonTime",
    "name": "dct:title",
    "description": "dct:description",
    "resultQuality": "sosa:resultQuality",
    "resultTime": "sosa:resultTime",
    "validTime": "sta:validTime",
    "ObservedProperty@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/ObservedProperty",
    "Sensor@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Sensor",
    "Thing@iot.navigationLink": "https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Thing",
    "orel": "http://www.opengis.net/def/rel/",
    "sosa": "https://www.w3.org/TR/vocab-ssn/#",
    "sta": "https://schemas.opengis.org/sta/def/core#",
    "rel": "http://www.iana.org/assignments/relation/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream/context.jsonld)

## Sources

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html#datastream)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-sta](https://github.com/ogcincubator/bblocks-sta)
* Path: `_sources/Datastream`

