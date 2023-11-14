# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.2.0]
### Uncategorized
- chore: add missing releases to CHANGELOG.md
- format CHANGELOG.md
- rename package from ethjs-filter to @metamask/ethjs-filter
- npm v5+ compat: rename prepublish script to prepare
- chore: add .nvmrc set to v12
- chore: remove unused devDependencies
- chore: remove lint:staged script
- npm dedupe; npm audit fix
- ci: move from TravisCI to GitHub Actions ([#4](https://github.com/legobeat/ethjs-filter/pull/4))
- deprecate nodejs <8.17, npm<6 ([#5](https://github.com/legobeat/ethjs-filter/pull/5))
- Check in lockfile ([#3](https://github.com/legobeat/ethjs-filter/pull/3))
- v0.1.8
- v0.1.7
- v0.1.6
- fix for BlockFilter
- version 0.1.5 -- config fixes
- version 0.1.4 -- minor fix to object assign
- version 0.1.3 -- decoder, defaultTxObject

## [0.1.8]
### Fixed
- Remove redundant dependency `ganache-core`

## [0.1.7]
### Changed
- Add dependency `ganache-core`

## [0.1.6]
### Removed
- Removed promise watch, only for callbacks

### Fixed
- Fixed unhandled promise rejection

## [0.1.5]
### Changed
- config fixes
  - webpack config updates
  - build config updates

## [0.0.1]
### Added
- ethjs-filter
  - Basic testing
  - Basic docs
  - License

[Unreleased]: https://github.com/legobeat/ethjs-filter/compare/v0.2.0...HEAD
[0.2.0]: https://github.com/legobeat/ethjs-filter/compare/v0.1.8...v0.2.0
[0.1.8]: https://github.com/legobeat/ethjs-filter/compare/v0.1.7...v0.1.8
[0.1.7]: https://github.com/legobeat/ethjs-filter/compare/v0.1.6...v0.1.7
[0.1.6]: https://github.com/legobeat/ethjs-filter/compare/v0.1.5...v0.1.6
[0.1.5]: https://github.com/legobeat/ethjs-filter/compare/v0.0.1...v0.1.5
[0.0.1]: https://github.com/legobeat/ethjs-filter/releases/tag/v0.0.1
