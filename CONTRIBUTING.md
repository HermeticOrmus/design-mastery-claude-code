# Contributing to Design Mastery

Design Mastery is one Claude Code plugin: the repository root is both the `design-mastery` marketplace and the `design-mastery` plugin. Contributions that add knowledge (a master, a movement, a principle), sharpen when a component fires, or prove a claim with an eval are the most useful.

## Ways to contribute

### Take a Menu item

[`pantry/MENU.md`](pantry/MENU.md) lists the next pieces of work, each with a Done-when anyone can check, and names one as up next. The research behind it (competitor map, posts on X, what people said here) sits beside it in [`pantry/`](pantry/). Open items are [`[menu]` issues](https://github.com/HermeticOrmus/design-mastery-claude-code/issues?q=is%3Aopen+label%3Amenu); smaller starting points are under [good first issues](https://github.com/HermeticOrmus/design-mastery-claude-code/contribute). Claim one by commenting on its issue, then open a pull request that says `Closes #N`.

### Report or fix a routing miss

Every agent, command and skill has a `description` that tells Claude when to use it. When Claude picks the wrong one, or none (for example `design-master` answers a "why does this look retro?" question that `visual-historian` should take), open a [routing miss](https://github.com/HermeticOrmus/design-mastery-claude-code/issues/new?template=routing-miss.yml) with the prompt, what should have run, and what ran instead. The fix is usually a sharper `description` in that file's frontmatter, which makes it a good first pull request.

### Propose or build an agent, command, skill or reference

Open a [plugin proposal](https://github.com/HermeticOrmus/design-mastery-claude-code/issues/new?template=plugin-proposal.yml) first, so the job it does and its Done-when are agreed before you write it. Everything lives at the repository root:

```text
.claude-plugin/plugin.json               # name, version, description, author, homepage, repository, license, keywords
.claude-plugin/marketplace.json          # the design-mastery marketplace; its one entry has source "."
agents/<agent>.md                        # frontmatter: name, description ("Use this agent when ..."), model: inherit
commands/<command>.md                    # frontmatter: name, description, argument-hint if it takes input
skills/<skill>/SKILL.md                  # frontmatter: name, description (say when to use it: "Use when ...")
skills/<skill>/references/<topic>.md     # read on demand; list it in that SKILL.md's Resources section
evals/<case>/prompt.md, graders/*.md     # cases for claude plugin eval
```

A new agent, command or skill needs no new marketplace entry; add it to the README tables. If you change `version`, change it in both `plugin.json` and the marketplace entry, since the two must agree. A new reference file follows the layout of its neighbors (for a master: who they are, key works with dates, principles to borrow, applying them in UI work with Tailwind or CSS, common misreadings, quick reference), and every date or attribution cites a source. The README's Contributing section lists the knowledge we most want: designer deep-dives, more movements, principle references, and case studies.

### Translate

The docs are in English only. A translation of the README is a good place to start: add it next to the original with the language code (for example `README.es.md`), link it from the English file, and label the pull request `translation`.

### Share what you built

Post it in [Discussions, Show and tell](https://github.com/HermeticOrmus/design-mastery-claude-code/discussions/categories/show-and-tell): the prompt, what the plugin said, and what you shipped. Good ones can become examples, eval cases or Menu items.

### Test your change locally

```bash
# Load the plugin from your working tree for a single session, without installing it
claude --plugin-dir .

# Validate the marketplace manifest
claude plugin validate .

# Validate the plugin and every agent, command and skill, the way CI does:
# validate a copy without marketplace.json, with warnings treated as errors
dir=$(mktemp -d)
git ls-files | grep -v '^.claude-plugin/marketplace.json$' | xargs -d '\n' cp --parents -t "$dir"
claude plugin validate --strict "$dir"

# Install from your checkout into a throwaway config; your own config is untouched
export CLAUDE_CONFIG_DIR=$(mktemp -d)
claude plugin marketplace add ./
claude plugin install design-mastery@design-mastery
claude plugin details design-mastery@design-mastery   # lists the agents and skills Claude Code found (commands show up as skills)
unset CLAUDE_CONFIG_DIR

# Run the eval suite (it runs on your own Claude account; add --case <name> for one case)
claude plugin eval . --no-publish
```

`git ls-files` copies only tracked files, so `git add` new files before the strict check. CI ([`.github/workflows/check.yml`](.github/workflows/check.yml), running `bash scripts/check.sh`) runs the same validation and clean-config install on every pull request. A first-time contributor's CI run waits until a maintainer approves it, so a pending check on your first pull request is expected.
</content>
</invoke>
