# OGC Sensor Things API 1.1 Building Blocks

The OGC SensorThings API (STA) provides an open, geospatial-enabled and unified way to interconnect the Internet of Things devices, data, and applications over the web. The OGC SensorThings API is an open Standard, and that means it is non-proprietary, platform-independent, and perpetually royalty-free. Although it is a new Standard, it builds on a rich set of proven-working and widely-adopted open standards, such as the web protocols and the OGC Sensor Web Enablement (SWE) Standards, including the OGC/ISO Observation and Measurement data model [OGC 10-004r3 and ISO 19156:2011]. That also means the OGC SensorThings API is extensible and can be applied to not only simple but also complex use cases.

These [Building Blocks](https://ogcincubator.github.io/bblocks-docs/) document the underlying components of the STA standard and provide examples and mappings to related standards.

# How to use these Building Blocks

This collection allows you to develop and validate STA compliant services, and to augment STA compliant response payloads with semantic annotations.

These can be used either directly, or as the foundations for more specialised Building Blocks for implementation profiles of STA - or any specific component.

The compiled (ready to use) elements and documentation are available here: (https://ogcincubator.github.io/bblocks-sta/)

For example an _Observation_ like this:
```
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

can have additional properties defined for a specific use.  A Building Block for that use case simply declares a dependency, or makes a schemas reference to a component, and inherits from this.

For more information see the [Building Blocks documentation](https://ogcincubator.github.io/bblocks-docs/).

## General Building block repository structure


The `build/` directory contains the **_reusable assets_** for implementing this building block, in full or part, and the rest of the repository contain *sources* to build these assets.  *Sources* minimise redundant information and preserve original forms of inputs, such as externally published schemas etc.  This allows these to be updated safely, and also allows for alternative forms of original source material to be used whilst preserving uniformity of the reusable assets.

Note that the these components will be consistently structured for a given type of building block, and the editable components may vary according to the source material used to derive the building block, and therefore cannot be directly referenced.

## Acknowledgements

The work has been co-funded by the European Union, Switzerland and the United Kingdom under the Horizon Europe:
* [Iliad project](https://www.ogc.org/initiatives/iliad/) (GA 101037643)
* [AD4GD project](https://www.ogc.org/initiatives/ad4gd/)(GA 101061001)

