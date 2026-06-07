# Ashfall Creator Breakdown

Ashfall is Official ECHO Pack #1 and demonstrates the official-pack pattern for ECHO creators.

## Module Usage

Ashfall uses `echoashfallprotocol` for official pack content and registers into reusable ECHO modules such as Terminal, Index, MissionCore, HoloMap, WeatherCore, SoundCore, Lens, WorldCore, PowerGrid, Armory, Logistics, Convoy, Orbital Remnants, Stationfall, Nexus Protocol, and Blackbox Protocol when those modules are present.

## Isolation Pattern

Ashfall-specific content belongs under the Ashfall profile and `echoashfallprotocol` namespace. Generic ECHO modules should remain reusable and should not hardcode Ashfall content, ECHO-7 strings, Prime Relay language, or Ashfall Nexus progression.

## Creator Pattern

Creators can follow the same pattern without becoming official packs:

1. Select reusable ECHO modules.
2. Add custom Index, MissionCore, HoloMap, ThemeCore, WeatherCore, WorldCore, SoundCore, and Lens content through datapacks/configs.
3. Keep pack-specific story/content in the pack namespace.
4. Validate with the creator tools before publishing.
