
# STA Datastream as ObsCollection (Schema)

`ogc.api.sta.Datastream-Collection` *v0.1*

Metadata about a coherent set of observations - linked to a stream of observations. [OGC 10-004r3 / ISO 19156:2011]

[*Status*](http://www.opengis.net/def/status): Under development

## Description

## What it represents

Forces the datastream to be an upper-level ObservationCollection setting common values, and the values stream to be regarded as a link to an ObservationCollection

### Limitations

TBD

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
  "@context": "https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream-Collection/context.jsonld",
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

#### ttl
```ttl
@prefix dcterms: <http://purl.org/dc/terms/> .
@prefix ns1: <https://www.w3.org/TR/vocab-ssn/#> .
@prefix sosa: <http://www.w3.org/ns/sosa/> .

<http://w3id.org/ogcincubator/bblocks-sta/2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c> dcterms:description "The datastream of jf2024 by sensor: 2e92962c0b6996add9517e4242ea9bdc for observed property: Jelly Fish Abundance Property" ;
    dcterms:title "2e92962c0b6996add9517e4242ea9bdc:d2511e0ff7ac61981c6051a52b51f05c" ;
    sosa:featureOfInterest <https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Thing> ;
    sosa:madeBySensor <https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Sensor> ;
    sosa:observedProperty <https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/ObservedProperty> ;
    ns1:hasMember <https://sensor-things-api-sensor-things-api.apps.dcw1.paas.psnc.pl/jf2024/api/v1.0/Datastreams(2e92962c0b6996add9517e4242ea9bdcd2511e0ff7ac61981c6051a52b51f05c)/Observations> .


```

## Schema

```yaml
$schema: http://json-schema.org/draft-04/schema#
allOf:
- $ref: https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream/schema.yaml
x-jsonld-extra-terms:
  Observations@iot.navigationLink:
    x-jsonld-id: https://www.w3.org/TR/vocab-ssn/#hasMember
    x-jsonld-type: '@id'
x-jsonld-prefixes:
  sosa: https://www.w3.org/TR/vocab-ssn/#

```

Links to the schema:

* YAML version: [schema.yaml](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream-Collection/schema.json)
* JSON version: [schema.json](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream-Collection/schema.yaml)


# JSON-LD Context

```jsonld
{
  "@context": {
    "@iot.id": "@id",
    "@iot.selfLink": "orel:iana/1.0/self",
    "phenomenonTime": "sosa:phenomenonTime",
    "name": "dct:title",
    "description": "dct:description",
    "resultQuality": "sosa:resultQuality",
    "resultTime": "sosa:resultTime",
    "validTime": "sosa:validTime",
    "ObservedProperty@iot.navigationLink": {
      "@id": "sosa:observedProperty",
      "@type": "@id"
    },
    "Sensor@iot.navigationLink": {
      "@id": "sosa:madeBySensor",
      "@type": "@id"
    },
    "Thing@iot.navigationLink": {
      "@id": "sosa:featureOfInterest",
      "@type": "@id"
    },
    "Observations@iot.navigationLink": {
      "@id": "https://www.w3.org/TR/vocab-ssn/#hasMember",
      "@type": "@id"
    },
    "orel": "http://www.opengis.net/def/rel/",
    "sosa": "http://www.w3.org/ns/sosa/",
    "dct": "http://purl.org/dc/terms/",
    "sta": "https://schemas.opengis.org/sta/def/core#",
    "rel": "http://www.iana.org/assignments/relation/",
    "@version": 1.1
  }
}
```

You can find the full JSON-LD context here:
[context.jsonld](https://ogcincubator.github.io/bblocks-sta/build/annotated/api/sta/Datastream-Collection/context.jsonld)

## Sources

* [OGC SensorThings API Part 1: Sensing Version 1.1](https://docs.ogc.org/is/18-088/18-088.html#datastream)

# For developers

The source code for this Building Block can be found in the following repository:

* URL: [https://github.com/ogcincubator/bblocks-sta](https://github.com/ogcincubator/bblocks-sta)
* Path: `_sources/Datastream-Collection`

