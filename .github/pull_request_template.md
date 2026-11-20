<!--
  Pull request template (works on GitHub and Azure DevOps Server).
  Put a copy in the repo at:
    GitHub:        .github/pull_request_template.md
    Azure DevOps:  .azuredevops/pull_request_template.md
  The text below fills the description box of every new pull request. Delete these comment lines.
-->

## What this changes

<!-- One or two sentences, in plain words. Name the item: SR-4, F-3. -->

## Why

<!-- The problem or requirement this solves. Link the work item: #123 (Azure DevOps) or the issue. -->

## How it was tested

- [ ] Unit tests pass (the pre-push hook ran them)
- [ ] Tried it by hand: <!-- what you clicked or ran -->

## Needs extra review?

- [ ] Changes the data model, API contract, sign-in, integrations or deployment (Architect review)
- [ ] Touches member data or secrets (security review)

## Checklist

- [ ] Branch name starts with the item ID (`sr-4-online-dispute`)
- [ ] Made-up data only in tests and examples
- [ ] No secrets in the code (they live in `.env` or the key vault)
