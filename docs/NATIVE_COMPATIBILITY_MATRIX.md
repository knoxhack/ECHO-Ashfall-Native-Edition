# Native Compatibility Matrix

| Runtime | Module artifact | Status |
| --- | --- | --- |
| ECHO Native Platform | `<module>-<version>.echo-addon` | Supported for Native Edition packs. |
| Minecraft/NeoForge bridge | `<module>-<version>-neoforge.jar` | Supported by NeoForge Edition, not loaded directly by Native Edition. |
| ECHO Standalone Runtime | `<module>-<version>-standalone.jar` | Supported by Standalone Edition, not loaded directly by Native Edition. |

Native Edition should use `.echo-addon` packages and avoid installing NeoForge or standalone module jars into the native module folder.
