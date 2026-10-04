# Install in Grok Build

A user installs design-mastery-claude-code plugins with the Grok Build CLI, which reads the same plugin folders as Claude Code. Each installed plugin shows as installed in `grok plugin list`.

## Sub-features

- `grok-install-one` installs one plugin with `--trust`.
- `grok-install-all` installs every plugin the Grok manifest lists.
- `grok-list` shows each installed plugin with status `installed`.
- `grok-manifest-sync` keeps `.grok-plugin/marketplace.json` matching the Claude manifest, where the repo has one.

## How to get to it (user POV)

- From a terminal: `grok plugin install HermeticOrmus/design-mastery-claude-code --trust`.
- From a clone: `grok plugin install <checkout> --trust`.

## Driving it with control-design-mastery

Preconditions:

- `.grok/skills/verify-design-mastery/bin/control-design-mastery doctor` reports `worth_driving: true`, including `grok_manifest_in_sync: true`.

- **Install the plugin.** Run `.grok/skills/verify-design-mastery/bin/control-design-mastery install --grok`. `evidence/grok-install.log` ends in `exit 0`.
- **Confirm it is installed.** `result.json` has `grok.installed` equal to `grok.wanted` and an empty `grok.missing`. `evidence/grok-list.json` lists the plugin with `"status": "installed"`.
- **Install the whole pack.** Run `.grok/skills/verify-design-mastery/bin/control-design-mastery run`. `result.json` has `grok.missing` empty and `ok: true`.
- **Proof.** Keep `evidence/grok-list.json` and `evidence/result.json` from the run.

## Gotchas

- The repo root is the one plugin and there is no `.grok-plugin/marketplace.json`, so Grok installs the folder directly instead of adding a marketplace.
- `--trust` is required for a non-interactive install. Without it Grok stops to ask.
- After changing `.claude-plugin/marketplace.json`, run `python3 scripts/sync-grok-manifest.py` and commit what it writes, or `doctor` and `scripts/check.sh` fail on the sync check.
