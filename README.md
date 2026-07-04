# renovate-config

**Moved.** The shared Renovate preset now lives at [krypsis-io/renovate-config](https://github.com/krypsis-io/renovate-config).

This repo's `default.json` is a shim that extends the krypsis-io preset, so:

- repos still extending `github>cwaits6/renovate-config` keep working and get the krypsis-io rules
- new `cwaits6` personal repos onboarded by Renovate (which auto-detects this repo) land on the krypsis-io preset too

For new repos, prefer extending the source of truth directly:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>krypsis-io/renovate-config"]
}
```
