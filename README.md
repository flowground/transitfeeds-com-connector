# ![LOGO](logo.png) TransitFeeds **flow**ground Connector

## Description

A generated **flow**ground connector for the TransitFeeds API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/transitfeeds.com/1.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:26+03:00

## API Description

API to view feed information and download feeds from TransitFeeds.com


## Authorization

This API does not require authorization.

## Actions

### Retrieve a list of versions of specified (or all) feeds.

> This API call allows you to easily see every single feed update in the TranstiFeeds.com system. Since this can be quite<br/>
> long, it's also possible to filter this list by a single feed ID.

#### Input Parameters
* `key` - _required_ - Your personal API key, used for authentication.
* `feed` - _optional_ - If you only want to retrieve feed versions for a particular feed, include its ID here. You can use the `/getFeeds` call to discover feed IDs.
* `page` - _optional_ - The page number of results to return. For example, if you specify a `page` of `2` with a `limit` of 10, then results 11-20 are returned.
The number of pages available is included in the response.

* `limit` - _optional_ - The maximum number of results to return..
* `err` - _optional_ - To include any errors detected when importing this feed in the response, specify a valud of `1`.
    Possible values: 0, 1.
* `warn` - _optional_ - To include any warnings detected when importing this feed in the response, specify a valud of `1`.
    Possible values: 0, 1.

### Retrieve a list of feeds.

> Used this API to retrieve a list of feeds in the system. Doing so can be usedful to discover feed IDs that<br/>
> can be used in other API calls.

#### Input Parameters
* `key` - _required_ - Your personal API key, used for authentication.
* `location` - _optional_ - This is the unique ID of a location. If specified, feeds will only be returned that belong to this location
(and perhaps sub-locations too, depending on the `descendants` value). You can use the `/getLocations` API
endpoint to determine location IDs.

* `descendants` - _optional_ - If a location is specified in `location`, this flag can be used to control if returned feeds must be assigned directly to the location, or if feeds belonging to sub-locations can also be returned. If `0`, then feeds must be assigned directly to the specified location.
    Possible values: 0, 1.
* `page` - _optional_ - The page number of results to return. For example, if you specify a `page` of `2` with a `limit` of 10, then results 11-20 are returned.
The number of pages available is included in the response.

* `limit` - _optional_ - The maximum number of results to return..
* `type` - _optional_ - The type of feeds to return. If unspecified, feeds of all types are returned.
    Possible values: gtfs, gtfsrealtime.

### Retrieve the download URL for the latest version of a feed.

> Once you have used `/getFeeds` to discover a feed's URL, you can use this endpoint to download its latest version from TranstiFeeds.<br/>
> It will be unmodified in the original format from the provider.

#### Input Parameters
* `key` - _required_ - Your personal API key, used for authentication.
* `feed` - _required_ - The ID of the feed to retrieve the latest feed version for. You can use the `/getFeeds` call to discover feed IDs.

### Retrieve a list of locations.

> Retrieve a list of locations. Each location (except for the root) has a parent location, and each<br/>
> location has zero or more child locations. This hierarchy is generally structured so countries contain<br/>
> states, states contain cities (although this typically depends on the country).

#### Input Parameters
* `key` - _required_ - Your personal API key, used for authentication.

## License

**flow**ground :- Telekom iPaaS / transitfeeds-com-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
