# renovate-config

Shared [Renovate](https://docs.renovatebot.com/) configuration preset for [`cwaits6`](https://github.com/cwaits6) repos.

## Usage

Add a `renovate.json` to any repo:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>cwaits6/renovate-config"]
}
```

That's it. All rules from this repo's `default.json` apply automatically.

## What's included

- **Base**: `config:recommended` — dependency dashboard, monorepo grouping, rate limiting
- **Schedule**: weekdays only (America/New_York)
- **Semantic commits**: PR titles follow conventional commit format, compatible with semantic-release
- **Labels**: all Renovate PRs get a `dependencies` label

### Automerge rules

| Update type | Scope | Automerge |
|---|---|---|
| `patch` | all | yes |
| `minor` | devDependencies | yes |
| `minor` / `patch` | GitHub Actions | yes (grouped) |
| `major` | all | no — manual review required |

## Customizing per repo

To override a rule in a specific repo, add `packageRules` in that repo's `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>cwaits6/renovate-config"],
  "packageRules": [
    {
      "matchUpdateTypes": ["minor"],
      "automerge": false
    }
  ]
}
```

Per-repo rules merge with and can override the shared config.
