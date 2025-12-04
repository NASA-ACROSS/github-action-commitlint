# github-action-lint-pr-title

Validates commit messages on PR titles using commitlint with conventional commits standard.

## Usage

```yaml
name: PR Title Check

on:
  pull_request:
    types: [opened, edited, synchronize, reopened]

jobs:
  commitlint:
    runs-on: ubuntu-latest
    steps:
      - uses: your-org/commitlint-action@v1
        with:
          message: ${{ github.event.pull_request.title }}
```

## Inputs
| Input | Required | Description |
|-------|----------|-------------|
| `message` | yes | Message to validate (typically `${{ github.event.pull_request.title }}`) |

## Validation Rules
Uses [@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/@commitlint/config-conventional):

### Valid formats:

`<type>`: your commit message

### Valid types:

`feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`
