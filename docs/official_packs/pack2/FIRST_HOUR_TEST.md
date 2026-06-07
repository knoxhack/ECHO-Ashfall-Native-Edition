# Pack #2 First Hour Test

Version: ECHO Ecosystem 1.0.0  
Pack: ECHO: Foundry Protocol  
Status: release-candidate prototype test script

## Purpose

This test validates the first hour of the locked Pack #2 prototype without adding new content. It is a manual QA script for maintainers and approved creators.

## Test Matrix

| Beat | Expected Result | Current RC Status | Notes |
| --- | --- | --- | --- |
| First launch | Pack loads as Official Pack #2 draft/internal RC metadata, not as public beta. | Ready for validation | Public launcher flags must remain false. |
| First instructions | Terminal dashboard shows internal preview/RC status, Next Objective, and What Now. | Implemented | Fallback Index overview exists if Terminal is unavailable. |
| First mission | `echo_template_pack2_draft:foundry_commissioning_draft` starts Foundry Orientation. | Implemented | Structured objectives are used. |
| First system interaction | Player performs one Lens Deep Scan and reads the next objective. | Implemented as profile/data route | Lens absence should warn, not imply public readiness. |
| First reward | Starter PowerGrid kit rewards are listed for generator, battery, cable, and diagnostic tool. | Implemented as MissionCore rewards | Balance is not final. |
| First map usage | HoloMap points at the Foundry Terminal and later route markers when installed. | Implemented as optional data links | HoloMap absence should fall back to Terminal/Index guidance. |
| First scan/docs usage | Lens scan links to Index entries and mission objectives. | Implemented | Pack #2 profile validator checks references. |
| First failure state | Missing Lens, missing HoloMap, placeholder visuals, or stuck objective has known issue text. | Documented | Severe runtime failures should block creator preview. |
| First exit/save/reload | Player exits after starter objective, reloads, and confirms MissionCore route and profile metadata still resolve. | Manual QA required | No Pack-specific DataCore persistence is required yet. |

## First Hour Script

1. Launch the Pack #2 RC profile through internal launcher preview tooling.
2. Confirm the launcher card says release candidate or internal preview and that install/play buttons are disabled or preview-only.
3. Open the Foundry Terminal dashboard.
4. Confirm internal preview status, Next Objective, What Now, Mission Panel, Archive Docs, Map Objective, Lens Scan Status, and Warning State are present.
5. Start Foundry Orientation.
6. Complete one Lens Deep Scan.
7. Confirm Index unlock guidance points to Foundry Protocol Preview Brief and Grid Commissioning.
8. Claim the starter PowerGrid kit.
9. Place or inspect the starter generator, battery, cable, or diagnostic tool where available.
10. Open HoloMap if installed and confirm the next-objective marker exists.
11. Trigger or simulate a failure state by checking behavior without optional HoloMap/Lens expectations.
12. Exit the session, reload, and confirm the route and docs still resolve.

## Pass Criteria

- The player always has a clear next step.
- Missing optional modules produce warning/fallback text, not a public-release claim.
- Mission, Index, Lens, Terminal, and HoloMap ids validate.
- Exit/save/reload does not require Pack-specific DataCore persistence.
- The run still communicates that Pack #2 is not public beta.

## Fail Criteria

- Public release flags are enabled.
- First mission uses broken or legacy objective data.
- Launcher card implies public availability.
- Terminal or Index gives no fallback path.
- Pack #2 references Ashfall-only content.
- Validation fails after the test data is updated.

