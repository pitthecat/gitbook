# Changelog

## 1.1.1

### Added

*  feat: allow excluding branches from triggering slack hooks [\#406](https://github.com/sorry-cypress/sorry-cypress/pull/406) by  [@ImanMahmoudinasab](https://github.com/ImanMahmoudinasab)

### Fixed

* fix:  properly show git SSH URLs [\#413](https://github.com/sorry-cypress/sorry-cypress/pull/413) by [@Zaista](https://github.com/Zaista)

## 1.1.0

### Added

* feat: Allow resetting instance for retesting [fae3f7a](https://github.com/sorry-cypress/sorry-cypress/commit/fae3f7a6bac8e24ed3b4c4546043f8f48f2ac31b) by [@Aeolun](https://github.com/Aeolun)

## 1.0.3

### Fixed

* fix: show correct duration in specs list [98ae7be](https://github.com/sorry-cypress/sorry-cypress/commit/98ae7be35005eadd0981455396cfe608f998fc2b). Closes [\#374](https://github.com/sorry-cypress/sorry-cypress/issues/374).
* fix: heroku build build process [a658d3f](https://github.com/sorry-cypress/sorry-cypress/commit/a658d3f34dd988a9b281dfbe659626473e47f665). Closes [\#373](https://github.com/sorry-cypress/sorry-cypress/issues/373).

### Dependencies

* deps: dns-packet-1.3.4 [1358c74](https://github.com/sorry-cypress/sorry-cypress/commit/1358c7431babac346bca8f79c591c0d6a305ce84)

## 1.0.2

### Fixed

* fix: handle nullable results.tests [a469c76](https://github.com/sorry-cypress/sorry-cypress/commit/a469c76a586a35e71c8756f269aadb81fb375b48). Closes [\#360](https://github.com/sorry-cypress/sorry-cypress/issues/360).

## 1.0.1

### Changes

* Serve css and fonts locally [9e5c3a5](https://github.com/sorry-cypress/sorry-cypress/commit/9e5c3a5b28f6660c58bf7d81739c31114e44e640). Closes [\#363](https://github.com/sorry-cypress/sorry-cypress/issues/363)

### Fixed

* Allow skipping --parallel flag [d7a64b0](https://github.com/sorry-cypress/sorry-cypress/commit/d7a64b0fba4533d5b282e087f907f5304d52eda2). Closes [\#365](https://github.com/sorry-cypress/sorry-cypress/issues/365)

## 1.0.0 🎉

### Changed

* remove inactivity timeout implementation
* use runs timeout via project settings
* add `RUN_TIMEDOUT` hook - based on the project runs timeout settings
* emit `RUN_FINISH` for each group in a run

## 1.0.0-rc.12

### Fixed

* Return `runId` with `getInstance` query. [Issue \#357](https://github.com/sorry-cypress/sorry-cypress/issues/357).

## 1.0.0-rc.11

### Added

* Show retry count on run details page. [\#350](https://github.com/sorry-cypress/sorry-cypress/pull/350) by [@boxofcrates](https://github.com/boxofcrates)

### Changed

* Refactor instance results retrieval - use GQL query resolved. Increate auto-refresh rate to 5 seconds. [\#336](https://github.com/sorry-cypress/sorry-cypress/pull/336) by [@anishkargaonkar](https://github.com/anishkargaonkar)

## 1.0.0-rc.10

### Fixed

* Correctly extract `ciBuildId` from Gitlab CI. [\#343](https://github.com/sorry-cypress/sorry-cypress/pull/343) by [@boxofcrates](https://github.com/boxofcrates)
* Fix support to projects with slashes. [\#340](https://github.com/sorry-cypress/sorry-cypress/pull/340) by [@fsmaia](https://github.com/fsmaia)

## 1.0.0-rc.9

### Fixed

* Successfully fire slack hooks without commit data. [\#328](https://github.com/sorry-cypress/sorry-cypress/pull/328) by [@pbeckham](https://github.com/pbeckham)
* Restore generic hooks functionality

### Changed

* Refactor - use `runSingleReporter` and move files [b296289](https://github.com/sorry-cypress/sorry-cypress/commit/b2962892c743219e43fdf289617d73b20dd06b2f)

## 1.0.0-rc.8

### Changed

* Remove mongo `$map` usages to simpler syntax and AWS DocumentDB compatibility. [PR \#324](https://github.com/sorry-cypress/sorry-cypress/pull/324).
* Support monorepos for BitBucket hooks. [PR \#325](https://github.com/sorry-cypress/sorry-cypress/pull/325).

## 1.0.0-rc.7

### Fixed

* Validate possibly empty results when checking run completion. [Issue \#317](https://github.com/sorry-cypress/sorry-cypress/issues/317)

## 1.0.0-rc.6

### Fixed

* Return `application/javascript` for `mjs` files served by dashboard `nginx` server. [Issue \#321](https://github.com/sorry-cypress/sorry-cypress/issues/321)

## 1.0.0-rc.5

### Changed

* Use `@graphql-tools/merge` to allow breaking down schema definitions to multiple files
* Remove aggregation stages for `runsFeed` to improve performance

## 1.0.0-rc.4

### Added

* Add slack hook filters and advanced formatting [\#309](https://github.com/sorry-cypress/sorry-cypress/pull/309) by [@DeniDoman](https://github.com/DeniDoman)

## 1.0.0-rc.3

### Fixed

* Support auto-detection of `ciBuildId` for major CI providers. [Issue \#310](https://github.com/sorry-cypress/sorry-cypress/issues/310)

## 1.0.0-rc.2

### Fixed

* Support cypress 6.7.0

## 1.0.0-rc.1

### Fixed

* Prevent hooks for in-memory driver

## 1.0.0-rc.0

### Added

* Sorry Cypress is now able to detect stale runs and properly report RUN\_FINISH hook using I[nactivity Timeout.](../concepts/inactivity-timeout.md) That includes. more complex cases when multiple spec groups involved.
* Optional [Redis](../configuration/persistent.md#redis-optional) integration via `REDIS_URI` director configuration variable.
* Bitbucket Integration

### Changed

* Webhooks, Github and Slack reporting mechanism was revisited and improved - the new implementation  immutable and has a better type support.
* Project Setting UI refactored
* The project now has a [common](https://github.com/sorry-cypress/sorry-cypress/tree/master/packages/common) package, which allows to share utilities, type definitions etc.
* Type definitions and GraphQL schema were updated and improved to allow better reusability, discovered and fixed a few bugs on the way.
* Major refactoring to dashboard files structure and improvements to components composition, polling and type definitions.
* Build process is now a bit more complex and slow because we need to build `common` package as part of every image.
* Node 14  everywhere
* Mongo 4.2
* Suggested development flow doesn't require docker compose anymore.
* Remove example - not used in docs anymore

### Fixed

* Properly detect `RUN_FINISH` 
* Remove Github / Bitbucket secrets from queries
* Test execution timer never stops for manually terminated runs [\#134](https://github.com/sorry-cypress/sorry-cypress/issues/134)
* "Finished" run changing its state to "started" when new machine is joined after finish [\#215](https://github.com/sorry-cypress/sorry-cypress/issues/215)
* Test duration time continuous to count [\#245](https://github.com/sorry-cypress/sorry-cypress/issues/245)
* Enhance Generic WebHook [\#248](https://github.com/sorry-cypress/sorry-cypress/issues/248)

## Older Versions

[Github Releases](https://github.com/sorry-cypress/sorry-cypress/releases)

### 



