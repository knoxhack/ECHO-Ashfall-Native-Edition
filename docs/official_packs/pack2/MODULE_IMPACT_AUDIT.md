# Pack #2 Module Impact Audit

Rule: if a change benefits all packs, add it to the reusable module. If it is Pack #2-specific, keep it in the Pack #2 profile/content.

| Module | Used By Pack #2 | Generic Feature Needed | Pack-Specific Content Only | Isolation Safe | API Hooks Needed | New Assets Needed |
| --- | --- | --- | --- | --- | --- | --- |
| `echocore` | Yes | Possible profile metadata helpers later | No | Yes | Maybe profile registry helpers | No |
| `echonetcore` | Yes | No | No | Yes | No | No |
| `echoterminal` | Yes | Generic factory dashboard provider may help multiple packs | Foundry dashboard copy and ids | Yes | Maybe data-provider hook | Later UI art |
| `echoindex` | Yes | Generic machine troubleshooting category may help all tech packs | Foundry manuals and production entries | Yes | No | No |
| `echomissioncore` | Yes | No | Commissioning mission text | Yes | No | No |
| `echoscriptcore` | Optional tooling | Generic authoring docs may help | No | Yes | No | No |
| `echocreatorcore` | Optional tooling | Template authoring preview may help | No | Yes | No | No |
| `echodatacore` | Optional | Facility/team state could be generic | Pack #2 facility flags | Yes | Maybe team progress hooks | No |
| `echomultiblockcore` | Yes | Generic workcell status summaries | Foundry workcell plans | Yes | Maybe status provider | Later block visuals |
| `echoruntimeguard` | Yes | Factory scaling budget presets could help all automation packs | Foundry budget checklist | Yes | No | No |
| `signalos` | Optional | No | Optional operator terminal bridge | Yes | No | No |
| `signalosexample` | No | No | No | Yes | No | No |
| `echorendercore` | Optional | No | Future showcase renders only | Yes | No | Later preview art |
| `echothemecore` | Yes | No | Industrial theme token selection | Yes | No | Later pack branding |
| `echoscreencore` | Optional | Generic factory UI components later | No | Yes | Maybe UI page hooks | Later UI art |
| `echowiki` | Optional | No | Pack reference pages | Yes | No | No |
| `echotextureforge` | Tooling only | No | Visual QA prompts only | Yes | No | No |
| `echoholomap` | Yes | Facility-floor layer type could be generic | Foundry floor markers | Yes | Maybe layer metadata | Later map icons |
| `echolens` | Yes | Generic blocker scan summaries | Foundry substation and processor scans | Yes | Maybe scan profile ids | No |
| `echoorbitalremnants` | No | No | No | Yes | No | No |
| `echonexusprotocol` | No | No | No | Yes | No | No |
| `echoagriculturereclamation` | No | No | No | Yes | No | No |
| `echoworldcore` | Yes | Indoor/facility region descriptors may help | Foundry facility zones | Yes | Maybe region type docs | No |
| `echoblockworks` | Optional | No | Facility palette notes | Yes | No | Later block palette screenshots |
| `echoplayercore` | Optional | No | Server utility presets | Yes | No | No |
| `echopowergrid` | Yes | Generic commissioning diagnostics may help all tech packs | Foundry opening power spine | Yes | Maybe diagnostics provider | No |
| `echosoundcore` | Optional | No | Factory ambience and warning cues | Yes | No | Later OGG files |
| `echotutorialcore` | Yes | No | Foundry onboarding hints | Yes | No | No |
| `echorelictech` | No | No | No | Yes | No | No |
| `echoweathercore` | No | No | No | Yes | No | No |
| `echorecovery` | Optional | No | Server recovery notes | Yes | No | No |
| `echonpcore` | Optional future | Generic facility operator profiles may help | Foundry operators | Yes | Maybe profile examples | Later NPC visuals |
| `echoarmory` | No | No | No | Yes | No | No |
| `echoblackboxprotocol` | No | No | No | Yes | No | No |
| `echoconvoyprotocol` | Optional later | Generic freight bridge may help | Future freight expansion | Yes | Maybe route bridge | Later vehicle screenshots |
| `echoindustrialnexus` | Yes | Generic factory commissioning hooks may help all factory packs | Foundry production orders | Yes | Maybe commissioning API | Later machine showcase art |
| `echologisticsnetwork` | Yes | Generic depot status summaries may help | Foundry depot requests | Yes | Maybe endpoint summary hook | Later depot visuals |
| `echostationfall` | No | No | No | Yes | No | No |

## Audit Decision

Pack #2 can start as profile/template content without depending on other official pack content. Any reusable API hook must be proposed separately after the MVP proves the need.
