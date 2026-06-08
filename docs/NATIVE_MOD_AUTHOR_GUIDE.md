# Native Mod Author Guide

Native modules are packaged as `.echo-addon` artifacts with an embedded `META-INF/echo.mod.json` descriptor and `echo-addon-package.json` package metadata.

## Required Files

- `META-INF/echo.mod.json`
- `echo-addon-package.json`
- Runtime payload files declared by the package metadata

## Release

Publish native module artifacts from `knoxhack/ECHO-Modules` and pin them through Native Edition `moduleRequirements`.
