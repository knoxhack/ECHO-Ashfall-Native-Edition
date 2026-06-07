# Ashfall UX Contract Freeze

This freezes the minimum player-facing UX for Agent 5 work. A feature is not shippable until it gives the player a visible objective, readable feedback, a player-facing explanation, and complete resource surfaces for the way the player meets that feature.

## Minimum Contract

- Visible objective: mission objective, HUD line, Terminal row, scan result, or HoloMap marker tells the player the next action.
- Readable feedback: completion, blocked, warning, and reward states use player language, not internal event names.
- Player-facing explanation: Terminal, Wiki, Codex/Index, Lens, HoloMap, tooltip, or screen copy explains why the feature matters.
- Asset completeness: lang, icons, models, textures, blockstates, item definitions, recipes, loot tables, schemas, and Terminal mission art are valid where applicable.
- No debug placeholders: no player-facing text may look like debug, TODO, placeholder, or null output.

## Feature Coverage

| Feature | Required UX Surfaces |
| --- | --- |
| First spawn | Welcome screen, starter HUD/chat, starter note, first-month Terminal page, Wiki first steps, Index starter entries, Lens profile, HoloMap layer |
| Water | Water missions, water item names/tooltips, rain collector and purifier recipes/loot, Terminal/Index/Wiki explanations |
| Shelter | Welcome card, starter note, shelter/base objectives, safe-route HoloMap context, first-steps Wiki |
| Primitive tools | Scrap knife mission, tooltip, recipe/model/lang surfaces, starter note |
| Starter machines | Rain collector, hand recycler, field kit, schematics, mission art, recipes, loot, Terminal/Index support |
| Machine/power/logistics | Block/item models, textures, recipes, loot, lang, UI panels, HUD readouts, Terminal help, Codex/Index entries |
| Scanner/factions | Scanner UI, Lens profiles, HoloMap POIs, faction Terminal pages, drone HUD, cache loot, faction rewards |
| Midgame survival | Hazard readouts, mutation status, med bay UI, lab/vault Terminal pages, data logs, radiation/atmosphere documentation |
| Late game | Boss intel, Nexus UI, Prime relay pages, ending branch presentation, late-game Codex/Index and HoloMap state |

## Validation

Run the focused audit before handing off Agent 5 work:

```bash
python tools/validate_ashfall_ux_assets.py --json
```

The broader resource audit remains the release gate:

```bash
python tools/validate_resources.py --addon-set all
```
