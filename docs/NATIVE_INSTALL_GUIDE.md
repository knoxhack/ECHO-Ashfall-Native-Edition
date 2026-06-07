# ECHO Native Install Guide

## Prerequisites

| Component | Required Version | Notes |
|---|---|---|
| Java | 25 | ECHO Native targets the Java 25 runtime. |
| Minecraft | 26.1.2 | Base runtime version. |
| NeoForge | 26.1.2.29-beta | Compatibility backend for NeoForge lane. |
| ECHO Native Loader | 1.0.0-RC | The loader itself. |

## Client Installation

1. Install a Java 25-compatible launcher (Prism Launcher, ATLauncher, or manual).
2. Download the ECHO Native Loader and required core modules:
   - `echo-native-loader-1.0.0-RC.jar`
   - `echocore-1.0.0.jar`
   - `echonetcore-1.0.0.jar`
3. Place core modules in your `mods/` folder.
4. Add any desired optional addons.
5. Launch and verify the ECHO Native bootstrap message appears in `latest.log`.

## Server Installation

1. Install NeoForge server for `26.1.2.29-beta`.
2. Add the ECHO Native Loader and core jars to the server `mods/` folder.
3. Start the server once to generate `config/echo/` and `echo/addons/` paths.
4. Review `config/echo/echocore.toml` for budget defaults and service toggles.
5. Restart after config changes.

## Verifying Installation

Check `logs/latest.log` for:

```
[ECHONativeBootstrap] Loader v1.0.0-RC initialized
[ECHONativeBootstrap] Discovered 3 native addons, 2 neoforge-bridge addons
[EchoCoreServices] Registry online
```

If you see `NativeAddonDescriptorValidationException`, one addon is missing a required field in its descriptor. See [Troubleshooting](NATIVE_TROUBLESHOOTING.md).

## Upgrading

1. Back up worlds, configs, and `echo/` state. See [Rollback Guide](NATIVE_ROLLBACK_GUIDE.md).
2. Replace loader and module jars with the new RC versions.
3. Do not mix RC loader jars with pre-RC addon descriptors.
4. Start and review the parity report if available.
