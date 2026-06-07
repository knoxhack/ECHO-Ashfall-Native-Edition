# Pack #2 First 30 Minutes

## Player Flow

1. Player starts in the internal Pack #2 prototype.
2. Player receives/open first guidance through the Pack #2 welcome Index entry or Terminal mission route.
3. Player opens Index or Terminal and sees the starter route: Foundry Orientation, First Tool Check, Mark the Processor Worksite, Read the First Meter, Shift Handoff.
4. Player completes Foundry Orientation by using Lens Deep Scan on any block.
5. Player claims the starter grid kit: `echopowergrid:hand_crank_generator`, `echopowergrid:small_battery_bank`, `echopowergrid:low_voltage_cable`, and `echopowergrid:grid_diagnostic_tool`.
6. Player places the hand crank generator, low voltage cable, and small battery bank, then Deep Scans the small battery bank.
7. Player uses HoloMap to create one waypoint for the processor worksite.
8. Player claims the Power Meter, places it, and Deep Scans it.
9. Player claims the Power Cell and Insulated Wire reward, then Deep Scans the hand crank generator.
10. Player receives the Scrap Processor Blueprint and sees the next objective: prepare the processor route in the next internal phase.

## Mission Chain

- `echo_template_pack2_draft:foundry_commissioning_draft`: Foundry Orientation. Deep Scan any block through `echolens:mission/verified_deep_scan/scan`. Reward: starter grid kit.
- `echo_template_pack2_draft:restore_power_spine`: First Tool Check. Deep Scan `echopowergrid:small_battery_bank`. Reward: scrap wire and fuse.
- `echo_template_pack2_draft:route_processor_line`: Mark the Processor Worksite. Create a waypoint through `echoholomap:mission/create_waypoint/waypoint`. Reward: power meter.
- `echo_template_pack2_draft:calibrate_depot_requests`: Read the First Meter. Deep Scan `echopowergrid:power_meter`. Reward: power cell and insulated wire.
- `echo_template_pack2_draft:runtime_budget_review`: Shift Handoff. Deep Scan `echopowergrid:hand_crank_generator`. Reward: `echoindustrialnexus:scrap_processor_blueprint` and next-phase guidance.

## Module Surfaces

- MissionCore drives objective state, reward state, and the live Terminal route.
- Index provides five starter pages: welcome, core mechanic, first objective, first reward, and troubleshooting/what now.
- Terminal uses existing MissionCore, PowerGrid, and TutorialCore surfaces. `foundry_dashboard.json` is dashboard metadata, not a new Terminal layout system.
- TutorialCore provides the Foundry Orientation card, starter hints, and mission-completion flow steps.
- Lens Deep Scan records both the existing Lens mission target and the actual scanned block id.
- HoloMap completes the waypoint mission through player waypoint support. Pack #2 layer JSON supplies metadata labels only.
- SoundCore uses a valid ambience profile and generic mission completion stingers.
- WorldCore metadata labels the Foundry Floor and starter power-bus hazard without adding worldgen or custom hazard behavior.

## MVP Boundary

The first 30 minutes stop after the Scrap Processor Blueprint and next objective. Full factory balance, recipes, structures, public launcher visibility, final art, and broader pack progression remain out of scope.
