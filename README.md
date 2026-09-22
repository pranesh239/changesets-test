# React + TypeScript + Vite

## Changelogs

Use Node 24 (`nvm use`) and pnpm. For each user-facing change, run `pnpm changeset`, select `changesets`, choose the appropriate patch/minor/major bump, and commit the generated `.changeset/*.md` file with your change. Run `pnpm changeset:status` to preview pending releases.

When preparing a release, set `GITHUB_REPOSITORY=owner/repo` and `GITHUB_TOKEN` in your environment, then run `pnpm changeset:version`. This consumes pending changesets, bumps the private app's version, and updates `CHANGELOG.md` with GitHub links. Commit the version and changelog changes together. GitHub Actions provides `GITHUB_REPOSITORY` automatically; a local run needs it set explicitly. The token needs permission to read the repository and user information used for release links.

This repository is on `main` but has no commits yet. Create the initial commit before using Git-based Changesets commands such as `changeset:status`. Add a GitHub remote before generating GitHub-linked changelogs, and update `.changeset/config.json` if your default branch is not `main`.

This template provides a minimal setup to get React working in Vite with HMR and some Oxlint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is enabled on this template. See [this documentation](https://react.dev/learn/react-compiler) for more information.

Note: This will impact Vite dev & build performances.
You can also try [the experimental native React Compiler support in plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md#rust-react-compiler) by using `compiler: true` in the plugin options instead of using the Babel plugin.

## Expanding the Oxlint configuration

If you are developing a production application, we recommend enabling type-aware lint rules by installing `oxlint-tsgolint` and editing `.oxlintrc.json`:

```json
{
  "$schema": "./node_modules/oxlint/configuration_schema.json",
  "plugins": ["react", "typescript", "oxc"],
  "options": {
    "typeAware": true
  },
  "rules": {
    "react/rules-of-hooks": "error",
    "react/only-export-components": ["warn", { "allowConstantExport": true }]
  }
}
```

See the [Oxlint rules documentation](https://oxc.rs/docs/guide/usage/linter/rules) for the full list of rules and categories.
