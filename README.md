# txtcv actions

This repository provides a reusable GitHub Action definition for validating JSON Resume
CV files using the [`txtcv`](https://github.com/txtcv/cli) command-line tool.

## Usage

Use the `validate` action to validate JSON CV files against the JSON Resume schema.
Here's an example:

```yaml
name: Validate CV

on:
  push:
    branches:
      - main

jobs:
  validate:
    runs-on: macos-latest
    steps:
      - uses: txtcv/actions-validate@v1
        with:
          cv_path: cv.json
```

## Notes

- Homebrew must be available on the runner. GitHub-hosted macOS and Ubuntu runners
  include Homebrew by default; ensure it is available on self-hosted runners before
  using these actions.
- The actions currently target Linux and macOS runners. Ensure a matching Homebrew
  bottle exists before enabling them on Windows.
