# Menu: design-mastery-claude-code

Queue: 2026-09-30-pantry-queue.md
Counts: open 7, in flight 0, shipped 0, parked 0, dropped 0, needs fixing 0

## Steer

- none

## Up next

**contrast-check**: Compute contrast ratios with a script instead of estimating them (`contrast-check`) (queue #1, high, repo, since 2026-09-30)

- Done when: `skills/design-principles/scripts/contrast.py` (Python standard library only) prints the WCAG 2 contrast ratio of two hex colors, so `python3 skills/design-principles/scripts/contrast.py 9CA3AF FFFFFF` prints 2.54:1 and says it fails AA for normal text; the design-principles SKILL.md Resources list it; `commands/design-audit.md` tells Claude to run it for each text and background pair it scores; the plugin check passes
- Verify on: repo
- Evidence: Matrix: Deterministic checks (no LLM) (Us N, Impeccable Y). X: tayarndt, pbakaus (detector claim). Repo: the design-audit-dashboard grader expects the 2.5:1 figure for #9CA3AF on white
- Issue: none yet (promote after merge)
- Order: contrast-check, generic-defaults-reference, browser-audit, other-harnesses, susan-kare, eval-baseline, eval-coverage
- Tie: contrast-check over generic-defaults-reference, by key order (jev off)

## Atoms

| Key | Title | State | Confidence | Class | Since | Queue # | Issue | Because |
|-----|-------|-------|------------|-------|-------|---------|-------|---------|
| browser-audit | Let design-audit read a running page through a browser MCP (`browser-audit`) | open | medium | repo | 2026-09-30 | 6 | - | - |
| contrast-check | Compute contrast ratios with a script instead of estimating them (`contrast-check`) | open | high | repo | 2026-09-30 | 1 | - | - |
| eval-baseline | Record a baseline run of the eval suite (`eval-baseline`) | open | medium | eval | 2026-09-30 | 3 | #4 | - |
| eval-coverage | Add eval cases for style-guide and premium-landing (`eval-coverage`) | open | medium | eval | 2026-09-30 | 4 | - | - |
| generic-defaults-reference | Name the generic AI defaults and the principle each one breaks (`generic-defaults-reference`) | open | high | repo | 2026-09-30 | 2 | - | - |
| other-harnesses | Document the skills in Cursor, Codex and Gemini CLI (`other-harnesses`) | open | medium | repo | 2026-09-30 | 7 | - | - |
| susan-kare | Add a Susan Kare profile to design-masters (`susan-kare`) | open | medium | repo | 2026-09-30 | 5 | - | - |

## Retired

| Key | Title | State | Since | Issue | Because |
|-----|-------|-------|-------|-------|---------|
| none | | | | | |

## Notes

- none
