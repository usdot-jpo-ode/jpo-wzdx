# Lane Type 
A description of the type of a lane on the roadway.

## Values
Value | Description
--- | ---
`lane` | Generic lane type, intended to be used for normal, driveable lanes
`right-turning-lane` | A lane where right turns are permissible
`left-turning-lane`| A lane where left turns are permissible
`right-exit-lane` | A lane with an egress on the right
`left-exit-lane` | A lane with an egress on the left
`left-exit-ramp`| An exit ramp with an egress on the left in the direction of flow at an interchange
`right-exit-ramp` | An exit ramp with an egress on the right in the direction of flow at an interchange
`right-entrance-ramp` | A lane or ramp with an ingress on the right
`left-entrance-ramp` | A lane or ramp with an ingress on the left
`sidewalk` | A sidewalk or pedestrian way
`bike-lane` | A lane on the roadway for cyclists only
`shoulder` | A generic shoulder
`center-left-turn-lane` | A lane in the center of a bidirectional roadway in which traffic from both directions uses to make a left turn

## Used By
Property | Object
--- | ---
`type` | [Lane](/spec-content/objects/Lane.md)

## Additional Information
The LaneType enumerated type was originally based on the TMDD LaneRoadway Enumeration, which is imported into TMDD from SAE 2540 (ITIS Standard).

In later release, other standards were examined for inspiration. These include SAE J2735 and the ISO 20524-1 Geographic Data Files (GDF) standard.