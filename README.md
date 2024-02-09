# OGC Sensor Things API 1.1 Building Blocks

The OGC SensorThings API (STA) provides an open, geospatial-enabled and unified way to interconnect the Internet of Things devices, data, and applications over the web. The OGC SensorThings API is an open Standard, and that means it is non-proprietary, platform-independent, and perpetually royalty-free. Although it is a new Standard, it builds on a rich set of proven-working and widely-adopted open standards, such as the web protocols and the OGC Sensor Web Enablement (SWE) Standards, including the OGC/ISO Observation and Measurement data model [OGC 10-004r3 and ISO 19156:2011]. That also means the OGC SensorThings API is extensible and can be applied to not only simple but also complex use cases.

# How to use this collection

This collection allow to develop and validate STA compliant services payload with semantic annotations.
It can be used either directly or as the reference to specialised Building Blocks.
The compiled (ready to use) elements and documentation are available here: (https://ogcincubator.github.io/bblocks-sta/)

For example observation like this:
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

Can have additional properties defined for the specific use. Then building block for that use case shall be defined inheriting from this in separate fork of the [Template](https://github.com/opengeospatial/bblock-template/blob/master/USAGE.md).

## General Building block repository structure


The `build/` directory contains the **_reusable assets_** for implementing this building block, in full or part, and the rest of the repository contain *sources* to build these assets.  *Sources* minimise redundant information and preserve original forms of inputs, such as externally published schemas etc.  This allow these to be updated safely, and also allows for alternative forms of original source material to be used whilst preserving uniformity of the reusable assets.

Note that the these components will be consistently structured for a given type of building block, and the editable components may vary according to the source material used to derive the building block, and therefore cannot be directly referenced.

### Editable components

- `features/`: schemas for the feature types defined by this bb (which is a "super-bb" containing at least oneOf these defined features)
- `datatypes/`: reusable schemas for (potentially complex) datatypes defined by this bb
- `aspects/`: groups of properties that may be included in feature types (equivalent to attribute groups in XML schema)
- `assets/`: Documentation assets (e.g. images) directory. See [Assets](#assets) below.
