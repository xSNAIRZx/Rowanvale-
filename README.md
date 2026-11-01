# Rowanvale 18.6.2 — Everyday Polish

> **PRE-RELEASE / release candidate.** For testing and feedback. This is not a stable release.

A reliability and usability pass on the latest Rowanvale: calmer effects, mobile Settings that stay usable while scrolling, clearer games/media shelves, correct movie-night guest voting, safer cross-tab saves and recoverable Quiet Room sessions. Existing artwork, profiles, local directories and data formats are preserved.

## Start or upgrade

1. In the previous app, export a JSON backup from Backups & Data; optionally export artwork too.
2. Stop the previous Rowanvale server. Keep its folder as a rollback copy.
3. Extract the entire new ZIP and double-click `START_ROWANVALE_WINDOWS.bat`. Node.js is required; no dependency installation is needed to use the app.
4. Use the same browser profile and `http://localhost:8080/api/launch`. Confirm **18.6.2**. Saved browser data remains associated with this address.

Do not open index.html directly or clear browser storage to upgrade. If moving computers or browser profiles, import your exported backup. Local guest labels and shared night plans do not become hosted accounts; hosted social remains a separate future feature.

## What's improved

- Calm View suppresses the newer atmosphere effects and is available in Comfort settings.
- Mobile Edit settings / Show preview tabs stay below the header.
- Games & Media and Books Directory can be chosen as the starting page.
- Current stories, future plans and favorites have count-bearing shelf shortcuts; paused items have a precise filter. Empty searches offer Clear filters.
- Editing a movie-night lineup or duration preserves the selected voting guest.
- Failed saves cannot roll back to a stale copy from before another tab's changes.
- Artwork backup export catches damaged image files before offering an archive that cannot be restored.
- Quiet Room remembers the selected duration and paused/completed state. A completed session that cannot save offers Retry saving session, including after reload in the same tab.
- Downloaded issue reports identify the running version correctly.

## Evidence and source

- [Audit, fixes, QA and remaining risks](docs/AUDIT_AND_QA_18.6.2.md)
- [Media product research](docs/MEDIA_POLISH_AUDIT.md)
- `docs/evidence/18.6.2/` — current full regression results
- `docs/evidence/audit-controls/` and `docs/evidence/audit-polish/` — targeted checks, control inventory and genuine before/after screenshots
- `BUILD_MANIFEST.json` — release file checksums

Earlier version reports are historical. An inventory of buttons is not proof every possible state or external integration has passed.

## Development

Plain JavaScript/CSS and a local Node server, with no new runtime dependencies. `npm ci` installs pinned development tools. Run `npm run check`, `npm test`, `npm run test:browser`, `npm run format:check`, and `npm run catalog:audit`. Browser checks use isolated temporary data; set `ROWANVALE_BROWSER` to Chrome or install Playwright Chromium. `npm run build` creates the distribution; `npm run test:live-covers` separately exercises public providers.

No personal workspace, account secrets, node_modules or private artwork cache is bundled.
