# Rowanvale Beta 19.3 — More of Your World

> **BETA / PRE-RELEASE — 19.3.0.** This build is for testing and feedback, not a stable release.

A more personal, organized and useful local home for games, films, television, anime and books. Built on 18.6.2, preserving its repairs, profiles, artwork, directories and saved data.

## New in Beta 19.3

- **Trust repairs:** journals save to the right records; history no longer silently loses older entries; Repeat selects the session displayed; search opens the correct saved title.
- **Reviewed imports:** local Rowanvale JSON and Goodreads/Letterboxd/generic CSV, conservative duplicate review, edition-aware matching, preserved paused/dropped statuses, and undo for unchanged imported records.
- **Movement:** recoverable structured workouts with sets, reps, weights, kg/lb, prior values, routines and an optional rest timer. Food entries can be corrected; unknown nutrients remain unknown.
- **Wellbeing:** searchable private history, date/type filters, edits, deletion/undo and selected export. Custom Quiet Room durations and recoverable paused sessions.
- **Media:** dated diaries, episode/season history and rewatches, book editions/copies/rereads. Group plans record guest access and setup needs.

See [Beta 19.3 verification and limits](docs/QA_BETA_193.md), [movement guide](docs/TRAINING_193.md), and [import guide](docs/IMPORT_193.md).

## Retained from Beta 19.0

- **Workspace presets:** coordinated Quiet focus, Play & discover and Evening unwind setups; save up to 12 of your own. Compare saved versus draft appearance before committing. Share validated visual/layout preferences without identity, uploaded media or private records.
- **Smart Shelves:** save up to 20 named searches with format, status and sort. Matching titles join automatically as your library changes. Rename/remove a shelf without deleting stories.
- **Library views:** cover grid, detailed list and compact list, remembered across visits and included in backups. Planned games stay on For later after reload.
- **Night planning:** review a vote-based lineup that fits known durations and breaks; No votes are excluded and missing votes remain visible. Accept explicitly, then export a calendar file without guest identities or individual ballots.
- **Data Health:** inspect real saved-workspace readability, browser storage estimates, active-worker offline cache verification, and clearly labeled backup-download records.

Every feature above works locally. First-time external artwork/metadata and optional cloud services still require a network. Night plans remain local/manual sharing; this is not hosted friend accounts or synchronized streaming.

## Launch or upgrade

1. Export a JSON backup from the old app; optionally export artwork too.
2. Stop the previous server and retain its folder.
3. Extract the full ZIP and run **START_ROWANVALE_WINDOWS.bat**. Node.js is required; no npm install is needed to run Rowanvale.
4. Use the same browser profile at **http://localhost:8080/api/launch**. Confirm **19.3.0 / Beta**.

Do not open index.html directly or clear browser storage. Moving browsers/computers requires importing your backup. The old release is preserved for rollback.

## Guides

- [What changed, what is still missing, and the next priorities](docs/BETA_19_PRODUCT_DIRECTION.md)
- [Verification and limitations](docs/QA_BETA_19.md)
- [Smart Shelves and library views](docs/LIBRARY_19.md)
- [Data Health semantics and performance observations](docs/DATA_HEALTH_19.md)
- `docs/evidence/19.3.0/` contains actual browser captures and machine-readable results.
- `BUILD_MANIFEST.json` in the release lists per-file SHA-256 checksums.

Older reports describe their own releases. No claim is made that every legacy control, device or external integration is certified.

## Development

Plain JavaScript/CSS, local Node server, no new runtime dependency. `npm ci` installs pinned development tools. `npm run check`, `npm run test:browser`, `npm run format:check`, `npm run catalog:audit`, and `npm run build` validate and package the app. Set ROWANVALE_BROWSER to Chrome or install Playwright Chromium for browser tests. Tests use synthetic workspaces and temporary server data, never your real browser profile.
