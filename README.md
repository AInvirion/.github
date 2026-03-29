# AInvirion Organization Configuration

This repository contains organization-wide GitHub configurations and reusable workflows for AInvirion.

## Reusable Workflows

### CLA Assistant

Enforces Contributor Assignment Agreement signing on pull requests.

**Usage:** Add this workflow to any repo that requires CLA:

```yaml
# .github/workflows/cla.yml
name: CLA Assistant

on:
  issue_comment:
    types: [created]
  pull_request_target:
    types: [opened, synchronize, reopened]

permissions:
  contents: write
  pull-requests: write
  actions: read

jobs:
  cla:
    uses: AInvirion/.github/.github/workflows/cla.yml@main
    secrets:
      CLA_TOKEN: ${{ secrets.CLA_TOKEN }}
```

**Requirements:**
- `CLA_TOKEN` organization secret with:
  - Contents: Read and write
  - Pull requests: Read and write
  - Metadata: Read

## License

Copyright (c) 2025-2026 AInvirion. All Rights Reserved.
