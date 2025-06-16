---
title: Adding and Managing Secrets and Variables
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
This guide provides a step-by-step process for adding and managing secrets and variables at both the project and environment levels within Facets.cloud. Properly managing secrets and variables ensures secure and efficient configuration for your projects.

### Why Manage Secrets and Variables?

Security: Protect sensitive information such as API keys, credentials, and tokens from unauthorized access by encrypting secrets at rest and in transit.

Environment-Specific Flexibility: Define variables and secrets that can be overridden per environment to accommodate testing, staging, and production needs.

Dynamic Configuration: Enable resources to dynamically reference secrets and variables, reducing the need for hardcoded values and simplifying code maintenance.

Scalability: Centralized management of secrets and variables allows for consistent configurations across multiple environments and projects.

Auditability: Track changes to secrets and variables with audit logs, ensuring compliance with security and operational policies.

Error Reduction: Auto-injection of secrets and variables minimizes configuration errors and accelerates deployment processes.

***

## How to Add Secrets and Variables in a Project?

1. Open the Projects Tab: Navigate to the Projects section and select the desired project.
2. Access the Secrets and Variables Section:
3. Click on the Secrets and Variables tab in the project’s settings.
4. Define a New Secret or Variable: Click on the Define New button.
5. In the pop-up that appears:
   1. For Secrets:
      1. Choose Secret as the type.
      2. Provide a unique Name for the secret. It is recommended to set the values at the environment level for better security and flexibility.
   2. For Variables:
      1. Choose Variable as the type.
      2. Enter a unique Name and specify the Default Value.
6. Auto-Inject into Resources: Check the Auto Inject checkbox to automatically add the key-value pair to all resources in the Blueprint.
7. Add Multiple Entries: Use the Add More button to define multiple secrets or variables in one session.
8. Save Changes: Once all entries are defined, click Save to add them to the project.

***

## How to Override Secrets and Variables for an Environment?

1. Open the Projects Tab: Navigate to the Projects section and select the desired project.
2. Access the Secrets and Variables Section: Click on the Secrets and Variables tab to view all defined entries.
3. Edit Environment Variables: Click on the Edit Env. Variables button. 
4. In the window that appears, select the environment where the values need to be updated.
5. Modify Environment-Specific Values: Locate the entry you wish to modify and click the Edit icon beside it.
6. Update the Environment Value and confirm changes by clicking the tick icon.
7. Save Changes:

After updating all necessary values, click Save Changes to apply the modifications.

<br />

***

## FAQ

1: What is the difference between a secret and a variable?

Secret: Used for storing sensitive information like API keys or passwords. These are encrypted and not visible in plain text.

Variable: Used for storing non-sensitive configuration values. These are visible in plain text and can have default values.

2: Can I override a project-level secret or variable in a specific environment?

Yes, you can override project-level secrets or variables by defining environment-specific values. The environment-level values take precedence.

3: How does auto-injection work?

When the auto-injection checkbox is enabled, the key-value pair of the secret or variable is automatically added to all resources in the Blueprint without requiring manual configuration.

4: Are secrets and variables versioned?

Yes, changes to secrets and variables are tracked with audit trails, allowing you to view their history and revert if necessary.

5: How do I securely share secrets across multiple projects?

Use Facets.cloud’s shared secret functionality or replicate the same secret definitions in each project while maintaining their encrypted state.

6: What happens if I delete a secret or variable?

Deleting a secret or variable removes it from the project and any associated resources. Ensure you review dependencies before deletion to avoid breaking configurations.
