# pr-integrator

This repository uses GitHub Actions to keep "subscribed" Python packages up-to-date in pyodide's monorepo. Similar to `regro-cf-autotick-bot`, it uses a cron job to identify recipes that do not point to the latest version of the package on PyPI. For these recipes, a PR is issued that updates the version, URL, and sha256. 


## Registering a package
1. Open a new PR which adds a `<PACKAGE-NAME>.json` to `packages/`, conforming to `package-info.schema.json`
2. Wait for tests to pass (and the PR to be merged)
3. `pyodide-pr-bot` will create a new PR to pyodide/pyodide when it detects a new version of your package.

If a workflow run has already seen this package version, it will not create a new PR. This means that PRs should not be created multiple times.

## Future ideas
- Issue a notification if the dependencies of a package change.
