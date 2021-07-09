# RoadEventDataSource Object
The `RoadEventDataSource` object describes information about a specific data source used to build a work zone data feed. A WZDx feed must contain at least one `RoadEventDataSource`, included as an entry in the `data_sources` array of the `RoadEventFeedInfo` object.

## Properties
Name | Type | Description | Conformance | Notes
--- | --- | --- | --- | ---
`data_source_id` | String | Unique identifier for the data source organization providing work zone data. | Required | Linked to a [RoadEvent](/spec-content/objects/RoadEvent.md) by the `RoadEvent`'s `data_source_id` property.
`organization_name` | String | The name of the organization for the authoritative source of the work zone data. | Required | Example: County DOT
`location_method` | [LocationMethod](/spec-content/enumerated-types/LocationMethod.md) | The typical method used to locate the beginning and end of a work zone impact area. | Required | 
`update_date` | String; [date-time](https://tools.ietf.org/html/draft-handrews-json-schema-validation-01#section-7.3.1) | The UTC date and time when the data source was last updated. | Optional | All date-time formats shall follow [RFC 3339 Section 5.6](https://tools.ietf.org/html/rfc3339#section-5.6). Example: `2016-11-03T19:37:00Z`
`update_frequency` | Integer | The frequency in seconds at which the data source is updated. | Optional |
`contact_name` | String | The name of the individual or group responsible for the work zone data source. | Optional | Example: `Jo Help`
`contact_email` | String; [email](https://tools.ietf.org/html/draft-handrews-json-schema-validation-01#section-7.3.2) | The email address of the individual or group responsible for the data source. | Optional |
`location_verify_method` | String | The method used to verify the accuracy of the location information. | Optional | Example: `Survey accurate GPS equipment accurate to 0.1 cm`

## Used By
Property | Object
--- | --- 
`data_sources` | [RoadEventFeedInfo](/spec-content/objects/RoadEventFeedInfo.md)

## Additional Notes
The value of a `RoadEventDataSource`'s `data_source_id` property should match the value of the `data_source_id` property of at least one [RoadEvent](/spec-content/objects/RoadEvent.md) that is included within the same WZDx GeoJSON document.
