# Changesets

Create a changeset for each user-facing change with `pnpm changeset`. Commit the generated Markdown file with the code change. The release process consumes these files with `pnpm changeset:version` and updates `package.json` and `CHANGELOG.md`.

The GitHub changelog generator uses `GITHUB_REPOSITORY=owner/repo` and `GITHUB_TOKEN` when generating a release. In GitHub Actions, `GITHUB_REPOSITORY` is provided automatically. Locally, set both variables before running `pnpm changeset:version`.
