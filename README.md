<p align="center">
  <img src="https://ormus.solutions/mascot/pixellab_liquid_to_eye.gif" alt="Design Mastery" width="128" style="image-rendering: pixelated;" />
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

### Claude Code Plugin Marketplace

```bash
# Add to your Claude Code plugins
claude plugin add design-mastery
```

### Manual Installation

1. Clone this repository to your `.claude/plugins/` directory:
```bash
git clone https://github.com/HermeticOrmus/design-mastery-claude-code ~/.claude/plugins/design-mastery
```

2. Or copy the contents to your project's `.claude/` folder for project-specific use.

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

### Skills (Knowledge Bases)

| Skill | Coverage |
|-------|----------|
| **design-principles** | Gestalt, hierarchy, color theory, typography, composition |
| **design-masters** | Saul Bass, Vignelli, Rams, Scher, Brockmann, Carson, Rand |
| **design-movements** | Bauhaus, Swiss Style, Art Deco, Memphis, and more |
| **brand-systems** | Logo design, color palettes, typography pairing, voice |

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
├── agents/
│   ├── design-master.md
│   ├── brand-architect.md
│   └── visual-historian.md
├── commands/
│   ├── brand-identity.md
│   ├── design-audit.md
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
│   │   └── SKILL.md
│   └── brand-systems/
│       ├── SKILL.md
│       └── assets/
├── .claude-plugin/
│   └── marketplace.json
├── LICENSE
└── README.md
```

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
