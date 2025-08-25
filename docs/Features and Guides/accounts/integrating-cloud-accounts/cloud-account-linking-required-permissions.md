---
title: 'Cloud account linking: required permissions'
deprecated: false
hidden: false
metadata:
  robots: index
---
This document summarizes the permissions an end user needs to link their cloud account to Facets, and what permissions are granted to Facets during linking, based on the provided scripts in `scripts/`.

## AWS

* **What the script does** (`scripts/aws-account-link.sh`):
  * Generates an External ID and creates an IAM Role with a trust policy that allows `sts:AssumeRole` from the specified AWS account using that External ID.
  * Attaches an inline policy (downloaded from `scripts/aws-policy.json`) to that role.
  * Sends the role ARN and External ID to the control plane.

* **Permissions required for the end user running the script** (in the target AWS account):
  * `iam:CreateRole`
  * `iam:PutRolePolicy`
  * Optionally `iam:TagRole`/`iam:UpdateAssumeRolePolicy` if your environment enforces tags or requires updates
  * Network egress to the control plane URL provided as `CP_URL`

* **Permissions granted to Facets (via the attached role policy)**:

  * Explicit: `ssm:PutParameter` on `arn:aws:ssm:*:*:parameter/CodeBuild/*`
  * Broad service-level access (resource `*`) to manage common infra:
    * `iam:*`, `lambda:*`, `apigateway:*`, `s3:*`, `sqs:*`, `cloudwatch:*`, `ec2:*`, `acm:*`, `route53:*`, `eks:*`, `dynamodb:*`, `autoscaling:*`, `logs:*`, `codebuild:*`, `elasticfilesystem:*`, `ecr:*`, `events:*`, `elasticloadbalancing:*`, `cloudfront:*`, `rds:*`, `sns:*`, `kms:*`, `outposts:GetOutpostInstanceTypes`, `elasticache:*`, `ce:*`, `dax:*`, `dlm:*`, `kafka:*`, `kafka-cluster:*`, `kafkaconnect:*`, `es:*`, `secretsmanager:*`, `ecs:*`

  See `scripts/aws-policy.json` for the full, authoritative list.

## Azure

* **What the script does** (`scripts/azure-account-link.sh`):
  * Lets the user pick a subscription, sets context, creates a custom role definition scoped to that subscription, then creates a Service Principal and assigns that custom role to it.
  * Sends the Service Principal credentials and subscription details to the control plane.

* **Permissions required for the end user running the script**:
  * On the Azure AD tenant:
    * Ability to create an application/service principal (e.g., Azure AD roles such as Application Administrator or Cloud Application Administrator)
  * On the target subscription (scope of assignment):
    * Ability to create custom roles: `Microsoft.Authorization/roleDefinitions/write`
    * Ability to assign roles: `Microsoft.Authorization/roleAssignments/write`
    * Sufficient rights to read subscription and set context
  * Azure CLI authenticated with the correct tenant/subscription and network egress to the control plane URL

* **Permissions granted to Facets (via the custom role assigned to the SP)**:

  * Actions included by the role definition created by the script:
    * `Microsoft.Resources/subscriptions/resourceGroups/*`
    * `Microsoft.Network/virtualNetworks/*`
    * `Microsoft.Network/networkSecurityGroups/*`
    * `Microsoft.Network/publicIPAddresses/*`
    * `Microsoft.Network/natGateways/*`
    * `Microsoft.ContainerService/*`
    * `Microsoft.Storage/storageAccounts/*`
    * `Microsoft.Authorization/roleAssignments/*`
    * `Microsoft.Network/privateDnsZones/*`
    * `Microsoft.DBforMySQL/flexibleServers/*`
    * `Microsoft.ManagedIdentity/userAssignedIdentities/*`
    * `Microsoft.Network/applicationGateways/*`
    * `Microsoft.Cache/redis/*`
    * `Microsoft.Web/serverFarms/*`
    * `Microsoft.Web/sites/*`
    * `Microsoft.ServiceBus/namespaces/*`
    * `Microsoft.ContainerService/managedClusters/*`
    * `Microsoft.Compute/disks/write`
    * `Microsoft.Compute/disks/read`
    * `Microsoft.ServiceFabricMesh/register/action`

  This custom role is scoped to the selected subscription.

## GCP

* **What the script does** (`scripts/gcp-account-link.sh`):
  * Lets the user pick a project, enables a large set of required APIs, creates a service account (if needed) and a key, grants the service account the `roles/owner` role on the project, and sends the base64-encoded key to the control plane.

* **Permissions required for the end user running the script** (on the selected GCP project):
  * Enable services/APIs:
    * `serviceusage.services.enable` (e.g., role: `roles/serviceusage.serviceUsageAdmin`)
  * Service account management and key creation:
    * `iam.serviceAccounts.create` (e.g., role: `roles/iam.serviceAccountAdmin`)
    * `iam.serviceAccountKeys.create` (e.g., role: `roles/iam.serviceAccountKeyAdmin`)
  * IAM policy binding to grant the service account Owner:
    * `resourcemanager.projects.setIamPolicy` (commonly requires Project Owner or Project IAM Admin)
  * gcloud authenticated to the project and network egress to the control plane URL

* **Permissions granted to Facets (via the service account)**:
  * `roles/owner` on the selected project, which confers broad administrative privileges across most GCP services in that project.

## Notes

* The scripts assume properly configured CLIs (`aws`, `az`, `gcloud`, and `jq`), and that you are authenticated to the target accounts/tenants/projects.
* The permissions listed above are the minimum practical rights inferred from the scripts to complete linking; your organization may impose additional controls (e.g., policy-as-code, mandatory tags, approval gates) that require extra privileges.
