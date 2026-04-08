# Contributing to Prism.js ES|QL

## Commit Message Convention

This project uses [Conventional Commits](https://www.conventionalcommits.org/) following the **Angular** preset. Releases are automated via [semantic-release](https://github.com/semantic-release/semantic-release), so commit messages directly determine version bumps.

### Format

```
<type>(<optional scope>): <description>

[optional body]

[optional footer(s)]
```

### Commit Types

| Type       | Description                          | Version Bump |
|------------|--------------------------------------|--------------|
| `feat`     | A new feature                        | Minor        |
| `fix`      | A bug fix                            | Patch        |
| `refactor` | Code change (no new feature or fix)  | Patch        |
| `perf`     | Performance improvement              | Patch        |
| `build`    | Build system or dependency changes   | Patch        |
| `chore`    | Maintenance tasks                    | Patch        |
| `revert`   | Reverts a previous commit            | Patch        |
| `docs`     | Documentation only                   | No release   |

### Breaking Changes

To trigger a **major** version bump, include `BREAKING CHANGE` or `BREAKING CHANGES` in the commit footer:

```
feat: Add new command highligting

BREAKING CHANGE: The exports of the package have changed.
```

## Merging Pull Requests

When merging a pull request, select **squash and merge**. This collapses all commits into a single commit on `main`, keeping the history clean.

Before completing the merge, verify that the squash commit message follows the [conventional commit format](#commit-message-convention) — this is critical because `semantic-release` reads the commit messages on `main` to determine version bumps and generate changelogs. A malformed merge commit will not trigger a release or may produce an incorrect one.

## Releasing (Maintainers only)

Releases are fully automated via [semantic-release](https://github.com/semantic-release/semantic-release). There is no need to manually bump versions, tag commits, or publish to npm — the tooling handles all of it based on the commit history.

### How it works

1. `semantic-release` analyzes all commits on the target branch since the last release.
2. It determines the next version based on the [commit message types](#commit-message-convention).
3. It generates a changelog, creates a GitHub release, and publishes to npm with provenance.

### Triggering a release

The release is triggered manually via the **Release** GitHub Actions workflow (`workflow_dispatch`):

1. Go to **Actions** > **Release** in the GitHub repository.
2. Click **Run workflow**.
3. Select the branch to release from (defaults to `main`).
4. The workflow will lint, format-check, build, and test the code before releasing.

### Dry run

To preview what the next release would look like without actually publishing:

```bash
yarn semantic-release:dry-run
```

This runs `semantic-release --dry-run` locally and logs the version that would be released and the changelog that would be generated.
