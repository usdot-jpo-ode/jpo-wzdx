# road_event_feed_info (Formerly WZDx Header Data)
**Required**

This table contains information about road event datasets.  For each record in the road_event_feed_info table there must exist one or more related records in the [road_events](/data-tables/road_events.md) table.  The feed_info_id field acts as the foreign key in the road_event table.

Field Name | Data Type | Description | Conformance | Notes
---------- | --------- | ---------------- | ----------- | -----
feed_info_id |	ID |	Identifies the feed	Required | Primary Key |
feed_update_date |	DateTime |	Designates the date and time the data feed was last updated. |	Required |	
feed_publisher |	Text |	The organization issuing the data feed. |	Optional	|
feed_metadata |	URL |	A link to the metadata file (WZ-metadata.txt). See Section 2.6 for a description of the file. |	Optional	 |
feed_version |	Float |	The specification version used to create the dataset |	Optional	 |