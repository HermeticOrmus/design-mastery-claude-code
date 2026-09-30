# Pantry queue: design-mastery-claude-code

## How this fills

1. Read the latest competitor map, X mine and people mine.
2. Propose 5 to 8 Goal atoms that answer their themes. The Menu needs at least 3.
3. Each atom needs a Done predicate someone else can check on this repo, a surface, the evidence rows it answers, and a confidence (high, medium or low).
4. Save as `YYYY-MM-DD-pantry-queue.md`; the Menu reads the newest one.
5. Retire an atom only with a bullet under "Explicitly not stocked" of the form `<Title>: shipped, PR #N` or `<Title>: parked, <reason>`.

Sources for this run: [competitor map](2026-09-30-competitor-map.md), [X mine](2026-09-30-x-mine.md), [people mine](2026-09-30-people-mine.md) (no outside voices yet). "The plugin check" below means what CI runs: copy the tracked files without `.claude-plugin/marketplace.json` into a temp folder and run `claude plugin validate --strict` on it.

## Atoms

| # | Title | Done predicate | Surface | Evidence | Confidence |
|---|-------|----------------|---------|----------|------------|
| 1 | Compute contrast ratios with a script instead of estimating them (`contrast-check`) | `skills/design-principles/scripts/contrast.py` (Python standard library only) prints the WCAG 2 contrast ratio of two hex colors, so `python3 skills/design-principles/scripts/contrast.py 9CA3AF FFFFFF` prints 2.54:1 and says it fails AA for normal text; the design-principles SKILL.md Resources list it; `commands/design-audit.md` tells Claude to run it for each text and background pair it scores; the plugin check passes | repo | Matrix: Deterministic checks (no LLM) (Us N, Impeccable Y). X: tayarndt, pbakaus (detector claim). Repo: the design-audit-dashboard grader expects the 2.5:1 figure for #9CA3AF on white | high |
| 2 | Name the generic AI defaults and the principle each one breaks (`generic-defaults-reference`) | `skills/design-principles/references/generic-ai-defaults.md` exists and the SKILL.md Resources list it; each default it names (for example one accented word per headline, the same card grid on every page, gradient accents, a default font stack) maps to a principle already in this plugin and a Tailwind or CSS fix; `commands/design-audit.md` checks for them; each claim that a default is common cites a public source | repo | Map: Anthropic frontend-design (lists the clusters), Impeccable (anti-patterns), Hallmark (slop-test gates). Matrix: Aesthetic direction (avoids generic AI defaults) (Us P). X: emollick, michaelbrowk | high |
| 3 | Record a baseline run of the eval suite (`eval-baseline`) | `evals/BASELINE.md` lists, for each of the four cases, the with-plugin and no-plugin scores from one `claude plugin eval . --no-publish --json <file>` run, with the Claude Code version, the model and the runs per case; the README Evals section links it; `evals/results/` stays gitignored | repo | Matrix: Measured results (evals) (Us P). X: pbakaus (with-and-without-skill evals). Repo: the README says each case runs a no-plugin baseline, but no scores are recorded anywhere | medium |
| 4 | Add eval cases for style-guide and premium-landing (`eval-coverage`) | `evals/style-guide-*/` and `evals/premium-landing-*/` each hold a prompt.md with frontmatter and graders, one of them a `tool_used` grader for that command; the plugin check passes; `claude plugin eval . --case '<case name>' --runs 1 --no-publish` scores each new case | repo | Repo: the four cases cover brand, audit, masters and movements; none covers /style-guide or /premium-landing. Matrix: Measured results (evals), Design system and tokens | medium |
| 5 | Add a Susan Kare profile to design-masters (`susan-kare`) | `skills/design-masters/references/susan-kare.md` follows the layout of the other profiles (who she is, key works with dates, principles to borrow, applying them in UI work with Tailwind or CSS, common misreadings, quick reference); every date and attribution cites a source URL; the design-masters SKILL.md and the `design-master` agent list her | repo | Matrix: Design history: masters and movements (Us Y; no competitor in the map covers it). X: caglarispirli (a whole skill built around one master). Repo: README Contributing asks for "Additional designer deep-dives", and none of the seven profiles is a screen-interface designer | medium |
| 6 | Let design-audit read a running page through a browser MCP (`browser-audit`) | `commands/design-audit.md` has a section for when a Chrome DevTools or Playwright MCP server is connected: take a screenshot, read the computed colors and font sizes it scores, then audit; without one it keeps the description path; the README Usage section shows one example with a URL | repo | Map: OneRedOak design review, Impeccable (`live`, `detect <url>`). Matrix: Checks the rendered page in a browser (Us P). X: AnandChowdhary, gmchande | medium |
| 7 | Document the skills in Cursor, Codex and Gemini CLI (`other-harnesses`) | README gains an "Other agents" section with an install command for Cursor, Codex or Gemini CLI that the contributor ran (output pasted in the PR), and says what carries over (skills and their references) and what does not (agents, commands) | repo | Matrix: Other harnesses (Cursor, Codex, Gemini CLI) (Us N; Impeccable, UI UX Pro Max, Hallmark, wshobson/agents Y). X: abduzeedo | medium |

## Explicitly not stocked (and why)

- A full anti-pattern detector like Impeccable's 61 rules: large; atom 1 starts with the one check the audit already scores. Restock if feedback or routing-miss issues ask for more.
- Keeping the LibreUIUX copy of this plugin in sync: that copy lives in LibreUIUX-Claude-Code, so the work belongs to that repo's pantry.
- Scoring this plugin against competitors' plugins on the same prompts: needs installing and running other people's plugins, which a contributor cannot verify from this repo alone.
</content>
</invoke>
