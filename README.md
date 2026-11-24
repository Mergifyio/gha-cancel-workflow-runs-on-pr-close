# gha-cancel-workflow-runs-on-pr-close

GitHub Action to cancel workflow runs when a pull request is closed.

### Usage

```yaml
name: Cancel workflows on PR close

on:
  pull_request:
    types: [closed]

permissions:
  actions: write

jobs:
  cancel:
    runs-on: ubuntu-latest
    steps:
      - name: Cancel related runs
        uses: Mergifyio/gha-cancel-workflow-runs-on-pr-close@v1
```

### Push runs of a merge queue draft

To also cancel the `push` runs on the branch of a merge queue draft closed unmerged, name its prefix in
`push-branch-prefixes`, one per line:

```yaml
      - name: Cancel related runs
        uses: Mergifyio/gha-cancel-workflow-runs-on-pr-close@v1
        with:
          push-branch-prefixes: mergify/merge-queue/
```
