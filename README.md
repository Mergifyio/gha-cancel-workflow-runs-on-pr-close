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
        uses: Mergifyio/gha-cancel-on-pr-close@v1
```