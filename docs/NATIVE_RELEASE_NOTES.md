# ECHO Native 0.1.0 Public Beta — Release Notes

**Tag:** `v0.1.0-native-public-beta`  
**Date:** 2026-06-07  
**Minecraft:** 26.1.2  
**NeoForge Backend:** 26.1.2.29-beta  
**Java:** 25  

## What Is Included

- **ECHO Native Loader** — policy-driven addon loader supporting `NATIVE`, `NEOFORGE_BRIDGE`, and `STANDALONE` lanes.
- **SDK** — `echoaddonapi`, `echo-native-contracts`, `echo-sdk-gradle-plugin`, `echo-native-testkit`.
- **Core modules** — `echocore`, `echonetcore`, `echoadaptercore` validated across all three lanes.
- **100+ addon modules** — most are `ready` for `NATIVE` and `NEOFORGE_BRIDGE`; see compatibility matrix for per-module status.
- **Public docs** — install guide, mod author guide, porting guide, API reference, troubleshooting, known limitations, compatibility matrix, rollback guide, release packaging guide.
- **Templates and examples** — 2 templates + 7 example addons (registry, event, packet, config, screen/HUD, worldgen, testkit).
- **SBOM, checksums, license notices** — full compliance artifact set.

## What Is Not Included

- Standalone lane coverage for complex addons (core services only).
- Full Javadoc for experimental packages.
- Linux/macOS CI-verified support (community evidence welcome).
- Fabric mod loader support.

## Supported Platforms

| Platform | Status |
|---|---|
| Windows 10/11 desktop | Verified |
| Linux server/desktop | Supported with evidence |
| macOS | Supported with evidence |

## Install Steps

1. Install Java 25.
2. Download the ECHO Native Loader and core modules.
3. Place in `mods/` alongside NeoForge 26.1.2.29-beta.
4. Add optional addons.
5. Launch and verify bootstrap message in `latest.log`.

See [NATIVE_INSTALL_GUIDE.md](NATIVE_INSTALL_GUIDE.md) for full details.

## Mod Author Steps

1. Apply `echo-sdk-gradle-plugin`.
2. Write `echo-native-addon.descriptor.json`.
3. Implement `EchoNativeAddon` entry point.
4. Use `EchoCoreServices` for registries and optional integrations.
5. Validate with `./gradlew validateAddon`.
6. Package with `./gradlew packageAddon`.

See [NATIVE_MOD_AUTHOR_GUIDE.md](NATIVE_MOD_AUTHOR_GUIDE.md) and [templates](../templates/).

## Migration Status

Most addons are ready for `NATIVE` or `NEOFORGE_BRIDGE`. A subset is `blocked` due to `local_build_output_classpath_fallback` — these will be unblocked in 0.1.1. See [NATIVE_COMPATIBILITY_MATRIX.md](NATIVE_COMPATIBILITY_MATRIX.md).

## Known Limitations

- Standalone lane is core-services-only.
- Windows is the only verified OS lane.
- `echo-sdk-gradle-plugin` requires Gradle 8.5+.
- Some addons remain blocked for Native lane (see matrix).

See [NATIVE_KNOWN_LIMITATIONS.md](NATIVE_KNOWN_LIMITATIONS.md).

## Rollback Instructions

Back up worlds/configs, stop the runtime, replace jars with previous versions, restore configs if needed. See [NATIVE_ROLLBACK_GUIDE.md](NATIVE_ROLLBACK_GUIDE.md).

## Where to Report Bugs

- Bug reports: [Bug Report](../.github/ISSUE_TEMPLATE/bug_report.md)
- Crash reports: [Crash Report](../.github/ISSUE_TEMPLATE/crash_report.md)
- Addon author help: [Addon Author Support](../.github/ISSUE_TEMPLATE/addon_author_support.md)
- Security: Follow [Security Report](../.github/ISSUE_TEMPLATE/security_report.md) instructions (email `security@echo.dev` for undisclosed issues).

## Changelog

### 0.1.0-native-public-beta

- Initial public beta release.
- Native Loader with three runtime lanes.
- SDK public surface freeze (Beta annotated).
- 100+ module migration status published.
- Full docs, templates, and support infrastructure.
