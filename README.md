<p align="center">
  <img src="https://ormus.solutions/mascot/pixellab_liquid_to_lotus.gif" alt="Design Mastery" width="128" style="image-rendering: pixelated;" />
</p>

<h1 align="center">Design Mastery</h1>

<p align="center">
  <em>Learn from Saul Bass, Dieter Rams, and the masters -- through code</em>
</p>

<p align="center">
  <a href="https://github.com/HermeticOrmus/design-mastery-claude-code/stargazers"><img src="https://img.shields.io/github/stars/HermeticOrmus/design-mastery-claude-code?style=flat-square&color=aa8142" alt="Stars" /></a>
  <a href="https://github.com/HermeticOrmus/design-mastery-claude-code/blob/main/LICENSE"><img src="https://img.shields.io/github/license/HermeticOrmus/design-mastery-claude-code?style=flat-square&color=aa8142" alt="License" /></a>
  <a href="https://github.com/HermeticOrmus/design-mastery-claude-code/commits"><img src="https://img.shields.io/github/last-commit/HermeticOrmus/design-mastery-claude-code?style=flat-square&color=aa8142" alt="Last Commit" /></a>
  <img src="https://img.shields.io/badge/Claude Code-aa8142?style=flat-square&logo=anthropic&logoColor=white" alt="Claude Code" />
</p>

---

A comprehensive design knowledge plugin that brings timeless design wisdom to AI-assisted development. Learn from legendary designers, apply fundamental principles, and build professional brand identities.

## What This Is

Design Mastery is a Claude Code plugin that transforms how you approach visual design. Instead of vague aesthetic requests, you'll have access to:

- **Deep knowledge** of design principles (Gestalt, hierarchy, color theory)
- **Wisdom from masters** (Saul Bass, Massimo Vignelli, Dieter Rams, Paula Scher)
- **Historical context** (Bauhaus, Swiss Style, Memphis, and beyond)
- **Practical commands** for brand building and design evaluation

## Installation

### Install from Claude Code

```
/plugin marketplace add HermeticOrmus/design-mastery-claude-code
/plugin install design-mastery@design-mastery
```

The same thing from a terminal:

```bash
claude plugin marketplace add HermeticOrmus/design-mastery-claude-code
claude plugin install design-mastery@design-mastery
```

Or from a clone of this repository, run `./setup.sh`. It registers the checkout as a marketplace and installs the plugin through the Claude Code CLI (`./setup.sh --list` shows what it installs, `--scope project` installs for one project only, `--uninstall` removes it). Restart Claude Code after installing so it loads the plugin.

### Manual Installation

Copy the agents, commands, and skills into a project's `.claude/` folder for project-specific use:

```bash
git clone https://github.com/HermeticOrmus/design-mastery-claude-code
cp -r design-mastery-claude-code/agents design-mastery-claude-code/commands design-mastery-claude-code/skills your-project/.claude/
```

## What's Included

### Agents

| Agent | Description |
|-------|-------------|
| **design-master** | Comprehensive design guide drawing from principles and masters |
| **brand-architect** | Systematic brand identity development |
| **visual-historian** | Design history and movement expertise |

### Commands

| Command | Description |
|---------|-------------|
| `/brand-identity` | Guided workflow for creating brand identity systems |
| `/design-audit` | Systematic evaluation against design principles |
| `/style-guide` | Generate design system documentation |
| `/premium-landing` | Plan, build, review, and refine a premium SaaS landing page section by section |

### Skills (Knowledge Bases)

| Skill | Coverage |
|-------|----------|
| **design-principles** | Gestalt, hierarchy, color theory, typography, composition |
| **design-masters** | Saul Bass, Vignelli, Rams, Scher, Brockmann, Carson, Rand |
| **design-movements** | Bauhaus, Swiss Style, Art Deco, Memphis, and more |
| **brand-systems** | Logo design, color palettes, typography pairing, voice |
| **premium-saas-design** | The Define, Build, Review, Refine loop for premium SaaS marketing sites |

Each knowledge skill ships reference files that Claude reads on demand: a profile for every master (Bass, Vignelli, Rams, Scher, Müller-Brockmann, Carson, Rand), a file for every movement in the design-movements lineage, and deep dives on Gestalt, hierarchy, composition, color, typography, logos, palettes, type pairing, and brand voice.

## Usage Examples

### Get Design Guidance
```
"Make this hero section more impactful"

→ Design Master applies Saul Bass's simplification principles,
  suggests specific Tailwind changes with reasoning
```

### Build a Brand
```
/brand-identity

→ Walks you through Discovery → Strategy → Visual Identity →
  Guidelines, outputting actionable design tokens and documentation
```

### Evaluate a Design
```
/design-audit [screenshot or description]

→ Scores across 8 dimensions (hierarchy, typography, color, etc.)
  with specific fixes rooted in design theory
```

### Understand History
```
"Why does this feel 'retro'?"

→ Visual Historian traces the aesthetic to its historical roots,
  explains the cultural context, suggests intentional application
```

## Design Philosophy

This plugin is built on the belief that:

1. **Design is not decoration** — it's communication
2. **Principles trump trends** — fundamentals outlast fads
3. **History illuminates** — understanding origins enables intentionality
4. **Specificity beats vagueness** — "shadow-lg" works better than "make it pop"

## The Masters

Learn from designers whose work has shaped visual culture:

- **Saul Bass** — "Symbolize and summarize"
- **Massimo Vignelli** — "If you can design one thing, you can design everything"
- **Dieter Rams** — "Less, but better"
- **Paula Scher** — "It's through mistakes that you actually can grow"
- **Josef Müller-Brockmann** — "The grid system is an aid, not a guarantee"

## Structure

```
design-mastery-claude-code/
├── .claude-plugin/
│   ├── marketplace.json        # the design-mastery marketplace
│   └── plugin.json             # the design-mastery plugin (repo root)
├── agents/
│   ├── design-master.md
│   ├── brand-architect.md
│   └── visual-historian.md
├── commands/
│   ├── brand-identity.md
│   ├── design-audit.md
│   ├── premium-landing.md
│   └── style-guide.md
├── skills/
│   ├── design-principles/
│   │   ├── SKILL.md
│   │   ├── assets/
│   │   └── references/
│   ├── design-masters/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── design-movements/
│   │   ├── SKILL.md
│   │   └── references/
│   ├── brand-systems/
│   │   ├── SKILL.md
│   │   ├── assets/
│   │   └── references/
│   └── premium-saas-design/
│       └── SKILL.md
├── evals/                      # cases for `claude plugin eval`
├── pantry/                     # research and the Menu of open work
├── setup.sh
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

## Evals

`evals/` holds cases for `claude plugin eval`: a design audit of a flawed dashboard, a brand request that should start with positioning questions, a movement identification, and a Dieter Rams simplification. Run them from a clone with:

```bash
claude plugin eval . --no-publish
```

Each case runs the plugin and a no-plugin baseline, so the report shows what the plugin adds.

## Feedback

Starred this? Tell us what worked and what is missing: [open a feedback issue](https://github.com/HermeticOrmus/design-mastery-claude-code/issues/new?template=feedback.yml). Every piece of feedback gets an answer, and changes that come from it are credited in the release notes.

## Contribute

- Take an item from the [Menu](pantry/MENU.md): each one has a Done-when anyone can check. Open items are [`[menu]` issues](https://github.com/HermeticOrmus/design-mastery-claude-code/issues?q=is%3Aopen+label%3Amenu).
- New here? Start with the [good first issues](https://github.com/HermeticOrmus/design-mastery-claude-code/contribute).
- Use a form: [feedback](https://github.com/HermeticOrmus/design-mastery-claude-code/issues/new?template=feedback.yml), [routing miss](https://github.com/HermeticOrmus/design-mastery-claude-code/issues/new?template=routing-miss.yml) when Claude picks the wrong agent or skill, or [plugin proposal](https://github.com/HermeticOrmus/design-mastery-claude-code/issues/new?template=plugin-proposal.yml) for a new agent, command, skill or reference.
- Show what you built in [Discussions, Show and tell](https://github.com/HermeticOrmus/design-mastery-claude-code/discussions/categories/show-and-tell).
- The file layout and the commands to test a change locally are in [CONTRIBUTING.md](CONTRIBUTING.md).

## Contributing

Contributions welcome! Especially:

- Additional designer deep-dives
- More design movement coverage
- Reference documents for principles
- Real-world case studies

## License

MIT License - See [LICENSE](LICENSE)

## Acknowledgments

- Built for [Claude Code](https://claude.ai/claude-code)
- Inspired by the timeless work of design masters
- Part of the [LibreUIUX](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code) ecosystem

---

*Design is thinking made visual. — Saul Bass*

---

## Part of the Libre Open-Source Stack for Claude Code

This repository is part of a growing family of open-source toolkits for Claude Code.

### Libre suite — comprehensive plugin bundles

- [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code) — UI/UX development (152 agents, 71 plugins, 76 commands, 74 skills)
- [LibreArch-Claude-Code](https://github.com/HermeticOrmus/LibreArch-Claude-Code) — Software architecture and system design
- [LibreCopy-Claude-Code](https://github.com/HermeticOrmus/LibreCopy-Claude-Code) — Technical writing and documentation engineering
- [LibreDevOps-Claude-Code](https://github.com/HermeticOrmus/LibreDevOps-Claude-Code) — DevOps engineering and infrastructure automation
- [LibreEmbed-Claude-Code](https://github.com/HermeticOrmus/LibreEmbed-Claude-Code) — Embedded systems, firmware, and IoT development
- [LibreFinTech-Claude-Code](https://github.com/HermeticOrmus/LibreFinTech-Claude-Code) — Financial technology development
- [LibreGEO-Claude-Code](https://github.com/HermeticOrmus/LibreGEO-Claude-Code) — AI-search optimization (ChatGPT, Perplexity, Gemini, Google AI Overviews)
- [LibreGameDev-Claude-Code](https://github.com/HermeticOrmus/LibreGameDev-Claude-Code) — Game development across Godot, Unity, Unreal
- [LibreMLOps-Claude-Code](https://github.com/HermeticOrmus/LibreMLOps-Claude-Code) — ML engineering and AI operations
- [LibreMobileDev-Claude-Code](https://github.com/HermeticOrmus/LibreMobileDev-Claude-Code) — Mobile app development (Flutter, React Native, native iOS, native Android)
- [LibreSecOps-Claude-Code](https://github.com/HermeticOrmus/LibreSecOps-Claude-Code) — Security operations

### Skills mini-repos — single CLAUDE.md drop-ins

- [vibe-engineer-skills](https://github.com/HermeticOrmus/vibe-engineer-skills) — Direct AI codegen well (hypothesis → scope → validate → reject working-but-wrong)
- [markdown-discipline-skills](https://github.com/HermeticOrmus/markdown-discipline-skills) — Strip AI-slop from markdown (no em dashes, no marketing fluff)
- [shell-safety-skills](https://github.com/HermeticOrmus/shell-safety-skills) — `set -euo pipefail` discipline + 15 failure-mode examples
- [commit-standard-skills](https://github.com/HermeticOrmus/commit-standard-skills) — Ormus Commit Standard v1.0 + commit-msg hook + commitlint
- [unwoke-skills](https://github.com/HermeticOrmus/unwoke-skills) — Strip AI theater (ten sins to eliminate, symmetric engagement)
- [python-conventions-skills](https://github.com/HermeticOrmus/python-conventions-skills) — Modern Python 3.11+ (types, pathlib, async, ruff, mypy, uv)
- [typescript-conventions-skills](https://github.com/HermeticOrmus/typescript-conventions-skills) — TypeScript strict mode, discriminated unions, Result types
- [hermetic-laws-skills](https://github.com/HermeticOrmus/hermetic-laws-skills) — Seven Hermetic Principles applied to engineering
- [riper-workflow-skills](https://github.com/HermeticOrmus/riper-workflow-skills) — Research / Innovate / Plan / Execute / Review systematic dev
- [six-day-cycle-skills](https://github.com/HermeticOrmus/six-day-cycle-skills) — Sustainable shipping cadence with mandatory rest
- [token-optimization-skills](https://github.com/HermeticOrmus/token-optimization-skills) — Claude Code token + context optimization
- [osint-skills](https://github.com/HermeticOrmus/osint-skills) — OSINT research methodology (multi-wave investigative spiral)
- [calcinate-skills](https://github.com/HermeticOrmus/calcinate-skills) — Stage 1 of the Magnum Opus (burn project bloat)
- [claude-md-overhaul-skills](https://github.com/HermeticOrmus/claude-md-overhaul-skills) — Audit CLAUDE.md and MEMORY.md against caps
- [session-handoff-skills](https://github.com/HermeticOrmus/session-handoff-skills) — Session handoff + pickup discipline
- [naming-skills](https://github.com/HermeticOrmus/naming-skills) — Product naming methodology (mine the brand's vocabulary)
- [magnum-opus-skills](https://github.com/HermeticOrmus/magnum-opus-skills) — Seven-stage alchemy applied to project transformation

### Template source

- [andrej-karpathy-skills](https://github.com/HermeticOrmus/andrej-karpathy-skills) — the canonical single-file CLAUDE.md pattern (fork of jiayuan_jy's original)

Star the family, not just one — that's how the suite stays coherent.
