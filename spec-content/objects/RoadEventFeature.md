# RoadEventFeature Object (GeoJSON Feature)
The `RoadEventFeature` object is the container object for a WZDx [RoadEvent](/spec-content/objects/RoadEvent.md). The `RoadEventFeature` object is an instance of a [GeoJSON Feature](https://tools.ietf.org/html/rfc7946#section-3.2).

## Properties
Name | Type | Description | Conformance | Notes
--- | --- | --- | --- | ---
`id` | String | A unique identifier issued by the data feed provider to identify the WZDx road event. | Conditional; Required if road event's ID is not provided via the `road_event_id` property on the road event (detailed in the `properties` property). | In prior versions of WZDx, the road event ID was given by a `road_event_id` property on the [RoadEvent](/spec-content/objects/RoadEvent.md) object. Now, `road_event_id` is deprecated and this `id` should be used instead. This property will be required in a future version of WZDx. This is a GeoJSON property. 
`type` | String; `"Feature"` | The GeoJSON object type. This must be the string `Feature`. | Required | This is a GeoJSON property.
`properties` | [RoadEvent](/spec-content/objects/RoadEvent.md) | The specific details of road event. | Required | This is a GeoJSON property.
`geometry` | GeoJSON [Geometry](https://tools.ietf.org/html/rfc7946#section-3.1) object with `type` of [LineString](https://tools.ietf.org/html/rfc7946#section-3.1.4) or [MultiPoint](https://tools.ietf.org/html/rfc7946#section-3.1.3) | The geometry of the road event. The Geometry object's `type` property MUST be [LineString](https://tools.ietf.org/html/rfc7946#section-3.1.4) or [MultiPoint](https://tools.ietf.org/html/rfc7946#section-3.1.3). `LineString` allows specifying the entire road event path and should be preferred. `MultiPoint` should be used when only the start and end coordinates are known. | Required | This is a GeoJSON property.
`bbox` | GeoJSON [Bounding Box](https://tools.ietf.org/html/rfc7946#section-5) | Information on the coordinate range for this RoadEventFeature. Must be an array of length 2*n where n is the number of dimensions represented in the `geometry` property, with all axes of the most southwesterly point followed by all axes of the more northeasterly point.  The axes order of a bbox follows the axes order of the `geometry`. | Optional | This is a GeoJSON property.

## Used By
Property | Object
--- | ---
`features` | [WZDx Feed](/spec-content/objects/WZDxFeed.md)
