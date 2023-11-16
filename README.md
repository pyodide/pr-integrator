# pyodide-recipe-action

This repository uses GitHub Actions to keep "subscribed" Python packages up-to-date in pyodide's monorepo. Similar to `regro-cf-autotick-bot`, it uses a cron job to identify recipes that do not point to the latest version of the package on PyPI. For these recipes, a PR is issued that updates the version, URL, and sha256. 


## Future ideas
- Issue a notification if the dependencies of a package change.