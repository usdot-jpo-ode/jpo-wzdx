<img src="https://raw.githubusercontent.com/usdot-jpo-ode/jpo-wzdx/b3ee31a7a231270e536e4d71a7a45623c1e4ec99/images/wzdx_logo_blue_orange_x.png" height="150"/>

# Work Zone Data Exchange (WZDx) Specification

## Summary

This repository contains the Work Zone Data Exchange (WZDx) Specification.

The WZDx Specification repository contains two main subdirectories, each containing their own README file with additional information about the purpose and files within:


1. [`create-feed`](/create-feed), which contains information regarding the creation of a WZDx feed, including feed format, example feeds, JSON schemas, and validation tools.
2. [`spec-content`](/spec-content), which details the data content of the WZDx specification, including objects, property names and types, and enumerated types.


A third directory, [`images`](/images), contains the images that are referenced throughout the repository.

## Contents
- [**Creating the WZDx Feed**](/create-feed)
    - [**Example Feed GeoJSON Files**](/create-feed/examples)   
        - [LineString Example](/create-feed/examples/linestring_example.geojson)
        - [MultiPoint Example](/create-feed/examples/multipoint_example.geojson)
    - [**JSON Schemas**](/create-feed/schemas)
        - [WZDx v2.0 Feed](/create-feed/schemas/wzdx_v2.0_feed.json)
        - [WZDx v3.0 Feed](/create-feed/schemas/wzdx_v3.0_feed.json)

- [**Specification Content**](/spec-content)
    - [**Objects**](/spec-content/objects)
        - [WZDXFeed](/spec-content/objects/WZDxFeed.md)
        - [RoadEventFeedInfo](/spec-content/objects/RoadEventFeedInfo.md)
        - [RoadEventDataSource](/spec-content/objects/RoadEventDataSource.md)
        - [RoadEventFeature](/spec-content/objects/RoadEventFeature.md)
        - [RoadEvent](/spec-content/objects/RoadEvent.md)
        - [TypeOfWork](/spec-content/objects/TypeOfWork.md)
        - [Lane](/spec-content/objects/Lane.md)
        - [LaneRestriction](/spec-content/objects/LaneRestriction.md)
        - [Relationship](/spec-content/objects/Relationship.md)
    - [**Enumerated Types**](/spec-content/enumerated-types)
        - [EventStatus](/spec-content/enumerated-types/EventStatus.md)
        - [EventType](/spec-content/enumerated-types/EventType.md)
        - [LaneRestrictionUnit](/spec-content/enumerated-types/LaneRestrictionUnit.md)
        - [LaneStatus](/spec-content/enumerated-types/LaneStatus.md)
        - [LocationMethod](/spec-content/enumerated-types/LocationMethod.md)
        - [RoadRestriction](/spec-content/enumerated-types/RoadRestriction.md)
        - [SpatialVerification](/spec-content/enumerated-types/SpatialVerification.md)
        - [TimeVerification](/spec-content/enumerated-types/TimeVerification.md)
        - [VehicleImpact](/spec-content/enumerated-types/VehicleImpact.md)
        - [WorkTypeName](/spec-content/enumerated-types/WorkTypeName.md)
        - [**Enumerated Types Derived from ITS Standards**](/spec-content/enumerated-types/derived-from-its-standards)
            - [Direction](/spec-content/enumerated-types/derived-from-its-standards/Direction.md)
            - [LaneType](/spec-content/enumerated-types/derived-from-its-standards/LaneType.md)
- [**Images Used throughout the Specification**](/images)
  - [Object Diagram](/images/wzdx_object_diagram.jpg)
     - [Object Diagram editable draw.io file](/images/wzdx_object_diagram.drawio)


# README Outline
- [Work Zone Data Exchange (WZDx) Specification](#work-zone-data-exchange-wzdx-specification)
  - [Summary](#summary)
  - [Contents](#contents)
- [README Outline](#readme-outline)
- [Project Description](#project-description)
- [Contact Information](#contact-information)
- [Release Notes](#release-notes)
      - [Release v3.0 (Sep 2020)](#release-v30-sep-2020)
- [Getting Started](#getting-started)
- [Contributions](#contributions)
- [Versioning](#versioning)
- [License](#license)

# Project Description

**What is the WZDx Specification?**
The Work Zone Data Exchange (WZDx) Specification enables infrastructure owners and operators (IOOs) to make harmonized work zone data available for third-party use. The intent is to make travel on public roads safer and more efficient through ubiquitous access to data on work zone activity. Specifically, the project aims to get data on work zones to vehicles to help automated driving systems (ADS) and human drivers navigate more safely.

**Why is WZDx being developed?**
Improving access to work zone data is one of the top needs identified through the US Department of Transportation (USDOT) [Data for Automated Vehicle Integration (DAVI)](https://www.transportation.gov/av/data) effort.

Up-to-date information about dynamic conditions occurring on roads – such as construction events – can help ADS and humans navigate safely and efficiently. Many IOOs maintain data on work zone activity. However, a lack of common data standards and convening mechanisms makes it difficult and costly for third parties – including original equipment manufacturers (OEMs) and navigation applications – to access and use these data across various jurisdictions.

Inspired by [GTFS](https://developers.google.com/transit/gtfs/reference/), USDOT launched WZDx to jumpstart the voluntary adoption of a basic work zone data specification through collaboration with data producers and data users. Longer-term, the goal is to enable collaborative maintenance and expansion of the specification to meet the emerging needs of ADS.

**Who is involved in developing WZDx?**
The [Federal Highway Administration (FHWA)](https://www.fhwa.dot.gov/) and [Intelligent Transportation Systems Joint Program Office (ITS JPO)](https://www.its.dot.gov/) co-led the early stages of the WZDx project and remain actively involved along with the [Bureau of Transportation Statistics (BTS)](https://www.bts.gov/), [Federal Motor Carrier Safety Administration (FMCSA)](https://www.fmcsa.dot.gov/), and others in the USDOT. Several data producers and data users voluntarily developed v1.1 of the specification in collaboration with USDOT, and have started to set up data feeds based on it:
- The Texas Department of Transportation data feed based on WZDx Specification v2.0 can be found [here](https://datahub.transportation.gov/Roadways-and-Bridges/Work-Zone-Data-Exchange-WZDx-Feed-Registry/69qe-yiui)
- The Massachusetts Department of Transportation data feed based on WZDx Specification v2.0 can be found [here](https://wzdx.massdot-swzm.com/massdot_wzdx_v2.0.geojson)
- The Maricopa County Department of Transportation data feed based on WZDx Specification v1.1 can be found [here](https://datahub.transportation.gov/Roadways-and-Bridges/Work-Zone-Data-Exchange-WZDx-Feed-Registry/69qe-yiui), v2.0 can be found [here](https://api.mcdot-its.com/WZDx_v2.0/Activity/Get), and v3.0 can be found [here](https://api.mcdot-its.com/WZDx_v3.0/Activity/Get)
- The Iowa Department of Transportation data feed based on WZDx Specification v1.1 can be found [here](https://data.iowadot.gov/datasets/iowa-work-zone-data-exchange-wzdx).

Going forward, the [Work Zone Data Working Group (WZDWG)](https://github.com/usdot-jpo-ode/jpo-wzdx/wiki), established under the Federal Geographic Data Committee (FGDC) Transportation Subcommittee (TSC) will maintain the WZDx Specification with the goal of publishing incremental updates to refine the features, attributes, and vocabulary needed to model work zone activity data.

**How can I get help with implementation?**
This project repository will be continually updated with resources to help with implementation - in the meantime, please make a GitHub issue or discussion entry if you need help implementing the WZDx Specification or have questions.

The Federal Highway Administration is leading efforts, via the [Work Zone Data Initiative (WZDI)](https://collaboration.fhwa.dot.gov/wzmp/wzdi/Forms/AllItems.aspx), to develop a standard approach for collecting, organizing, and sharing data on the “when”, “where,” and “how” of work zone deployment.  As part of this effort, key documents have been developed and made publicly available:

- [WZDI Framework](https://collaboration.fhwa.dot.gov/wzmp/Framework/Forms/AllItems.aspx) provides a conceptual architecture for work zone data systems for collecting, storing, disseminating, managing, maintaining and archiving work zone activity data.
- [WZDI Data Dictionary](https://collaboration.fhwa.dot.gov/wzmp/Data%20DictionaryDocuments/Forms/AllItems.aspx) provides digital descriptions of work zone activities that enable and support transportation agencies and third party providers to describe and communicate work zone-related information to agency, private sector, and public users timely and seamlessly across multiple jurisdictions and regions.

# Contact Information

Contact Name: ITS JPO

Contact Information: [avdx@dot.gov](mailto:avdx@dot.gov?subject=Submission%20of%20WZDx%20Specification%20Issue&Body=Issue%20name:%20“[Clarification%20/%20New%20feature%20/%20Question%5d%20—%20Summarize%20topic”%20%0d%23%23%20Summary%0dA%20concise%20description%20of%20the%20problem,%20feature%20request%20(proposed%20change),%20or%20question.%20%0d%23%23%20Motivation%0dFor%20a%20clarification…%20Describe%20the%20ambiguity%20or%20edge%20case(s)%20in%20further%20detail,%20and%20the%20issues%20and%20problems%20this%20poses.%20%0dFor%20a%20new%20feature…%20Describe%20the%20use%20case%20that%20requires%20this%20data%20spec%20feature.%20%0dFor%20a%20question…%20Describe%20the%20deliberation%20that%20led%20to%20the%20question%20within%20your%20project%20or%20organization.%20%0d%23%23%20Proposed%20changes%0d%20In%20the%20case%20of%20a%20proposed%20change,%20provide%20one%20or%20a%20few%20options%20for%20moving%20forward.)

# Release Notes

#### Release v3.0 (Sep 2020)

- Restrict version format to major.minor and enforce via WZDx v3.0 JSON schema
- Add order property to lane entity to indicate a lane's position in sequence on the roadway
- Remove lane_edge_reference and standardize on counting lanes from the left side of the roadway
- Add event_type property to the road event entity and new Event Type Enumerated Type with the values work-zone and detour, to support adding detour information (and more in the future)
- Add relationship entity (one per road event entity) to enable describing relationships (hierarchical and sequential) between road events and other non-WZDx entities (such as a work zone phase or project)
- Add road_event_data_source entity to allow specifying multiple data sources within a single feed
- Streamline metadata (previously given in an external file, by URL) and add relevant fields to the road_event_feed_info and road_event_data_source entities
- Require restriction_type if providing a lane-level restriction
- Change Spatial Verification Enumerated Type and Time Verification Enumerated Type values to be all lowercase
- Remove all plural or nonsensical lane types from the Lane Type Enumerated Type and clarify that each WZDx lane should represent a single lane on the roadway


# Getting Started

The WZDWG welcomes feedback and comments on the WZDx 3.0 Specification. Comments can be made by posting a GitHub [Issues](https://github.com/usdot-jpo-ode/jpo-wzdx/issues) or [Discussions](https://github.com/usdot-jpo-ode/jpo-wzdx/discussions), while suggested changes can be made using a [Pull Request](https://github.com/usdot-jpo-ode/jpo-wzdx/pulls).

1. Read about WZDWG activities [Wiki](https://github.com/usdot-jpo-ode/jpo-wzdx/wiki) and the [WZDx Early Adopter's Guide](https://github.com/usdot-jpo-ode/jpo-wzdx/blob/create_feed_updates/documents/WZDx%20Early%20Adopters%20Guide.pdf)
2. Learn about using GitHub as a [tool for collaboration and support](/create-feed/README.md#collaborate-via-github).
3. Use [Specification Content](/spec-content) page to understand the data components of the specification.
4. [Create your own feed](/create-feed) using example feeds and follow the business rules.
5. Validate your feed output using the [WZDx v3.0 Feed JSON Schema](https://github.com/usdot-jpo-ode/jpo-wzdx/blob/master/create-feed/schemas/wzdx_v3.0_feed.json)
6. Publish your feed and tell us about it via avdx@dot.gov.

# Contributions

**How do I contribute to the WZDx Specification?**

- Report bugs and request features via [GitHub Issues](https://github.com/usdot-jpo-ode/jpo-wzdx/issues).
- Ask the WZDx community for input on a question or propose an idea you have via [GithHb Discussions](https://github.com/usdot-jpo-ode/jpo-wzdx/discussions).
- Create a [GitHub pull request](https://help.github.com/articles/creating-a-pull-request/) that outlines a new functionality or fixes a bug.
- Review and provide feedback on update issues/discussions/pull requests created by other users.
- Alternatively, [email us](mailto://avdx@dot.gov.) with any questions.
- Help us improve our best practices and formatting on GitHub.

# Versioning

The WZDx specification uses a major.minor versioning scheme, similar to [SemVer](https://semver.org/). The rules are as follows:

1. The minor version number must be incremented if new, backwards compatible fields/entities/enumerations are introduced or if any existing fields/entities/enumerations are marked as deprecated.
2. The major version number must be incremented if any backwards incompatible changes are introduced.
3. Neither version number shall be incremented for documentation changes/clarifications that have no effect on either the specification schema or the content or structure of a GeoJSON feed file which conforms to the specification.

To view available versions, refer to the [tags](https://github.com/usdot-jpo-ode/jpo-wzdx/tags) section of this repository.

# License

The WZDx project is in the worldwide public domain (i.e., in the public domain within the United States - copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal](https://creativecommons.org/share-your-work/public-domain/cc0/) public domain dedication). All contributions to this project will be released under the CC0 dedication. By submitting a pull request, you are agreeing to comply with the waiver of copyright interest. see [License](LICENSE) for more details.
