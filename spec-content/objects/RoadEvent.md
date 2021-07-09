# RoadEvent Object
The `RoadEvent` object contains information that describes where, when, and what activity is taking place along a road segment. This specification currently accommodates `work-zone` and `detour` type road events, specified by the road event's `event_type` property (see [EventType](/spec-content/enumerated-types/EventType.md])).

## Properties
Name | Type | Description | Conformance | Notes
--- | --- | --- | --- | ---
`event_type` | [EventType](/spec-content/enumerated-types/EventType.md) | The type/classification of road event. | Required |
`data_source_id` | String | Identifies the data source from which the road event originates. | Required | The value must match to the `data_source_id` property of a [RoadEventDataSource](/spec-content/objects/RoadEventDataSource.md) included within the same WZDx GeoJSON document.
`start_date` | String; [date-time](https://tools.ietf.org/html/draft-handrews-json-schema-validation-01#section-7.3.1) | The UTC time and date when the event begins. | Required | All datetime formats shall follow [RFC 3339 Section 5.6](https://tools.ietf.org/html/rfc3339#section-5.6). Example: `2016-11-03T19:37:00Z`.
`end_date` | String; [date-time](https://tools.ietf.org/html/draft-handrews-json-schema-validation-01#section-7.3.1) | The UTC time and date when the event ends. | Required | All datetime formats shall follow [RFC 3339 Section 5.6](https://tools.ietf.org/html/rfc3339#section-5.6). Example: `2016-11-03T19:37:00Z`.
`start_date_accuracy` | [TimeVerification](/spec-content/enumerated-types/TimeVerification.md) | A measure of how accurate the start Date Time is. | Required |
`end_date_accuracy` | [TimeVerification](/spec-content/enumerated-types/TimeVerification.md) | A measure of how accurate the end Date Time is. | Required | 
`beginning_accuracy` | [SpatialVerification](/spec-content/enumerated-types/SpatialVerification.md) | Indicates how the beginning coordinate was defined. | Required |
`ending_accuracy` | [SpatialVerification](/spec-content/enumerated-types/SpatialVerification.md) | Indicates how the ending coordinate was defined. | Required |
`road_names` | Array; [String] | A list of publicly known names of the road on which the event occurs. This may include the road number designated by a jurisdiction such as a county, state or interstate (e.g. I-5, VT 133). | Conditional: required if `road_name` is not provided. | This property captures the functionality of the deprecated `road_number` and `road_name` properties and conformance will be required in a future release.
`direction` | [Direction](/spec-content/enumerated-types/Direction.md) | The digitization direction of the road that is impacted by the event. This value is based on the standard naming for US roadways and indicates the direction of the traffic flow regardless of the real heading angle. | Required | Example `northbound` (for I-5 North)
`vehicle_impact` | [VehicleImpact](/spec-content/enumerated-types/VehicleImpact.md) | The impact to vehicular lanes along a single road in a single direction. | Required |
`relationship` | [Relationship](/spec-content/objects/Relationship.md) | Identifies both sequential and hierarchical relationships between the road events and other entities. For example, a relationship can be used to link multiple road events to a common 'parent', such as a project or phase, or identify a sequence of road events | Optional | 
`lanes` | Array; \[[Lane](/spec-content/objects/Lane.md)\] | A list of individual lanes within a road event (roadway segment) | Optional |
`beginning_cross_street` | String | Name or number of the nearest cross street along the roadway where the event begins. | Optional |
`ending_cross_street` | String | Name or number of the nearest cross street along the roadway where the event ends. | Optional |
`beginning_milepost` | Number | The linear distance measured against a milepost marker along a roadway where the event begins. | Optional | A milepost or mile marker is a surveyed distance posted along a roadway measuring the length (in miles or tenth of a mile) from the south west to the north east. These markers are typically notated on State and local government digital road networks.
`ending_milepost` | Number | The linear distance measured against a milepost marker along a roadway where the event ends. | Optional | A milepost or mile marker is a surveyed distance posted along a roadway measuring the length (in miles or tenth of a mile) from the south west to the north east. These markers are typically notated on State and local government digital road networks.
`event_status` | [EventStatus](/spec-content/enumerated-types/EventStatus.md) | The status of the event. | Optional |
`types_of_work` | Array; \[[TypeOfWork](/spec-content/objects/TypeOfWork.md)\] | A list of the types of work being done in a road event and an indiciation of if each type results in an architectural change to the roadway. | Optional | 
`workers_present` | Boolean | A flag indicating that there are workers present in the event space. | Optional |
`reduced_speed_limit` | Integer | The reduced speed limit posted within the event space. | Optional |
`restrictions` | Array; \[[RoadRestriction](/spec-content/enumerated-types/RoadRestriction.md)\] | Zero or more road restrictions applying to the work zone road segment associated with the work zone. | Optional | These are included as flags rather than detailed restrictions. Detailed restrictions are coded to specific lanes.
`description` | String | Short free text description of work zone. | Optional | This will be populated with formal phrases in a later WZDx version
`creation_date` | String; [date-time](https://tools.ietf.org/html/draft-handrews-json-schema-validation-01#section-7.3.1) | The UTC time and date when the activity or event was created. | Optional | All datetime formats shall follow [RFC 3339 Section 5.6](https://tools.ietf.org/html/rfc3339#section-5.6). Example: `2016-11-03T19:37:00Z`.
`update_date` | String; [date-time](https://tools.ietf.org/html/draft-handrews-json-schema-validation-01#section-7.3.1) | The UTC time and date when the activity or event was updated. | Optional | All datetime formats shall follow [RFC 3339 Section 5.6](https://tools.ietf.org/html/rfc3339#section-5.6). Example: `2016-11-03T19:37:00Z`.
`road_event_id` (DEPRECATED) | String | *This property is deprecated; use the `id` property on the parent [RoadEventFeature](/spec-content/objects/RoadEventFeature.md) object instead* — A unique identifier issued by the data feed provider to identify the road event activity. | Optional | This property will be removed in a future version of WZDx.
`road_number` (DEPRECATED) | String | *This property is deprecated and will be removed in a future version; include road numbers within the `road_names` array instead* — The road number designated by a jurisdiction such as a county, state, or interstate. | Optional | Examples I-5, VT 133.
`road_name` (DEPRECATED) | String | *This property is deprecated and will be removed in a future version; include road names within the `road_names` array instead* — Publicly known name of the road on which the event occurs. | Conditional: required if `road_names` property is not provided. | 
`total_num_lanes` (DEPRECATED) | Integer | *This property is deprecated and will be removed in a future version* — The total number of lanes associated with the road segment designated by the event geometry. | Optional | A segment is a part of a roadway in a single direction designated the event geometry.

## Used By
Property | Object
--- | ---
`properties` | [RoadEventFeature](/spec-content/objects/RoadEventFeature.md)

## Important Notes
The value of the `RoadEvent`'s `data_source_id` property MUST match the value of the `data_source_id` property of a [RoadEventDataSource](/spec-content/objects/RoadEventDataSource.md) that is included in the same WZDx GeoJSON document.
