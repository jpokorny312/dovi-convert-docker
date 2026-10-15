# v1.2.0 – Jellyfin 12 support

## Highlights
- **Jellyfin 12.x compatible.** Jellyfin 12 disables legacy authentication by default, so the previous `X-Emby-Token` header resulted in `401` on every call. The app now authenticates with the `Authorization: MediaBrowser … Token="…"` header, which also works on Jellyfin 10.x/11.x.

## Improvements
- Jellyfin library scan is paged (500 items per request) with progress output, instead of one 10,000-item request.
- More reliable metadata refresh after conversion/restore: exact path match first, then a unique exact file name; falls back to notifying Jellyfin via `/Library/Media/Updated`. Previously partial name matches could refresh the wrong item.
- Timeouts on all Jellyfin requests; clearer error when the API key is rejected (401).
- Updated Python dependencies (FastAPI, uvicorn, aiohttp, pydantic, Jinja2, websockets, python-multipart).

## Upgrade notes
- No configuration changes needed. Existing Jellyfin URL/API key settings keep working.
- Pull the new image: `docker pull <user>/dovi-convert:1.2.0`

## Full changelog
See [CHANGELOG.md](CHANGELOG.md).
