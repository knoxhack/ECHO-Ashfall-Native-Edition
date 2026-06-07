# ECHO Native Rollback Guide

## Before You Update

1. **Back up worlds and saves.**
   - Client: copy `saves/` and `config/`.
   - Server: copy the world folder, `config/`, and `echo/` state directories.
2. **Export configs.**
   - Copy `config/echo/` to a dated backup folder.
3. **Note the current versions.**
   - Write down the current ECHO Native Loader and addon versions.

## Rolling Back

1. **Stop the client or server.** Do not roll back while running.
2. **Replace jars.**
   - Remove current ECHO Native Loader and addon jars.
   - Restore the previous versions from backup.
3. **Restore configs (if needed).**
   - If new config options were added, restore the pre-update `config/echo/` folder.
4. **Restore saves (if needed).**
   - If world corruption is suspected, restore the pre-update world backup.
5. **Start and verify.**
   - Check `latest.log` for the expected older loader version string.
   - Run `/echo version` to confirm addon versions.

## Cross-Version Compatibility

- Do **not** mix ECHO Native Loader RC versions with mismatched addon descriptors. A 1.0.0-RC2 loader may reject 1.0.0-RC1 descriptors if schema fields changed.
- Do **not** open a world with newer addon data and then roll back to older addon jars without restoring the world backup.
- `DataCore` state is forward-compatible but not guaranteed backward-compatible. Restore world backups when rolling back.

## Partial Rollback (Single Addon)

If one addon update is broken:
1. Stop the runtime.
2. Replace only that addon's jar with the previous version.
3. Verify the addon's descriptor version matches what the loader expects.
4. Start and check logs.

## Automated Backups

Server operators can enable the `echoruntimeguard` backup budget:

```toml
[backup]
enabled = true
intervalMinutes = 30
keepCount = 6
```

This writes timestamped world snapshots to `backups/` and simplifies rollback.

## Getting Help

If rollback does not resolve the issue, follow the [Crash Report Guide](CRASH_REPORT_GUIDE.md) and open a bug report with your pre-update and post-update versions.
