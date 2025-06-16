---
title: 2. Types of Releases
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
Facets offers multiple types of releases, each designed for specific deployment needs. Below is a breakdown of each type, including its functionality, common use cases, and benefits.

<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>

        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }

        th, td {
            border: 1px solid #ccc;
            padding: 12px;
            text-align: left;
        }

        th {
            background-color: #e0e0e0;
            color: white;
        }

        tr:nth-child(even) {
            background-color: #f2f2f2;
        }

        tr:hover {
            background-color: #e0e0e0;
        }
    </style>
</head>
<body>
    <table>
        <thead>
            <tr>
                <th>Release Type</th>
                <th>Functionality</th>
                <th>Use Case</th>
                <th>Benefits</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Full Release</td>
                <td>Executes a complete Terraform apply to synchronize all pending changes in an environment.</td>
                <td>Ideal for ensuring the environment remains up to date by applying all accumulated modifications.</td>
                <td>Ensures consistency across the environment with minimal manual intervention.</td>
            </tr>
            <tr>
                <td>Selective Release</td>
                <td>Applies targeted Terraform changes to specific components or services.</td>
                <td>Used for urgent hotfixes or incremental updates without affecting unrelated components.</td>
                <td>Reduces risk by limiting changes to specific areas, improving stability and control.</td>
            </tr>
            <tr>
                <td>Custom Release</td>
                <td>Enables users to execute custom Terraform commands for advanced deployment control.</td>
                <td>Useful for power users who need greater flexibility beyond standard release types.</td>
                <td>Provides granular control over infrastructure changes, ensuring adaptability to unique scenarios.</td>
            </tr>
          <tr>
                <td>Plan Release</td>
                <td>Generates a preview of proposed changes without applying them, providing a detailed comparison of the current and desired states.</td>
                <td>Used for validation and review before execution to minimize unintended modifications.</td>
                <td>Improves transparency, allowing teams to assess potential impacts before committing changes.</td>
            </tr>
            <tr>
                <td>Launch Release</td>
                <td>Deploys all necessary infrastructure to initialize a new environment from scratch.</td>
                <td>Used for setting up new cloud environments for applications or services.</td>
                <td>Automates the provisioning process, accelerating environment setup with predefined configurations.</td>
            </tr>
            <tr>
                <td>Destroy Release</td>
                <td>Deprovisions and removes all resources managed by Facets in an environment.</td>
                <td>Used for decommissioning environments that are no longer needed.</td>
                <td>Ensures proper cleanup, optimizing cloud resource usage and cost management.</td>
            </tr>
        </tbody>
    </table>
</body>
</html> 
`}</HTMLBlock>

<br />

## Best Practices

To ensure a smooth and efficient release process, follow these best practices:

* **Use Plan Releases Before Applying Changes:** Always review proposed changes to detect unintended modifications and potential misconfigurations.
* **Limit Selective Releases to Critical Fixes:** Excessive selective changes can cause configuration drift, leading to inconsistencies over time.
* **Automate Full Releases for Stability:** Schedule regular full releases to maintain infrastructure consistency and prevent untracked changes.
* **Backup Before Destroy Release:** Always take snapshots or backups before deprovisioning an environment to avoid data loss.
* **Test Custom Releases in a Staging Environment:** Execute custom commands in a non-production environment first to validate their impact.
* **Implement Access Controls:** Define and enforce permissions based on user roles to prevent unauthorized or accidental modifications.
* **Setup necessary notification:** Setup necessary notifications using the deployment status update subscription to be informed about all the releases.

## Troubleshooting

1. **Release Stuck or Taking Too Long:** Check the logs for execution status and potential errors. Verify network connectivity and API response times. Ensure that Terraform state is not locked due to another ongoing release.
2. **Failed Release Execution:** Inspect error messages for root causes, such as missing variables or incorrect configurations. Ensure IAM permissions are correctly set for the executing user. Validate that the target environment is accessible and not in a restricted state.
3. **Selective Release Not Applying Changes:** Verify that the correct resources are targeted in the configuration. Check for dependency conflicts preventing the changes from being applied.
4. **Plan Release Showing Unexpected Changes:** Ensure that the Terraform state is correctly synchronized with the actual infrastructure. Review previous deployments to identify any untracked modifications.
5. **Destroy Release Failing to Remove Resources:** Check for dependencies preventing deletion, such as manually created resources. Verify that Terraform has the correct permissions to deprovision all resources.
6. **Launch Release Not Creating Expected Resources:** Confirm that all required configurations and templates are correctly defined. Validate the cloud provider’s service limits and quotas.
