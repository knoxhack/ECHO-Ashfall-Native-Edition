# Ashfall Known Issues

- BLOCKER: Agent 7 has produced semi-automated restore, destroy, and control crash-to-ending host proofs, but still needs player-facing balance/friction traversal before release sign-off.
- BLOCKER: Agent 7 still needs player-facing balance/friction notes for grind walls, lethal unavoidable hazards, unclear objectives, and broken recovery loops. Static gameplay-data, UX, route/faction balance, hazard recovery, RadAway, and substrate grinder host probes pass, but they do not prove live route feel.
- Real-client launch smoke now reaches post-resource-load/title-idle evidence after guarding ThemeCore loading-overlay text until the initial resource reload is complete. Fresh world creation and live route traversal are still open.
- Host save-reload relog is now proven in `agent7_checkpoint_relog_host_smoke` across major route checkpoints and restore epilogue. Real-client relog snapshots are still requested for release notes after first spawn, first relay, scanner/faction, midgame machine/power, Nexus decision, ending, reward claim, and machine UI.
- Operational note: the default local Gradle output may produce stale class-output or Windows deletion-lock failures during repeated host QA. Use a clean `ECHO_GRADLE_BUILD_DIR` such as `C:\Users\knox\AppData\Local\EchoGradleBuildAgent7` when collecting release evidence.
- Manual first-hour smoke testing still needs to be run in a real client world before claiming public release readiness.
- Dedicated server smoke testing still needs a fresh start, join, and shutdown pass.
- Real gameplay screenshots should be captured for storefront galleries and Launcher galleries; see `SCREENSHOT_REQUIREMENTS.md`.
- Server/client export smoke tests should be run before broad announcement.
- RenderCore pending production boards remain shared visual-review debt.
- ScreenCore Terminal pages remain opt-in through `terminal.screenCoreExperimentalTabs=true`; the classic Terminal renderer is still the safe default path.
- Official Pack #2 remains out of scope for Ashfall 1.7.6 stabilization.
