# Rowanvale 18.6.1 — Automatic Covers Everywhere

> **PRE-RELEASE — 18.6.1 release candidate.** This build is for testing and feedback, not a stable production release. Back up your local workspace before upgrading.

This fixes automatic artwork across Games & Media, Discover Games, Game Collection, Books Directory, Watch Room, Fan Lounge and Your Orbit. It preserves the 18.6 Personal Atlas, Reset Studio, all five media formats and existing local data.

## Launch the new build

1. Export a backup from the previous app and stop its server.
2. Use the supplied extracted Rowanvale_18.6.1 folder, or extract the complete new ZIP.
3. Double-click START_ROWANVALE_WINDOWS.bat. A supported Node.js installation is required (technical minimum 18); no npm install is required to run the app.
4. Keep the same browser profile and localhost:8080 address to retain its data. If needed, open http://localhost:8080/api/launch. Confirm version 18.6.1.

The launch endpoint bypasses Rowanvale's old cached shell while preserving your browser workspace and unrelated caches. Do not open index.html directly. Do not clear browser storage to upgrade. A previously running server must be stopped before launching this copy.

## What changed

Opening a media page now starts matched cover lookups, including unsaved directory entries. Cached covers display immediately; first-time online matches arrive progressively with visible cards prioritized. You do not need to save each title, click Find artwork, sign into a cloud account or supply TMDB/IGDB keys for the built-in public sources.

The previous loader missed directory cards and several legacy views, and the image validator rejected some valid cover hosts. A shared adapter now supplies every media renderer, source credits and protected custom choices. A separate cover setting defaults on; the older saved-item metadata backfill setting no longer blocks page covers.

Sources include verified Wikipedia work images and TVmaze, with configured existing providers as additional coverage. These are matched existing cover/poster images, not generated illustrations. A source may have no suitable image, a blocked network request or an ambiguous title. Those cards explain their status; the app does not silently substitute an unrelated work. Book art may be a historical first-edition title page, not the cover of your particular edition.

## Guides and evidence

- docs/START_HERE_18.6.1.md — upgrade, settings and troubleshooting
- docs/QA_REPORT_18.6.1.md — exact executed checks and limitations
- docs/RELEASE_REPORT_18.6.1.md — root causes, implementation and source/privacy details
- docs/evidence/18.6.1/ — browser captures and machine-readable results
- BUILD_MANIFEST.json — per-file SHA-256 hashes in the release

Earlier release documents remain historical. Their statements that basic movie/game artwork requires keys or saving each directory item are superseded by this release. The older account/provider setup guides still apply to optional richer metadata and private cloud sync.

## Development

Branch development/18.6.1-automatic-artwork, based on the verified 18.6 source. Plain JavaScript/CSS and the Node built-in server; no new runtime package. This release includes source, tests and reports. Git history remains in the development checkout and is not needed to run the ZIP.

Run npm ci for pinned development tools, npm run check for syntax/assets/vendor integrity, npm run format:check for maintained modules, npm test for Node/book checks, and npm run test:browser for the full regression suite. Set ROWANVALE_BROWSER to installed Chrome or install Playwright Chromium. npm run test:live-covers separately exercises genuine public services and image downloads; network availability can affect it. npm run catalog:audit audits bundled title structure; npm run build creates the distribution.

There is no TypeScript/ESLint pipeline. No account secrets, personal workspace, node_modules or private cover cache is included.

