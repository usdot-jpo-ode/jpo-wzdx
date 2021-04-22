# Road Restriction
The type of vehicle restriction on a roadway.

## Values
Value | Description
--- | ---
`local-access-only` | Travel allowed only for vehicles accessing addresses in the work zone area; this includes emergency services, deliveries, and direct property access
`no-trucks` | Trucks are prohibited from traveling in work zone area
`travel-peak-hours-only` | Travel restricted to travel peak hours only
`hov-3` | Travel restricted to high occupancy vehicles of three or more
`hov-2` | Travel restricted to high occupancy vehicles of two or more
`no-parking` | No parking in work zone area
`reduced-width` | Lane width is reduced in work zone area
`reduced-height` | Height restrictions reduced in work zone area
`reduced-length` | Vehicle length restrictions reduced in work zone area
`reduced-weight` | Vehicle weight restrictions reduced in work zone area
`axle-load-limit` | Vehicle axle-load-limit restrictions reduced in work zone area
`gross-weight-limit` | Vehicle gross-weight-limit restrictions reduced in work zone area
`towing-prohibited` | Towing prohibited in work zone area
`permitted-oversize-loads-prohibited` | “Permitted oversize loads” prohibited in work zone area; this applies to annual oversize load permits.

## Used By
Property | Object
--- | ---
`restrictions` | [RoadEvent](/spec-content/objects/RoadEvent.md)
`restriction_type` | [LaneRestriction](/spec-content/objects/LaneRestriction.md)
