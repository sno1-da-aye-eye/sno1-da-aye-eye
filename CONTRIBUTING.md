# Contributing and Learning Notes

This repository is also a learning notebook. Changes should be easy to understand, review, and undo.

## Suggested workflow

1. Write down the problem or question.
2. Make the smallest useful change.
3. Explain the reason in the commit message or pull request.
4. Test or inspect the result.
5. Record what was learned.
6. Keep uncertain ideas labelled as proposals rather than facts.

## Commit style

Use short, descriptive messages such as:

- `docs: clarify memory boundary`
- `feat: add provider interface`
- `fix: handle cancelled requests`
- `test: cover memory deletion`
- `refactor: separate orchestration from provider`

## Decision notes

When a choice may affect the project’s future, record:

- The decision.
- The alternatives considered.
- Why the decision was made.
- What would cause it to be revisited.

## Safety rule

Do not add secrets, API keys, private tokens, personal data, or production credentials to the repository. Use environment variables and documented examples instead.

Do not introduce autonomous code modification, unrestricted tool access, or deployment changes without a separate proposal and explicit review.
