# Competitor map: design-mastery-claude-code

## How this fills

1. Name the product and its surfaces (plugins, agents, skills, commands, install paths).
2. WebSearch / WebFetch public competitor docs, READMEs and homepages: other Claude Code plugin packs and marketplaces in this domain, Cursor rules and plugins, Codex or Gemini CLI extensions, and standalone tools people use for the same job.
3. One row per competitor; blank unknowns; cite a URL per row.
4. Fill the capabilities matrix (Y / N / P / ?) with the capabilities that matter in this domain, and a source per claimed cell.
5. Save as `YYYY-MM-DD-competitor-map.md` (keep this template).

Star counts are `stargazers_count` from the GitHub REST API, read on 2026-09-30. Feature claims come from each project's README or homepage as fetched on 2026-09-30.

## Product

- Name: Design Mastery for Claude Code, v1.1.0 on main.
- Flagship: the `design-mastery` plugin, installed from the `design-mastery` marketplace (`/plugin marketplace add HermeticOrmus/design-mastery-claude-code`, then `/plugin install design-mastery@design-mastery`). The repo root is both the marketplace and the plugin.
- Our surfaces:
  - Agents: `design-master`, `brand-architect`, `visual-historian` (all `model: inherit`, routing descriptions).
  - Commands: `/brand-identity`, `/design-audit` (eight scored dimensions, accessibility among them; takes a screenshot path, URL, code or description), `/style-guide` (tokens, type scale, Tailwind or CSS config), `/premium-landing`.
  - Skills: `design-principles`, `design-masters` (Bass, Vignelli, Rams, Scher, Müller-Brockmann, Carson, Rand), `design-movements` (11 reference files, Arts and Crafts to minimalism), `brand-systems`, `premium-saas-design`; 27 reference files in total.
  - Evals: 4 cases in `evals/` for `claude plugin eval` (design audit, brand discovery, movement identification, Dieter Rams). `evals/results/` is gitignored and no scores are recorded in the repo.
  - `setup.sh`, and a CI workflow that validates the marketplace, the plugin and every component, then installs it into a clean config.
  - A copy of this plugin also ships in [LibreUIUX-Claude-Code](https://github.com/HermeticOrmus/LibreUIUX-Claude-Code) as `design-mastery@libreuiux` (synced at 1.1.0, per that repo's CHANGELOG).

## Map

| Competitor | What it is | Overlap with us | Watch / differentiator | Source URL |
|------------|------------|-----------------|------------------------|------------|
| Anthropic frontend-design | First-party plugin and skill: pick an aesthetic direction before code, choose typefaces deliberately with a type scale "following the default guidance of The Elements of Typographic Style", avoid the traits AI-generated design clusters around, then critique against the brief | `design-principles`, `design-master`, `/design-audit` | First-party; in the official directory (anthropics/claude-plugins-official, 37,242 stars) and in anthropics/skills (179,153 stars) | https://github.com/anthropics/claude-code/tree/main/plugins/frontend-design |
| Anthropic skills: brand-guidelines, theme-factory, canvas-design | brand-guidelines applies Anthropic's own brand colors and type; theme-factory styles artifacts with 10 preset themes or a generated one; canvas-design makes posters and art "using design philosophy" | `brand-systems`, `/brand-identity`, `/style-guide` | Installable as a Claude Code marketplace (`/plugin marketplace add anthropics/skills`) | https://github.com/anthropics/skills |
| Impeccable (pbakaus/impeccable, 72,930 stars) | One skill, 24 commands (`critique`, `audit`, `typeset`, `colorize`, `layout`, `polish`, ...), 61 deterministic detector rules, live browser iteration | `/design-audit`, `design-principles` | `npx impeccable detect` checks files or a URL with no LLM; critique scores against Nielsen's heuristics (maker's post); records product context in PRODUCT.md | https://github.com/pbakaus/impeccable |
| UI UX Pro Max (nextlevelbuilder/ui-ux-pro-max-skill, 131,959 stars) | Searchable design data: 79 UI styles (50 active), 192 palettes, 74 font pairings, 119 UX guidelines; generates a design system per product type | `brand-systems`, `/style-guide` | Data-driven recommendations; installs in Claude Code, Cursor, Codex, Gemini CLI | https://github.com/nextlevelbuilder/ui-ux-pro-max-skill |
| Hallmark (Nutlope/hallmark, 29,355 stars) | Design skill with 21 themes and four verbs: build, `audit` (punch list against anti-patterns), `redesign`, `study` (extract a design's structure from a screenshot or URL) | `/design-audit`, `visual-historian` (naming what a design is doing) | Refuses pixel clones; emits a portable design.md | https://github.com/Nutlope/hallmark |
| wshobson/agents ui-design plugin (40,112 stars for the repo) | Plugin with agents ui-designer, design-system-architect, accessibility-expert; commands design-review, design-system-setup, create-component, accessibility-audit; skills incl. `visual-design-foundations`, `design-system-patterns`, `interaction-design` | `design-master`, `/design-audit`, `/style-guide`, `design-principles` | Multi-harness marketplace (Codex, Cursor, OpenCode, Antigravity, Copilot, Pi) | https://github.com/wshobson/agents/tree/main/plugins/ui-design |
| OneRedOak design review workflow (OneRedOak/claude-code-workflows, 3,892 stars) | A design-review agent and slash command that review front-end changes in a live browser through Playwright MCP, against a design-principles file | `/design-audit`, `assets/principles-checklist.md` | Looks at the rendered page; files to copy, not a plugin | https://github.com/OneRedOak/claude-code-workflows/tree/main/design-review |
| VoltAgent/awesome-design-md (118,939 stars) | DESIGN.md files describing popular brands' design systems, for agents to build a matching UI | `brand-systems`, `/style-guide` | Existing brands' systems, not the principles behind them | https://github.com/VoltAgent/awesome-design-md |
| cursor-designer (spencergoldade/cursor-designer, 34 stars) | Cursor rules for UX, UI, information architecture, accessibility and research-driven design, in core, lean and full profiles | `design-principles`, `/design-audit` | Cursor-native `.mdc` rules | https://github.com/spencergoldade/cursor-designer |

## Capabilities matrix

Mark Y / N / P (partial) / ? and cite. Rows are the capabilities that matter for this domain.

Columns: Us = design-mastery on main; FD = Anthropic frontend-design; Imp = Impeccable; UUPM = UI UX Pro Max; Hall = Hallmark; wsh-ui = wshobson/agents ui-design; ORO = OneRedOak design review; CurD = cursor-designer.

| Capability | Us | FD | Imp | UUPM | Hall | wsh-ui | ORO | CurD | Source notes |
|------------|----|----|-----|------|------|--------|-----|------|--------------|
| Claude Code plugin install | Y | Y | Y | Y | ? | Y | N | N | Us: `.claude-plugin/marketplace.json`, CI clean-config install. FD: plugin in anthropics/claude-code. Imp: maker's post https://x.com/pbakaus/status/2009758986418172226. UUPM: README `/plugin install ui-ux-pro-max@ui-ux-pro-max-skill`. Hall: README documents `npx skills add`. wsh-ui: `plugins/ui-design/.claude-plugin/plugin.json`. ORO: copy files. CurD: Cursor rules. |
| Other harnesses (Cursor, Codex, Gemini CLI) | N | ? | Y | Y | Y | Y | N | Y | Us: README documents Claude Code only. Imp, UUPM, Hall, wsh: README install paths per harness. CurD: Cursor only. |
| Design principles knowledge | Y | P | P | P | ? | Y | P | Y | Us: `design-principles` with 5 references and a checklist. FD: typography and structure guidance in SKILL.md. Imp: `typeset`, `layout`, `colorize` commands. UUPM: 119 UX guidelines. wsh-ui: `visual-design-foundations`. ORO: `design-principles-example.md`. CurD: UX, UI and IA rules. |
| Design history: masters and movements | Y | N | N | P | N | ? | N | N | Us: 7 master profiles, 11 movement files. Grep of the fetched READMEs of FD (SKILL.md), Imp, Hall and CurD finds no designers or movements; UUPM's style catalog names visual styles such as Brutalism, with no designers or history. wsh-ui: skills not read. |
| Aesthetic direction (avoids generic AI defaults) | P | Y | Y | Y | Y | ? | ? | ? | Us: `premium-saas-design` contrasts generic and premium output; no list of named AI tells. FD: SKILL.md lists the clusters of AI-generated design. Imp: README anti-patterns. UUPM: style per product type. Hall: 57 slop-test gates. |
| Brand identity workflow (positioning before visuals) | Y | N | P | P | ? | ? | N | ? | Us: `/brand-identity`, `brand-architect`, `brand-systems`; the brand eval grades asking positioning questions first. Imp: `/impeccable init` records audience, voice and constraints in PRODUCT.md. UUPM: palettes and type per industry. FD: the skill proposes a subject and audience, but no brand system. |
| Structured design critique | Y | P | Y | ? | Y | Y | Y | ? | Us: `/design-audit` scores eight dimensions and prioritizes fixes. FD: "plan, review against the brief, build, critique". Imp: `/impeccable critique`, `/impeccable audit`. Hall: `hallmark audit`. wsh-ui: `/design-review`. ORO: multi-phase review. |
| Design system and tokens | Y | ? | Y | Y | P | Y | P | ? | Us: `/style-guide` outputs tokens, type scale and Tailwind or CSS config. Imp: `document`, `extract` write DESIGN.md. UUPM: design system files. Hall: design.md from `study`. wsh-ui: `design-system-patterns`, `/design-system-setup`. ORO: principles file. |
| Checks the rendered page in a browser | P | N | Y | ? | P | ? | Y | ? | Us: `/design-audit` accepts a URL but gives no browser-tool steps. Imp: `live` mode and `detect <url>`. Hall: `study <screenshot or URL>`. ORO: Playwright MCP. |
| Deterministic checks (no LLM) | N | N | Y | N | ? | ? | N | N | Us: none; contrast ratios in `/design-audit` are estimated by the model. Imp: 61 detector rules, `npx impeccable detect --json`. |
| Measured results (evals) | P | ? | P | ? | ? | ? | N | N | Us: 4 eval cases with a no-plugin baseline arm, no recorded scores. Imp: maker's post describes an internal with-and-without-skill eval framework, https://x.com/pbakaus/status/2044505743144194514. |

## Search log (what we tried)

- WebSearch `Claude Code plugin UI UX design frontend skill`, `anthropics claude-code frontend-design plugin`, `Cursor rules UI design frontend awesome-cursorrules design system` (shared with the LibreUIUX-Claude-Code pantry run).
- GitHub API `repos/<owner>/<repo>` for every row's stars and description; `repos/anthropics/skills/contents/skills` and the SKILL.md frontmatter of `frontend-design`, `brand-guidelines`, `canvas-design`, `theme-factory`, `web-artifacts-builder`.
- GitHub API READMEs read: pbakaus/impeccable, nextlevelbuilder/ui-ux-pro-max-skill, Nutlope/hallmark, wshobson/agents and `plugins/ui-design` folder listing, OneRedOak/claude-code-workflows `design-review/README.md`, VoltAgent/awesome-design-md, spencergoldade/cursor-designer, anthropics/claude-code `plugins/frontend-design` README and SKILL.md.
- Grep of those fetched READMEs for `bauhaus|swiss|dieter rams|vignelli|saul bass|art deco|memphis|brutalism|design history|movement`: one hit, "Brutalism" in UI UX Pro Max's style list.
- Not rows: google-labs-code/stitch-skills (8,405 stars; DESIGN.md tooling around the Stitch MCP server, closer to LibreUIUX's scope), superdesigndev/superdesign (repo says it is no longer actively maintained).
- Local: `claude plugin validate .` passes on main; `evals/` read case by case.
</content>
</invoke>
