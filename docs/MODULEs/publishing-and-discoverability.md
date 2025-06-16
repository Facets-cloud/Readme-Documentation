---
title: Publishing a Module
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
Once your module is fully implemented and tested locally, it can be published to Facets so others can discover and reuse it. Use the [detailed guide](https://github.com/Facets-cloud/module-development-cli) to know how the module can be published using Facets CLI.

### Versioning Strategy

Facets modules use a versioned structure similar to APIs. You can continue updating a version (like `1.0`) as long as all changes are **backward compatible**. If you make **breaking changes**—such as removing inputs or changing the shape of existing ones—publish a **new version folder** (e.g., `2.0`).

> 🧠 Think of versioning in Facets like API versioning:
> 
> As long as your inputs and behavior are backward compatible, you can keep publishing to the same version.

***

### Readiness Checklist

Before you publish, ensure your module is clean, validated, and ready to use.

**✅ Module Publishing Checklist**

- [ ] All inputs are defined in `variables.tf` with clear descriptions and types.  
- [ ] The `spec` section in `variables.tf` is a valid **JSON Schema**, enabling Facets to generate forms automatically.  
- [ ] Terraform logic in `main.tf` relies only on:
  - `var.inputs.<field>` for user-supplied values
  - `var.instance_name` and `var.environment.unique_name` for naming
- [ ] The module contains **no provider blocks**, **no outputs**, and uses only defined variables.  
- [ ] You’ve tested the module using the CLI `ftf validate` command.  
- [ ] You’ve bumped the version folder if breaking changes were made.  

> 💡 Pro tip: Use Git branches or tags to manage multiple versions during development.

***

### Module Versioning and Adoption

Each module version is immutable once published. When a new version is created under the same Intent and Flavor, users can choose to adopt it at their own pace. Projects using older versions won’t be auto-upgraded. This ensures:

- Stability – Active environments aren't affected by upstream changes.
- Control – Teams can evaluate changes before rolling them out.

To adopt a new version, navigate to the project using the module, select the new version from dropdown and save & apply the changes to update the environment.

***

### CI for Modules

All modules should be tested via CI before publishing. Your CI pipeline should run `ftf validate` and ensure the module adheres to Facets’ requirements—particularly around schema, naming, and file structure. This keeps the published module stable and discoverable.

Next up, we will learn how to set up a CI pipeline for inner-sourced modules to automate testing and publishing before they’re used across teams.