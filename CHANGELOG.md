# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Fixed
- Jellyfin 12.x compatibility: authenticate via `Authorization: MediaBrowser ... Token="..."` instead of the removed `X-Emby-Token` header (also works on 10.x)
- Clearer error message when Jellyfin rejects the API key

## [1.0.0] - 2024-12-26

### Added
- Initial release
- Web interface for dovi_convert script
- Directory browser for selecting media paths
- Real-time output streaming via WebSocket
- Scan functionality to find Dolby Vision files
- Batch conversion with configurable options
- Safe mode support
- Auto-cleanup option for backup files
- Persistent settings storage
- Docker multi-architecture support (amd64, arm64)
- Unraid Community Applications template
- GitHub Actions for automated builds

### Dependencies
- dovi_convert script v6.6.3
- dovi_tool v2.1.2
- FFmpeg
- MKVToolNix
- MediaInfo


