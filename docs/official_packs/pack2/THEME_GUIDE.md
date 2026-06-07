# Pack #2 Theme Guide

Status: 1.0.0 internal MVP draft.

Theme id: `pack2_theme`

The Pack #2 theme is a Foundry Protocol draft. It must not replace another official pack theme and must not become the default ECHO theme.

## ThemeCore Token Map

Required tokens:

| Token | Value | Use |
| --- | --- | --- |
| `surface.background` | `#0b1114` | Deep factory background. |
| `surface.panel` | `#172126` | Primary dashboard panels. |
| `text.primary` | `#e9f6f2` | Main text. |
| `text.muted` | `#8da4a9` | Secondary labels and telemetry. |
| `state.success` | `#56d68a` | Throughput ready and route clear. |
| `state.warning` | `#f0a24a` | Caution, incomplete power, missing route. |
| `state.error` | `#ff5d6c` | Fault, blocked machine, unsafe route. |
| `focus.primary` | `#58d7ff` | Active scan and keyboard focus. |
| `accent.primary` | `#5bd6ff` | Foundry instrumentation accent. |

Optional tokens should include raised panels, row hover states, selected rows, map route lines, and fault borders.

## Terminal Style Notes

- Compact dashboard metadata for the live MissionCore route, What Now panel, starter mission panel, PowerGrid status, Tutorial guide, Lens, and HoloMap support.
- Use cyan focus for active diagnostics, amber for incomplete setup, green for cleared routes, and red only for blocking faults.
- Do not use labels, hazards, or profile copy from another official pack.

## Index Style Notes

- Index entries should read like operational manuals and commissioning notes.
- Prefer short procedure summaries over lore-heavy survival journals.
- Use diagrams and screenshots later; this MVP keeps starter guidance text-only.

## HoloMap Style Notes

- Map layers should show factory floor zones, power routes, processor lines, and depot paths.
- Icons should be simple industrial glyphs with strong silhouette readability.
- HoloMap colors should mirror the ThemeCore state colors.

## MissionCore Status Colors

- Draft or planned: muted text.
- Active route: cyan.
- Ready or cleared: green.
- Needs setup: amber.
- Blocked: red.

## Tutorial Card Style

- Tutorial cards should be concise operational prompts.
- Each card should point to exactly one next action.
- Avoid survival-warning language unless a future mechanic explicitly requires it.

## SoundCore UI Sound Notes

- Ambient bed: low factory room tone.
- Positive stinger: short relay confirmation.
- Warning stinger: soft caution pulse.
- Error stinger: clipped fault chirp.
- Avoid horror swells, wind beds, or survival-wasteland environmental distress.

## Icon Requirements

- Pack icon.
- Launcher card icon.
- Power spine icon.
- Processor route icon.
- Depot request icon.
- Runtime budget icon.
- Lens scan icon.
- HoloMap route marker.

## Logo Prompt

Create a clean industrial sci-fi logo for "ECHO: Foundry Protocol", dark factory panels, cyan instrumentation, amber caution accents, compact technical silhouette, no readable small text except the title, no watermark.

## Banner Prompt

Create a wide launcher banner for "ECHO: Foundry Protocol", dormant factory floor, power conduits, diagnostic panels, cyan and amber lighting, precise industrial mood, no wasteland imagery, no watermark.
