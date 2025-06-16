---
title: Continuous Integration
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This guide outlines a clean and consistent CI workflow to develop, test, and publish Terraform modules using GitHub Actions and the Facets control plane.

## CI Workflow

### 1. Development

* DevOps engineers create or update modules in a **feature branch** off `main`.
* **No preview is triggered** at this stage.
* Modules can be tested locally or **previewed from local** (explained later).

### 2. Preview on Pull Request

* When a **PR is raised against`main`** , CI automatically:
  * Registers the module as a **preview** in the Facets control plane.
  * This enables teams to test the module in real environments.
* Any update to the PR will update the preview module automatically.

### 3. Publish on Merge

* Once approved, merging the PR to `main` triggers CI to:
  * **Publish the module** in the Facets control plane.
  * Mark it as **production-ready** and available across projects.

<br />

<Image align="center" src="https://files.readme.io/6c3225ad276e2ed9d04277822f2e901593fec95fd0bdfeaed18f8613817ad767-Screenshot_2025-04-11_at_12.39.46_AM.png" />

***

## Sample GitHub Actions

### Preview on PR to Main

```yaml
name: "Preview Module on PR to Main"

on:
  pull_request:
    branches: [main]
    paths: ["**/*.yaml", "**/*.tf"]
  workflow_dispatch:

jobs:
  preview:
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

### Publish on Merge to Main

```yaml
name: "Publish Module from Main"

on:
  push:
    branches: [main]
    paths: ["**/*.yaml", "**/*.tf"]
  workflow_dispatch:

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - name: Run Facets Module Publish Action
        uses: Facets-cloud/github-actions/module-preview-action@master
        with:
          control_plane_url: ${{ secrets.CONTROL_PLANE_URL }}
          username: ${{ secrets.FACETS_USERNAME }}
          token: ${{ secrets.FACETS_API_TOKEN }}
          all-modules: false
          publish: true
          publishable: true
          auto-create-intent: true
```

***

## ✅ Key Principles

* **Preview only on PR:** Keeps the control plane clean until a module is ready for review.
* **Main is production-ready:** Modules in `main` are immediately usable.
* **Modules can be tested/previewed locally** before a PR is opened.
* **Automation ensures consistency** across all modules.

***

## 🔗 Using another CI or VCS?

Check out the [GitHub Action source](https://github.com/Facets-cloud/github-actions/tree/master/module-preview-action) to replicate this flow in other systems.
