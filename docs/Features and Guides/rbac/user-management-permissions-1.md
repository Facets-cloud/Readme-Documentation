---
title: User Management Permissions
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
RBAC roles defined in Facets have a list of associated permissions that grant the user privileges to perform certain actions. This page provides a comprehensive overview of the permissions available within the system.You can find a comprehensive list of permissions listed below.

### Common Permissions:

1. **Write:** Grants permission to create and edit entities.
2. **Delete:** Grants permission to delete entities.

### List of Permissions:

The table below categorizes permissions by their respective areas, detailing the capabilities granted under each category.

* **Category:** Represents the functional area or entity within the system.
* **Write:** Indicates whether `write` permission is available within the category.
* **Delete:** Indicates whether `delete` permission is available within the category.
* **Special Permissions:** Lists any additional specific permissions that provide more granular control over actions within the category.

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
            background: white;
        }
        th, td {
            border: 1px solid #ccc;
            padding: 10px;
            text-align: left;
        }
        th {
            background: #e0e0e0;
        }
        tr:nth-child(even) {
            background: #f4f4f4;
        }
    </style>
</head>
<body>
    <table>
        <thead>
            <tr>
                <th>Category</th>
                <th>Write</th>
                <th>Delete</th>
                <th>Special Permissions</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><b>Accounts</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Alerts</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>Configure:</strong> Grants permission to configure the alerts.</td>
            </tr>
          	<tr>
                <td><b>Application Rolling</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>Restart:</strong> Grants permission to initiate a rolling restart for an application.</td>
            </tr>
            <tr>
                <td><b>Artifact CI</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Artifacts</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Artifactory</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
          	<tr>
                <td><b>Audit Logs</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>View:</strong> Grants permission to view audit logs.</td>
            </tr>
          	<tr>
                <td rowspan="2"><b>Blue-Green/Canary</b></td>
                <td rowspan="2">No</td>
                <td rowspan="2">No</td>
                <td><strong>Promote:</strong> Grants permission to promote preview application deployment.</td>
            </tr>
            <tr>
                <td><strong>Abort:</strong> Grants permission to abort preview application deployment.</td>
            </tr>
            <tr>
                <td><b>Channel</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>CI Rule</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>CI/CD</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>Configure:</strong> Grants permission to configure CI/CD.</td>
            </tr>
            <tr>
                <td><b>CLI Artifact</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>Push:</strong> Grants permission to Push images to the inbuilt ECR repositories.</td>
            </tr>
            <tr>
                <td><b>Cost Explorer</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>View Cost Explorer:</strong> Grants permission to cost explorer.</td>
            </tr>
            <tr>
                <td rowspan="2"><b>Environment</b></td>
                <td rowspan="2" >Yes</td>
                <td rowspan="2">Yes</td>
                <td><strong>Configure:</strong> Grants permission to configure the Environment.</td>
            </tr>
          	<tr>
              <td><strong>View Secrets:</strong> Grants permission to view environment secrets.</td>
          </tr>    
            <tr>
                <td rowspan="4"><b>K8s</b></td>
                <td rowspan="4">No</td>
                <td rowspan="4">No</td>
                <td><strong>Reader:</strong> Grants permission to read Kubernetes.</td>
            </tr>
            <tr>
                <td><strong>Debugger:</strong> Grants permission to debug Kubernetes.</td>
            </tr>
            <tr>
                <td><strong>Custom:</strong> Grants permission to add your own Kubernetes roles.</td>
            </tr>
            <tr>
                <td><strong>Kubernetes Credentials:</strong> Grants permission to access kube credentials.</td>
            </tr>
            <tr>
                <td><b>Maintenance Window</b></td>
                <td>Yes</td>
                <td>No</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>OAuth Integration</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>OPA</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td><strong>Execute:</strong> Grants permission to execute opa policies.</td>
            </tr>
            <tr>
                <td><b>Pipeline</b></td>
                <td>Yes</td>
                <td>No</td>
                <td>-</td>
            </tr>
         	 <tr>
                <td><b>Project</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td><strong>Configure:</strong> Grants permission to configure the blueprint.</td>
            </tr>
          <tr>
                <td><b>Project Template</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Project Type</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
          	 <tr>
                <td><b>Promotion Workflow</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td rowspan="13"><b>Release</b></td>
                <td rowspan="13">No</td>
                <td rowspan="13">No</td>
                <td><strong>Release Approve/Reject:</strong> Grants permission to approve or reject pending releases.</td>
            </tr>
            <tr>
                <td><strong>Full Release:</strong> Grants permission to perform full release.</td>
            </tr>
            <tr>
                <td><strong>Plan Release:</strong> Grants permission to create a plan for both the full and selective release.</td>
            </tr>
            <tr>
                <td><strong>Apply Release Plan:</strong> Grants permission to apply planned releases both full and selective.</td>
            </tr>
            <tr>
                <td><strong>Selective Release:</strong> Grants permission to perform selective release.</td>
            </tr>
            <tr>
                <td><strong>Custom Release:</strong> Grants permission to perform custom release.</td>
            </tr>
            <tr>
                <td><strong>Maintenance Release:</strong> Grants permission to perform maintenance release.</td>
            </tr>
            <tr>
                <td><strong>Scale Up:</strong> Grants permission to perform environment scale up.</td>
            </tr>
            <tr>
                <td><strong>Scale Down:</strong> Grants permission to perform environment scale down.</td>
            </tr>
            <tr>
                <td><strong>Allow Destroy for Full Release:</strong> Grants permission to allow destruction of protected resources during the full release.</td>
            </tr>
            <tr>
                <td><strong>Allow Destroy for Selective Release:</strong> Grants permission to allow destruction of protected resources during the selective release.</td>
            </tr>
            <tr>
                <td><strong>Allow Destroy for Custom Release:</strong> Grants permission to allow destruction of protected resources during the custom release.</td>
            </tr>
            <tr>
                <td><strong>Pause/Unpause Releases:</strong> Grants permission to pause/unpause release.</td>
            </tr>
          	 <tr>
                <td><b>Release Stream</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Resource</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>Override:</strong> Grants permission to override the resources.</td>
            </tr>
            <tr>
                <td><b>Resource Group</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td><strong>Read:</strong> Grants permission to view resource group.</td>
            </tr>
            <tr>
                <td><b>Resource Information</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>View Resource Secrets:</strong> Grants permission to view secrets of resources.</td>
            </tr>
            <tr>
                <td><b>Role</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td><strong>Read:</strong> Grants permission to view roles.</td>
            </tr>
            <tr>
                <td><b>Settings</b></td>
                <td>Yes</td>
                <td>No</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Subscription</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Template</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td>-</td>
            </tr>
            <tr>
                <td><b>Trash</b></td>
                <td>No</td>
                <td>Yes</td>
                <td><strong>Restore:</strong> Grants permission to restore items from trash.</td>
            </tr>
            <tr>
                <td><b>User</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td><strong>Read:</strong> Grants permission to view users.</td>
            </tr>
            <tr>
                <td><b>User Group</b></td>
                <td>Yes</td>
                <td>Yes</td>
                <td><strong>Read:</strong> Grants permission to view user groups.</td>
            </tr>
            <tr>
                <td><b>VPN</b></td>
                <td>No</td>
                <td>No</td>
                <td><strong>VPN Connect:</strong> Grants permission to download vpn profile and connect to k8s using vpn.</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
`}</HTMLBlock>
