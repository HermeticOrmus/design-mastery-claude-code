# Install from Claude Code

A user adds design-mastery-claude-code as a plugin marketplace in Claude Code and installs plugins from it by name. Each installed plugin shows as enabled under the `design-mastery` marketplace and its components are available after a restart.

## Sub-features

- `claude-marketplace-add` registers the repo as the `design-mastery` marketplace.
- `claude-install-one` installs one plugin as `<plugin>@design-mastery`.
- `claude-install-all` installs every plugin in the pack (1 in total).
- `claude-list` shows each installed plugin as enabled.

## How to get to it (user POV)

- Inside Claude Code: `/plugin marketplace add HermeticOrmus/design-mastery-claude-code`, then `/plugin install design-mastery@design-mastery`.
- From a terminal: `claude plugin marketplace add HermeticOrmus/design-mastery-claude-code`, then `claude plugin install design-mastery@design-mastery`.
- `/plugin` inside Claude Code opens the plugin manager to browse the rest of the pack.

## Driving it with control-design-mastery

Preconditions:

- `.grok/skills/verify-design-mastery/bin/control-design-mastery doctor` reports `worth_driving: true`.

- **Add the marketplace and install one plugin.** Run `.grok/skills/verify-design-mastery/bin/control-design-mastery install --claude --only design-mastery`. `evidence/claude-marketplace-add.log` and `evidence/claude-install-design-mastery.log` end in `exit 0`.
- **Confirm it is enabled.** The same command prints `result.json`: `claude.enabled` is 1, `claude.missing` and `claude.load_errors` are empty. `evidence/claude-list.json` has `design-mastery@design-mastery` with `"enabled": true`.
- **Install the whole pack.** Run `.grok/skills/verify-design-mastery/bin/control-design-mastery run`. `result.json` has `claude.wanted` equal to `claude.enabled` (1) and `ok: true`.
- **Proof.** Keep `evidence/claude-list.json` and `evidence/result.json` from the run.

## Gotchas

- The marketplace name is `design-mastery` (from `.claude-plugin/marketplace.json`), not the repo name. `<plugin>@design-mastery-claude-code` fails in Claude Code.
- Installing from `HermeticOrmus/design-mastery-claude-code` installs what is on GitHub's default branch. To prove a change, install from the tree under test, which is what the helper does.
- Claude Code loads new plugins at the next session start. The proof is the list and details read back, not a live session.
