---
title: Continuous Integration to Develop Modules Faster
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Overview

This document outlines a **suggested CI workflow **for managing custom Terraform modules, from development through deployment, ensuring rigorous testing before production release. This approach can be modified based on your specific use case and organisational requirements. By automating module registration, testing, and publishing, CI enables efficient development, accelerates testing cycles, and ensures seamless module management across projects.

## CI Workflow

A central Git repository is maintained for all Terraform modules. Each DevOps engineer developing a module creates a feature branch based out of the main branch (Main branch always contains production-ready modules).

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/763a3e2f0fd8b4a3c4786e45222fd83fdc48d249569c78d115298420645d28e5-Screenshot_2025-04-10_at_2.51.02_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


**1. Development & Preview Registration**

- Devops engineer creates custom terraform module locally and maintains a feature branch based out of the main branch for development.
- Any commit to the feature branch triggers the CI pipeline (which includes the registration of the module in the control plane)
- The module is automatically registered in preview mode (cannot be published) within the control plane.
- DevOps engineer can test the module in test projects.

**2. Pull Request & Review**

- Once the module is tested and validated, a PR is raised against main.
- Updates to the PR trigger CI, updating the preview module in the control plane.

**3. Merging to Main & Production Deployment**

- When the PR is merged to main, module is published in the control plane to be used across all projects.
- Once published (through CD or otherwise), signifies the module as production-ready.

## Sample CI File: Preview Module on PR Request to Main (Github Action)

```yaml
name: "Preview Module on PR Request to Main"

on:
  pull_request:
    paths:
      - '**/*.yaml'
      - '**/*.tf'
    branches:
      - main

  workflow_dispatch:  # ✅ Manual trigger

jobs:
  test-action:
    runs-on: ubuntu-latest
    steps:

      - name: Run Facets Module Preview Action
        uses: Facets-cloud/github-actions/module-preview-action@master
        with:
          control_plane_url: ${{ secrets.CONTROL_PLANE_URL }}
          username: ${{ secrets.FACETS_USERNAME }}
          token: ${{ secrets.FACETS_API_TOKEN }}
          dry-run: false
          all-modules: false
          auto-create-intent: true
          publish: false
          publishable: false
```

## Sample CI File: Publish Module from Main (Github Action)

```yaml
name: "Publish Module from Main"
on:
  push:
    branches:
      - main
    paths:
      - '**/*.yaml'
      - '**/*.tf'

  workflow_dispatch:  # ✅ Manual trigger

jobs:
  test-action:
    runs-on: ubuntu-latest
    steps:
      - name: Run Facets Module Action to publish modules
        uses: Facets-cloud/github-actions/module-preview-action@master
        with:
          control_plane_url: ${{ secrets.CONTROL_PLANE_URL }}
          username: ${{ secrets.FACETS_USERNAME }}
          token: ${{ secrets.FACETS_API_TOKEN }}
          all-modules: false
          publish: true # This is marked true if we want direct publishing.
          publishable: true
          auto-create-intent: true
```

## Key Principles

- No long-lived feature branches: Modules should be merged as soon as they are ready.
- Main is always production-ready: Any module in main is immediately available for use.
- Continuous updates in preview: PR updates continuously update the preview module.
- Automation for consistency: CI pipeline ensures every module follows the same registration and deployment process.

By following this workflow, teams can efficiently develop and deploy Terraform modules while maintaining quality, consistency, and minimal overhead.