# Ashfall Official Pack Changelog 1.7.1

Ashfall 1.7.1 is a post-1.7.0 stabilization and player-experience patch for Official ECHO Pack #1.

## Fixed

- Corrected Terminal ScreenCore documentation so experimental tabs are described as opt-in, matching the client defaults.
- Retargeted Ashfall official pack, profile, template, preset, Launcher card, and generated example metadata to 1.7.1.
- Regenerated the Full Ashfall example pack from the Ashfall official template after the metadata sync.
- Removed null biome registration placeholders for data-driven Ashfall biomes so they do not freeze as unbound registry holders during host QA.
- Fixed the Agent 7 Phase 3 host-smoke fixture so `expedition_readiness` uses the canonical two-water and two-bandage requirements.
- Updated the gameplay-data validation gate to track Ashfall save migration version 4, including deprecated MissionCore alias migration.
- Guarded ThemeCore loading-overlay text until the initial client resource reload is complete, preventing the startup `minecraft:pipeline/gui_text` shader crash seen during Agent 7 real-client launch smoke.

## Improved

- Added 1.7.1 dev QA, triage, first-hour, smoke-test, and next-step documentation.
- Expanded known issues so remaining manual smoke and visual-review work stays visible.
- Unparked the registered Agent 7 complete host-smoke GameTests and validated the clean-root `ashfall_*_host_smoke` wildcard run with all eight required host smokes passing.
- Added Agent 7 semi-automated restore, destroy, and control full-playthrough host smokes that validate live first-spawn through each ending epilogue with MissionCore relog round-trips at major route checkpoints.
- Added an Agent 7 checkpoint relog host smoke that saves connected player data, reloads through the vanilla saved-data path, and verifies MissionCore plus restore epilogue state across major route checkpoints.
- Re-ran gameplay-data validation as a static first-hour recipe/source/loot baseline for Agent 7 balance QA.
- Ran focused Agent 7 balance/friction host probes for route/faction balance contracts, hazard and shelter recovery, RadAway use, and substrate grinder recipes.
- Recorded the real-client launch smoke reaching post-resource-load/title-idle evidence after the loading-overlay shader fix; fresh world creation and live route feel remain open Agent 7 work.

## Not Changed

- No new addons were added.
- No new major Ashfall systems or content waves were added.
- ScreenCore Terminal experimental tabs remain gated.
- Reusable ECHO modules remain standalone and are not made Ashfall-only.
