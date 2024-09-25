## What it represents

A Datastream groups a collection of Observations measuring the same ObservedProperty and produced by the same Sensor. [https://docs.ogc.org/is/18-088/18-088.html#datastream].

Datastreams may be raw values or observation objects inheriting common property values from the Datastream description.

### Limitations

Observations navigation link is to an array of observation properties. This requires an extra schema element to navigate the relationship between OMS/SOSA ObservationCollection and the set of observations as direct members. 

## References

Requirements: [http://www.opengis.net/spec/iot_sensing/1.1/req/datamodel#datastream](https://docs.ogc.org/is/18-088/18-088.html#datastream)
