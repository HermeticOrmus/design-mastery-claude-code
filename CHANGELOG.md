# Changelog

All notable changes to Design Mastery for Claude Code are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project uses [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Added

- A public pantry in `pantry/`: a competitor map, an X mine, a people mine and a pantry queue, every row cited. `pantry/MENU.md` is generated from the queue, never edited by hand, and names the next piece of work anyone can pick up.
- Two issue forms, with labels of the same names: `routing-miss`, for when Claude picks the wrong agent or skill, and `plugin-proposal`, for a new agent, command, skill or reference.
- CONTRIBUTING.md with a "Ways to contribute" section (Menu items, routing misses, new components and the file layout, translations, Show and tell) and the commands to test a change locally, plus a Contribute section in the README.

## [1.1.0] - 2026-09-30

A minor release: nothing is removed or renamed, and existing agents, commands, and skills keep their names. Install it with `/plugin marketplace add HermeticOrmus/design-mastery-claude-code` and `/plugin install design-mastery@design-mastery`.

### Added

- `.claude-plugin/plugin.json` at the repository root, so the repo installs as the `design-mastery` plugin from the `design-mastery` marketplace.
- 24 new reference files that the skills load on demand (27 in total, up from 3):
  - Masters: Massimo Vignelli, Dieter Rams, Paula Scher, David Carson, Josef Müller-Brockmann, Paul Rand (joining Saul Bass).
  - Movements: Arts and Crafts, Art Nouveau, Art Deco, Bauhaus, Swiss International Style, psychedelic design, postmodernism, Memphis, grunge and deconstructivism, interface styles from skeuomorphism to flat, Material, and current styles, and minimalism.
  - Principles: Gestalt grouping, visual hierarchy, composition (joining color theory and typography fundamentals).
  - Brand systems: logo design, color palettes, typography pairing, brand voice.
  Each covers key works with dates, the principles to borrow, how to apply them in UI work with Tailwind or CSS examples, and common misreadings. Every file the SKILL.md Resources sections promised now exists.
- The `premium-saas-design` skill and the `/premium-landing` command (the Define, Build, Review, Refine loop for premium SaaS marketing sites), previously only in the LibreUIUX copy of this plugin.
- An eval suite in `evals/` for `claude plugin eval`: a design audit of a flawed dashboard, a brand request that should start with positioning questions, identifying a movement from its visual markers, and a Dieter Rams simplification.
- `setup.sh`, which installs the plugin through the Claude Code CLI (`--list`, `--only`, `--scope`, `--uninstall`).
- A GitHub Actions workflow that validates the marketplace, the plugin, and every agent, command, and skill, then installs the plugin into a clean config.
- A feedback issue form and a Feedback section in the README.

### Changed

- Agents now use `model: inherit`, so they run on the model of your session instead of always on Sonnet.
- Every agent, command, and skill has a routing description that says when to use it. Commands have an `argument-hint`.
- The marketplace entry drops its hand-maintained component lists; Claude Code discovers `agents/`, `commands/`, and `skills/` from `plugin.json`.
- README: install instructions that work (`/plugin marketplace add`, `claude plugin install`, `./setup.sh`), updated contents and structure, and an Evals section.

### Fixed

- Installation instructions: `claude plugin add design-mastery` is not a Claude Code command, and cloning into `~/.claude/plugins/` does not register a plugin.
- The Vignelli Canon principles: Ambiguity means a plurality of meanings (not "eliminate it"), Responsibility is to the work, the client, and the public, and Equity is about the recognition an established mark has earned.
- Vignelli's typefaces: his "A Few Basic Typefaces" exhibition used four (Garamond, Bodoni, Century Expanded, Helvetica), not "only 5 in his career".
- Paula Scher designed the Windows 8 logo, not the Metro design language; the Citi identity dates from 1999.
- Paul Rand's logo criteria now follow his essay "Logos, Flags, and Escutcheons" instead of an unattributed list.
- Saul Bass: The Shining (1980) was a poster, not a title sequence; Kleenex (1961) and Continental Airlines (1967) dates corrected.
- WCAG large text is 24px regular or about 18.66px bold, not 18px; touch targets cite WCAG 2.2 (24x24px AA, 44x44px AAA).
- Tailwind `text-4xl` is 36px, not 40px; visual weight is higher in the frame, not lower (Arnheim); the FedEx arrow is figure/ground, not closure; the golden ratio is presented as one proportion system, not an innate preference.
- Contrast figures for `#2563eb` and `#0066CC`, deuteranopia prevalence, and a note that Tailwind's 500-step semantic colors fail 4.5:1 as text.
- Movements: grunge origins (Southern California, Seattle, London, Cranbrook, Emigre), Memphis founded in 1980, the Bowie "Tonight" cover (not Memphis work), Bauhaus legacy claims, and the revival "cycle" labelled as speculation.
- A pronoun slip in the design-master agent and an overstated "father of Swiss style" claim.
- The premium SaaS skill's opening statistic now describes the Stanford web credibility study accurately.
