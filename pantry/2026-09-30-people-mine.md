# People mine: design-mastery-claude-code

What people who use the product said in its own public places: issues, issue comments, discussions, pull requests, and forks that changed something. Optional third pantry source; a product with no outside voices yet leaves the Hits table empty and says so.

## How this fills

1. List the product's own repos (the kitchen law names them).
2. Read what people outside the maintainers wrote since the last run: issues (the `feedback` label first), issue comments, discussions and their comments, pull requests, and forks with commits ahead of the default branch.
3. One row per voice. Quote a short snippet and link the exact issue, comment, discussion, PR or commit. Say whether they gave credit consent when the source has a consent box.
4. Tag each row with the capability it is about, in the same words as the competitor map's matrix, so the queue can cite it next to competitor and X rows.
5. Never count stars as feedback, never infer sentiment the person did not state, never paraphrase a number. Maintainers' own issues are not voices.
6. Save as `YYYY-MM-DD-people-mine.md` beside the other dated files (keep this TEMPLATE).

## Hits

No outside voices yet: every issue, comment and pull request in this repo is the maintainer's, there are no discussions, and there are no forks.

| Repo | Kind (bug/feature/question/praise/contribution) | Snippet | Link | Theme (matrix capability) | Credit consent |
|------|--------------------------------------------------|---------|------|---------------------------|----------------|
|  |  |  |  |  |  |

## Read log (what we read)

- Issues and pull requests, all states (`gh api repos/HermeticOrmus/design-mastery-claude-code/issues?state=all`): #1 to #3, all opened by the maintainer (HermeticOrmus).
- Issue comments (`issues/comments`): one, by the maintainer on #1.
- Pull request review comments (`pulls/comments`): none.
- Commit comments (`repos/.../comments`): none.
- Discussions (GraphQL `repository.discussions`): enabled, 0 discussions. Categories: Announcements, General, Ideas, Polls, Q&A, Show and tell.
- `feedback` label: exists, no issues carry it.
- Forks (`repos/.../forks`): 0.
- Related, not this repo: the same plugin ships inside LibreUIUX-Claude-Code, whose people mine has one fork with commits ahead that proposes a design-to-code plugin next to design-mastery. That voice belongs to that repo's pantry and is not counted here.
- Stars are not counted as feedback.
</content>
</invoke>
