# Ashfall Screenshot Requirements

Ashfall Native cannot clear Phase 9 player-facing polish until the Launcher
gallery uses real gameplay captures instead of icon, banner, pack card, or
showcase art.

## Required Captures

Capture these from the release candidate build that will be published:

- `first_launch.png`: first real client launch into Ashfall, after the player
  reaches the playable first-hour world. The frame should show the Ashfall HUD
  or first route context and must not be a generated promotional image.
- `server_export.png`: server/client export smoke proof. The frame should show
  either the exported server/client package surface or a client joined to the
  freshly exported server with Ashfall running.
- `route_verification.png`: opening route proof with Terminal, Index, Lens,
  HoloMap, or MissionCore context visible.
- `ending_verification.png`: late-route or ending proof from the same release
  candidate line.

Store final captures under `metadata/assets/official_packs/ashfall/` and list
only those screenshot-style assets in `metadata/official_packs/ashfall.json`
`screenshots`. Keep `icon.png`, `banner.png`, `pack_card.png`, and
`showcase.png` in their dedicated metadata fields, not in the screenshot gallery.

## Release Gate

The Release Index Phase 9 readiness gate requires:

- `screenshotsNeeded` is empty.
- `screenshots` has at least four existing files.
- One screenshot path matches first-launch or first-hour evidence.
- One screenshot path matches server/client export evidence.
- `icon.png`, `banner.png`, `pack_card.png`, and `showcase.png` are absent from
  the `screenshots` list.
