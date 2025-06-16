---
title: 3. Test, Register and Publish Module
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
Once a Facets module is developed, it must be tested and registered in the Facets.cloud platform to ensure functionality, adherence to standards, and availability across projects.

## Directory Structure of a Module

Here is an example directory structure for a custom module:

```
custom_s3_module/
├── facets.yaml
├── main.tf
├── variables.tf
├── outputs.tf
```

***

## ** Step 1: Local Testing**

Local testing validates the Terraform logic and configurations before registering the module in Facets.

### Validate Directory

Validate the Terraform configuration for formatting, initialization, and security violations using Checkov. 

```Text bash
ftf validate-directory /path/to/module [OPTIONS]
```

Options:

- \--check-only: Verifies formatting without applying changes.

The command operates directly on the provided path without additional prompts.

***

## **Step 2: Registering the Module in Facets**

Once local testing is complete, the module can be registered in preview mode in Facets.cloud for testing. The module will be registered only in projects marked as testing projects.

### Facets FTF Login

You'll need to login to your control plane to register your module. To login:

```Text bash
ftf login [OPTIONS]
```

Prompts for Control Plane URL, Username, Token, and Profile. This information is stored under a specified profile for future interactions. Options:

- \-c, --control-plane-url: (prompt) The URL of the control plane. (e.g.`https://<your-company>.console.facets.cloud)`
- \-u, --username: (prompt) Your username.
- \-t, --token: (prompt) Your access token, input is hidden
- \-p, --profile: (prompt) The profile name to use for storing credentials, defaults to default.

Personal Token can be found in the User menu. Click your profile icon in the bottom left, then select 'Personal Token'.

### Register Your Module

```bash bash
ftf preview-module /path/to/module [OPTIONS]
```

Options:

- \-p, --profile: (prompt) Profile to use, defaults to default.
- \-a, --auto-create-intent: Automatically create intent if not exists.
- \-f, --publishable: Indicates whether the module is publishable for production.
- \-g, --git-repo-url: Git repository URL from where the code is taken.
- \-r, --git-ref: Git reference or branch name.

_Note:_ Registered Modules will be visible only in testing projects, allowing users to test the module in specific environments. Run the following script to mark any project as testing project (this action can be done from the UI in Project Settings as well).

```
curl -s https://facets-cloud.github.io/facets-schemas/scripts/allow_preview_modules.sh | bash -s -- -c <control plane url> -u <username> -t <token> -p <project-name> -a true
```

- Requirements: Bash (Unix-based shell), `curl` utility, `jq` utility (for parsing JSON responses)

***

## **Step 3: Publishing the Module in Facets**

After testing and preview registration, the module can be published for being available across all projects in the control plane. The command to publish the module is same as preview with few extra flags. 

### Publish the Module

```
ftf preview-module /path/to/module --publish -f
```

### Governance and Readiness Checks

Before publishing, check:

- All inputs and outputs conform to organisational standards.
- The module has been reviewed and approved by relevant stakeholders.
- Metadata in `facets.yaml` is accurate and complete.

***

## **Step 4: Validation in Facets**

After publishing, validate the module by creating a resource in a test project.

### Steps to Validate

1. Navigate to the "Blueprint" tab in the Facets UI.
2. Add the newly published resource to the project.
3. Deploy the blueprint and monitor the logs to ensure successful execution.

### Console Testing

Once the module is registered and the resource is created and enabled:

1. Perform a release for the resource.
2. Open the Terraform logs and expand the **PRE-BUILD** section.
3. Look for the following indicators:
   - **"Module Matched"**: Confirms that the resource matches a registered module. Example:
     ```plaintext
     Module Matched
     - Module: ../modules/1_input_instance/grafana_dashboard
     - Flavor: DEFAULT
     - Version: latest
     - Module Name: grafana_dashboard_vm-metrics
     ```
   - **"No per instance module matched"**: Indicates that no module matches the kind, flavor, or version of the resource. Example:
     ```plaintext
     No per instance module matched for ../stacks/infra-dev/aurora/disaster-recovery.json
     - Kind: infra-dev
     - Flavor: NONE
     - Version: 0.1
     ```

This verifies that the custom resource is correctly associated with the registered module.

### Troubleshooting

- Check Terraform logs for errors during deployment.
- Ensure the module inputs match the schema defined in `facets.yaml`.
- Validate outputs to ensure consistency with the declared outputs in `outputs.tf`.

***

By following these steps, Ops teams can confidently test, register, and publish custom Terraform modules in Facets.cloud, ensuring reliable and standardised infrastructure management.