Commit And Prompt Tracking Rules

1. Collect prompt context continuously
- Keep a running record of the user prompts and follow-up instructions that directly drive code changes.
- Treat later clarifications, corrections, and constraints as part of the effective prompt for the resulting change.
- Do not include unrelated chat or planning text that did not affect the implementation.

2. Commit format
- When the user asks for a commit, use a semantic commit message.
- Prefer: feat(scope): ..., fix(scope): ..., refactor(scope): ..., chore(scope): ..., docs(scope): ...
- Choose the type and scope based on the actual code changes in the commit, not the original broad goal.

3. Prompt selection for commits
- When preparing a commit, propose the prompt lines most likely to belong in the commit body.
- Let the user choose which prompts to include when that choice is ambiguous or when multiple prompts contributed.
- If the user does not want to choose, include only the prompt lines that are strongly attributable to the committed changes.
- If a prompt was later corrected by the user, prefer the corrected version.
- If the relationship is uncertain, omit that prompt rather than guessing.

4. Commit body
- Include an `AI prompt:` section in the commit body when the commit was driven by user prompts.
- Under `AI prompt:`, include the most relevant prompt text that actually led to the committed changes.
- Merge related prompt fragments when they belong to the same commit.
- Exclude duplicated, stale, or clearly superseded prompt text unless it still materially affected the final implementation.

5. Privacy and safety
- Do not include secrets, private URLs, tokens, personal data, or sensitive internal identifiers in commit messages.
- If seed/sample/demo data contains private information, remove or sanitize it before commit when requested.

6. Working style
- Before committing, review the actual diff and make sure the semantic subject matches the code being committed.
- If the working tree contains mixed concerns, prefer splitting into separate commits when practical.
- If the user wants a single commit, summarize the dominant concern in the subject and include the selected prompts in the body.

Commit template

<type>(<scope>): <summary>

AI prompt:
- <prompt item 1>
- <prompt item 2>
- <prompt item 3>
