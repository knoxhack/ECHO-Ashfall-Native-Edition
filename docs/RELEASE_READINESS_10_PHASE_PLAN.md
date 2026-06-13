# Ashfall Release Readiness Plan

This plan tracks the release gates for a fully playable Ashfall experience across Native, NeoForge, Standalone, Launcher, Release Index, and shared modules.

## Phase Status

| Phase | Title | Status | Exit Gate |
| --- | --- | --- | --- |
| 1 | Release Freeze | Open | One release version, supported lanes, repo list, and go/no-go checklist are frozen. |
| 2 | Artifact Truth | Local staged; live blocked | Public downloads unzip into playable Ashfall packages with non-empty manifests and matching checksums. |
| 3 | Release Index Consistency | Local validators pass; live Native warning | Release Index pack and modpack records match live GitHub artifact URL, size, and SHA-256 data. |
| 4 | Required Module Closure | Local pass | Required transitive dependencies are explicit and installable. |
| 5 | Native Code Gate Fix | Local pass | `ECHO-Native-Platform` `gradlew.bat check` passes. |
| 6 | Module Artifact Build | Local pass | Compiled `.echo-addon`, `-neoforge.jar`, `-standalone.jar`, and source artifacts are generated and verified. |
| 7 | Native Public Beta Gates | Blocked | M30/M31 candidate, soak, no-crash, support, rollback, and public beta safety gates pass. |
| 8 | Gameplay QA | Evidence generator implemented; real play blocked | Real client, route, save/reload, server, export, and ending evidence clears release blockers. |
| 9 | Player-Facing Polish | Partial local pass; gameplay captures blocked | Docs, Launcher cards, screenshots, release notes, limitations, and known issues match the release. |
| 10 | Release Candidate And Publish | Local smoke implemented; publish blocked | Draft releases are downloaded, installed, smoke tested, and promoted only after all gates pass. |

## Required Validation Commands

Run these from the named repository roots before promoting a release candidate:

```txt
ECHO-Ashfall-Native-Edition: node scripts/docs-audit.mjs
ECHO-Ashfall-NeoForge-Edition: node scripts/docs-audit.mjs
ECHO-Ashfall-Standalone-Edition: node scripts/docs-audit.mjs
ECHO-Release-Index: node scripts/validate-index.mjs
ECHO-Release-Index: node scripts/sync-public-alpha-index.mjs --check
ECHO-Release-Index: node scripts/validate-public-alpha.mjs
ECHO-Release-Index: node scripts/verify-artifact-urls.mjs --all
ECHO-Release-Index: node scripts/test-build-public-alpha-assets.mjs
ECHO-Release-Index: node scripts/test-verify-ashfall-artifact-truth.mjs
ECHO-Release-Index: node scripts/test-verify-ashfall-release-readiness.mjs
ECHO-Release-Index: node scripts/test-generate-ashfall-rc-smoke.mjs
ECHO-Release-Index: node scripts/test-download-ashfall-draft-release.mjs
ECHO-Release-Index: node scripts/verify-ashfall-artifact-truth.mjs --download-live
ECHO-Release-Index: node scripts/verify-ashfall-artifact-truth.mjs --require-release-ready
ECHO-Release-Index: node scripts/generate-ashfall-rc-smoke.mjs
ECHO-Release-Index: node scripts/test-promote-ashfall-native-catalog.mjs
ECHO-Release-Index: node scripts/verify-ashfall-release-readiness.mjs --require-release-ready
ECHO-Release-Index: node scripts/build-public-alpha-assets.mjs --only ECHO-Modules --workspace-root .. --strict-assets
ECHO-Release-Index: node scripts/build-public-alpha-assets.mjs --only ECHO-Ashfall-Native-Edition --workspace-root .. --strict-assets
ECHO-Release-Index: node scripts/publish-public-alpha.mjs --only ECHO-Ashfall-Native-Edition --draft --prune-unlisted --publish --write-manifest --strict-assets
ECHO-Release-Index: node scripts/download-ashfall-draft-release.mjs --clean
ECHO-Release-Index: node scripts/generate-ashfall-rc-smoke.mjs --native-stage tmp/ashfall-draft-download/ECHO-Ashfall-Native-Edition --draft-download-evidence
ECHO-Release-Index: node scripts/promote-ashfall-native-catalog.mjs --write
ECHO-Modules: node scripts/validate-module-graph.mjs
ECHO-Modules: .\gradlew.bat generateAshfallRequiredModuleRelease --console=plain --no-configuration-cache --no-problems-report --max-workers=1
ECHO-Modules: node scripts/verify-module-release.mjs --release-dir dist/echo-module-release
ECHO-Native-Platform: .\gradlew.bat check
ECHO-Native-Platform: node scripts/test-generate-ashfall-native-code-gate.mjs
ECHO-Native-Platform: node scripts/generate-ashfall-native-code-gate.mjs
ECHO-Native-Platform: .\gradlew.bat packagePublicAlphaRelease --console=plain
ECHO-Native-Platform: node scripts/test-generate-ashfall-native-public-beta-evidence.mjs
ECHO-Native-Platform: node scripts/generate-ashfall-native-public-beta-evidence.mjs
ECHO-Native-Platform: node scripts/test-generate-ashfall-gameplay-qa-evidence.mjs
ECHO-Native-Platform: node scripts/generate-ashfall-gameplay-qa-evidence.mjs
ECHO-Launcher: npm.cmd test
ECHO-Launcher: npm.cmd run lint
ECHO-Launcher: npm.cmd run audit:placeholders
ECHO-Launcher: npm.cmd run build
ECHO-Launcher: npm.cmd run perf:budget
ECHO-Launcher: npm.cmd run test:e2e:release-index
```

## Non-Automated Release Evidence

Do not mark Ashfall public-release-ready until these have current evidence:

- Native artifact is a full playable Ashfall package, not a source-style placeholder archive.
- Release Index `verify-ashfall-artifact-truth --require-release-ready` passes after `--download-live` inspection.
- Native Platform `packagePublicAlphaRelease` stages from `build/native-product-package`; missing product layout must fail closed.
- Phase 5 Native code gate evidence from `generate-ashfall-native-code-gate.mjs` must record a real `gradlew check` execution with exit code 0.
- ECHO Modules public-alpha staging passes without `--allow-source-packaged-modules`; source-packaged output is only allowed for visibility builds and is not player-ready evidence.
- At least three distinct no-crash internal soak sessions with logs.
- Phase 7 Native public beta reports from `generate-ashfall-native-public-beta-evidence.mjs` must only pass after `fixtures/ashfall/native-public-beta/manual-evidence.json` cites three clean internal sessions, crash review notes, latest log review, checksum-verified tester package, support runbook, rollback plan, and published limitations.
- Real client first-hour smoke.
- Fresh world creation.
- Save/reload snapshots after first spawn, first relay, scanner/faction route, machine/power route, Nexus decision, ending, reward claim, and machine UI.
- Dedicated server start, join, gameplay smoke, and shutdown.
- Server/client export smoke.
- Balance/friction notes for grind walls, unavoidable hazards, unclear objectives, recovery loops, RadAway, and substrate grinder flow.
- Real gameplay screenshots for Launcher and storefront surfaces.
- Phase 8 gameplay QA evidence from `generate-ashfall-gameplay-qa-evidence.mjs` must only pass after upstream Native tester reports are current/non-dry-run and `fixtures/ashfall/gameplay-qa/manual-evidence.json` cites real first-hour, save/reload, route, server/export, ending, and no-crash artifacts.
- Release Candidate smoke evidence from `generate-ashfall-rc-smoke.mjs` may clear local install/repair/rollback evidence, but `draftReleaseDownloaded` now requires `release-readiness/ashfall-draft-download.json` from `download-ashfall-draft-release.mjs`, and `promotedAfterGreen` must only be true after final green-gate promotion actually happens.
- Ashfall Native release assets should be uploaded with `publish-public-alpha.mjs --only ECHO-Ashfall-Native-Edition --draft --prune-unlisted` first; this path must prune legacy placeholder assets and skip generic `manifest.json`, leaving only `checksums.txt`, `echo-release.json`, the exporter `.pack.json`, and the pack ZIP in the draft. If the tag already has a public release, either use a fresh RC tag or add `--convert-existing-public-release-to-draft` only after deciding to intentionally hide that public release. Catalog metadata can move to `approved` only after the draft assets download, checksums match, local smoke passes, and the remaining readiness gates are green.
- `promote-ashfall-native-catalog.mjs --write` is the only release-index-side step that may switch Ashfall Native catalog and Launcher metadata to `approved`; it must refuse promotion until the release is no longer draft and RC smoke records both `draftReleaseDownloaded` and `promotedAfterGreen`.
