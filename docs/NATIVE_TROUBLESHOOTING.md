# Native Troubleshooting

## Descriptor Validation

If the runtime reports `NativeAddonDescriptorValidationException`, inspect the module's embedded `META-INF/echo.mod.json` and confirm `id`, `name`, `version`, runtime targets, and required dependencies are present.

## Module Install Failures

Confirm the pack manifest declares `moduleArtifactFamily: "echo-addon"` and that each `moduleRequirements` entry resolves to `<module>-<version>.echo-addon` in `knoxhack/ECHO-Modules`.

## Crash Reports

Use [Crash Report Guide](CRASH_REPORT_GUIDE.md) and include the pack manifest, module list, launcher log, runtime log, and the failing descriptor.
