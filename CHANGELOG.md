Change Log
==========

## 1.3.0

_2016-11-23_

* Consistently name entity and response classes.
* `Series`: Add `siteRatingCount`. Use `Integer` for `lastUpdated` (was `Long`).
* `SeriesImageQueryResult`: Add `count` to `ratingsInfo`.
* `Episode`: `lastUpdated` is returned with basic episode data, `directors` list instead of `director`, 
  full data added `siteRatingCount`, use `Integer` for `seriesId` (was `int`).
* Add `errors` field to `EpisodeResponse`, `EpisodesResponse`, `SeriesResponse`.
* Update retrofit to 2.1.0.
* Removed built-in logging support. Simply subclass `TheTvdb` and add your own logger by overriding `setOkHttpClientDefaults()`.
  See `BaseTestCase` for an example.

## 1.2.0

_2016-05-06_

* Use version 2.1.0 of the TheTVDB API.
* Update to retrofit 2.0.2.
* Add `/episodes/{id}` endpoint.

## 1.1.2

_2016-04-20_

* Add additional properties to `BaseEpisode` entity (`airedSeasonID`, `firstAired` and `language`).

## 1.1.1

_2016-04-20_

* Make `TheTvdbInterceptor` handling publicly accessible as well.

## 1.1.0

_2016-04-15_

* Rename `Series` service to `SeriesService` to avoid naming conflict with the entity `Series`.
* Make using a shared OkHttp client easier: `TheTvdbInterceptor` now only interecepts if the host is `api.thetvdb.com`.
  `TheTvdbAuthenticator` response handling is publicly accessible through its `handleRequest()` method so it can be used
  in your own authenticator implementation.

## 1.0.2

_2016-04-14_

* Do not retry `/login` requests, fail immediately if `401 Unauthorized` is returned.

## 1.0.1

_2016-04-09_

* Remove deprecated `seriesId` from `Series` entity. Would return empty string instead of integer if not available, so
  remove it altogether. 

## 1.0.0

_2016-04-08_

* Initial release supporting TheTVDB API v2.0.0 final.
* Many endpoints are still incomplete, pull requests are welcome.