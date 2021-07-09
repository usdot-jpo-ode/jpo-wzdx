# Lane Status
The status of a lane for the traveling public.

## Values
Value | Description
--- | ---
`open` | The lane is open for travel
`closed` | The lane is closed to travel
`shift-left` | The lane shifts left from its current bearing and continues
`shift-right` | The lane shifts right from its current bearing and continues
`merge-left` | The lane gradually tapers while merging into the lane directly to the left 
`merge-right` | The lane gradually tapers while merging into the lane directly to the right
`alternating-flow` | Traffic may travel in either direction, depending on certain conditions. Example conditions include time of day (e.g. reversible lanes), automated controls, or on-site personnel

## Used By
Property | Object
--- | ---
`status` | [Lane](/spec-content/objects/Lane.md)
