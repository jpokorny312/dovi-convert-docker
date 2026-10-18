# v1.2.1 – Cleaner conversion output

## Fixes
- **Web UI output:** The progress bar of `dovi_convert` is now shown as a single-line progress bar (percent, step, elapsed time, ETA) that updates in place instead of one new line per update. Conversion progress is easy to follow again, and the log history stays compact.
- **Responsiveness:** ANSI control codes of the `dovi_convert` spinner are stripped, and spinner updates are throttled, so the UI no longer lags during long steps.

## Included from v1.2.0
- Jellyfin 12.x compatibility (`Authorization: MediaBrowser` header instead of the removed `X-Emby-Token`), paged library scans, exact item matching for metadata refresh, request timeouts, updated dependencies.

## Upgrade notes
- No configuration changes needed. Pull the new image: `docker pull jpkrny/dovi-convert:1.2.1`

## Full changelog
See [CHANGELOG.md](CHANGELOG.md).
