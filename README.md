# github-action-commitlint

Validates commit messages on PR titles using commitlint with conventional commits standard.

## Usage

```yaml
name: Commit Lint PR Title

on:
  pull_request:
    types: [opened, edited, synchronize, reopened]

jobs:
  commitlint:
    runs-on: ubuntu-latest
    steps:
      - uses: NASA-ACROSS/github-action-commitlint@v1
```

## Inputs

| Input     | Required | Description                                                                          |
| --------- | -------- | ------------------------------------------------------------------------------------ |
| `message` | no       | Message to validate (defaults to PR title: `${{ github.event.pull_request.title }}`) |

## Validation Rules

Uses [@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/config-conventional):

### Valid formats

`<type>`: your commit message

### Valid types

`feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`
