# ECHO Native Known Limitations

## RC 1.0.0 Limitations

This is a release-candidate build. The following limitations are expected and documented. Do not report them as unknown bugs.

### Runtime Lanes

- **Standalone lane** is validated for core services only. Complex addons with deep NeoForge registries may require `NEOFORGE_BRIDGE` or `NATIVE` lanes.
- `STANDALONE` does not support custom `Capability` implementations; use `EchoBackendEnergyBridge` and `EchoBackendFluidBridge` for portable handlers.

### Module Coverage

- Not every existing ECHO addon has been ported to the Native SDK. See the [Module Release Matrix](../reports/echo/native/plan3/plan3-module-release-matrix.md) for per-module status.
- Addons marked `blocked` in the matrix may still function under `NEOFORGE_BRIDGE` but are not yet validated under `NATIVE`.

### NeoForge Feature Gaps

- Direct addon runtime imports from NeoForge classpath are unsupported. Use descriptor `optionalIntegrations` and service lookups.
- Dev classpath fallback (loading classes from `build/classes` directly) is unsupported. Always package as jars for Native lane testing.
- Metadata-only mutation claims (declaring a mutation without an implementation) are rejected during validation.

### OS Support

- **Windows desktop** is the verified local lane.
- **Linux** and **macOS** are supported in principle but require CI evidence before public support claims. Run the testkit on your target OS and report results.

### SDK

- `echo-sdk-gradle-plugin` currently supports Gradle 8.5+. Newer Gradle versions may require a plugin update.
- Javadoc generation for `echo-native-contracts` is present but incomplete for experimental packages.

### Tooling

- The in-game `/echo export-diagnostics` command is present; remote telemetry is not enabled in RC builds.
- Visual parity reports (`rendercore` board checks) require manual review and cannot be fully automated.

### Compatibility

- ECHO Native addons are not Fabric mods. Do not attempt to load them on Fabric.
- NeoForge mods that do not use ECHO services will load normally alongside ECHO Native, but they will not participate in ECHO service discovery.

## Upcoming Work

- Full Linux/macOS CI verification.
- Standalone lane coverage for remaining core addons.
- GA API freeze and binary compatibility baseline.

See [Compatibility Matrix](NATIVE_COMPATIBILITY_MATRIX.md) for version mapping.
