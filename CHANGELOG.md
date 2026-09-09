# Changelog

All notable changes are documented here.
Format follows keepachangelog.com, versions are semver-ish.

## [0.3.9] - 2026-08-24

### Fixed
- crash on paths containing spaces
- edge case when the input list is empty

### Changed
- smaller memory footprint on large inputs

## [0.2.0] - 2026-04-12

### Added
- 4xx fails fast; 429 and 5xx retry with jittered backoff

## [0.1.0] - 2026-06-21

### Added
- 4xx fails fast; 429 and 5xx retry with jittered backoff
