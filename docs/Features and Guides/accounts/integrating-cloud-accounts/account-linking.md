---
title: Account Linking
deprecated: false
hidden: true
metadata:
  robots: index
---
## Quick summary

1. In the Facets UI go to **Settings → Accounts**.
2. Choose the cloud provider (AWS, Azure, GCP, Kubernetes), give the account a name and continue.
3. Copy the one-line command shown in the UI.
4. Open the provider Cloud Shell (recommended) or an authenticated CLI session, paste and run the command. For Kubernetes, ensure your kubeconfig is loaded first.
5. Return to Facets — the UI will show the account as linked when complete.

***

## Prerequisites

* Facets UI access with permissions to add/link accounts (Settings → Accounts).
* CLI access or Cloud Shell access authenticated to the target account/project/subscription.
* Network egress from the shell/terminal to the Facets control plane URL the UI shows.
* For Kubernetes: access to the cluster kubeconfig so you can run the UI-provided command against the cluster.

***

## What you will do (high-level flow)

* Open Facets → **Settings → Accounts**.
* Click the cloud tile (AWS / Azure / GCP / Kubernetes), enter an account name, click **Next**.
* Copy the single-line command the UI displays.
* Paste and run that command in the provider Cloud Shell or authenticated CLI session (for Kubernetes, include your kubeconfig first).
* The Facets UI will update to show the linked account.

***

## Permissions _you_ need (by provider)

> These list the common minimum privileges the person running the UI-provided command typically must hold in the target account/tenant/project/subscription. Your organization may require additional approvals or different role names.

### AWS — Required by the user who runs the command

* Ability to create and configure an IAM role in the target AWS account, commonly including:
  * `iam:CreateRole`
  * `iam:PutRolePolicy` / `iam:AttachRolePolicy`
  * (Possibly) `iam:TagRole` / `iam:UpdateAssumeRolePolicy` if your org enforces tagging or special trust policy updates
* Outbound network egress from the shell to the Facets control plane URL.

### Azure — Required by the user who runs the command

* Privileges in Azure AD to register/create an application or service principal (Application Administrator or equivalent).
* Privileges on the selected subscription to create and assign a custom role, typically including:
  * `Microsoft.Authorization/roleDefinitions/write` (create role definition)
  * `Microsoft.Authorization/roleAssignments/write` (assign the role to the service principal)
* Authenticated Azure CLI targeting the correct tenant/subscription and network egress.

### GCP — Required by the user who runs the command

* Ability to enable APIs/services on the project (e.g., `serviceusage.services.enable`).
* Ability to create service accounts and keys, commonly:
  * `iam.serviceAccounts.create` (create service accounts)
  * `iam.serviceAccountKeys.create` (create keys)
* Ability to grant the created service account the project-level role(s) required by Facets (often Project Owner or equivalent) — this typically requires `resourcemanager.projects.setIamPolicy` or Project Owner privileges.
* `gcloud` authenticated to the chosen project and outbound network egress.

### Kubernetes — Required by the user who runs the command

* Access to the cluster kubeconfig with sufficient rights to allow the command to install or register the agent/components that Facets requires (cluster-admin or appropriate delegated privileges in many environments).
* Ability to run `kubectl` from the environment where you paste/run the UI command (Cloud Shell or workstation with kubeconfig loaded).

***

## What permissions Facets will have after linking

> Facets receives broad administrative capabilities in a scoped way so it can orchestrate resources. You keep control because these are cloud-native role/service-account/role-assignment artifacts created in your account/project/subscription.

### AWS — What Facets gets

* Facets is granted access by way of an **IAM role** created in your account that Facets can assume. The role’s attached policy includes permissions across many infrastructure services needed for orchestration and management (examples include actions against IAM, S3, EC2, EKS, RDS, KMS, CloudWatch, CodeBuild, ECR, Lambda, etc.).
* You retain full control over the role — you can inspect, modify, restrict, or delete it at any time.

### Azure — What Facets gets

* A **Service Principal** is created and a **custom role** scoped to the selected subscription is assigned to it. The custom role contains privileges to manage typical platform resources (resource groups, networking, compute, storage, AKS, role assignments, DNS, managed identities, databases, app services, and more).
* Review or revoke the role assignment from the subscription’s Role Assignments if needed.

### GCP — What Facets gets

* A **Service Account** is created in the selected GCP project and given broad administrative privileges in that project (commonly a project Owner role). You can revoke the created key or remove the role assignment from the project to terminate access.

### Kubernetes — What Facets gets

* When linking a Kubernetes cluster, Facets is given the rights necessary to manage resources within that cluster (via the Kubernetes RBAC rules or service account created as part of the linking process). You can remove the service account/cluster role bindings to revoke access.

***

## Security & operational notes (recommended practices)

* **Network egress:** The linking command needs outbound access to Facets’ control plane URL from the shell you run. Ensure your Cloud Shell or terminal can reach it.
* **Least privilege & scoping:** Where possible, link only the account/project/subscription you want Facets to manage (e.g., dedicated account for platform workloads). Review and minimize permissions after verifying required functionality.
* **Audit & monitoring:** Enable cloud audit logs (CloudTrail, Azure Activity Log, Cloud Audit Logs) and monitor actions by the created identities. Treat created roles/keys as privileged credentials — rotate and audit them periodically.
* **Org policies:** If your organization enforces guardrails (SCPs, management group policies, required tags), the linking flow may require an admin to perform or approve some steps.

***

## Troubleshooting checklist

* Ensure you copied the one-line command exactly from the Facets UI and ran it in the provider Cloud Shell or an authenticated CLI session.
* Confirm you are authenticated to the correct account/project/subscription/tenant in the shell where you run the command.
* Confirm the shell has outbound access to the Facets control plane URL.
* For Kubernetes: verify the kubeconfig loaded into the shell targets the intended cluster and you have sufficient RBAC permissions.
* If linking fails, inspect cloud provider telemetry (CloudTrail / Activity Log / Cloud Audit Logs) to see what failed and why, and review the command output for error messages.

***

## One-page checklist (copyable / printable)

**Before you begin**

* [ ] You have Facets UI access with permission to add accounts (Settings → Accounts).
* [ ] You have CLI/Cloud Shell access to the provider and are authenticated to the correct account/project/subscription/tenant.
* [ ] Your shell has outbound network access to the Facets control plane URL shown by the UI.

**Provider-specific pre-checks**

* AWS: You can create an IAM role and attach policies (`iam:CreateRole`, `iam:PutRolePolicy`).
* Azure: You can create/register apps/service principals and create/assign custom roles on the subscription.
* GCP: You can enable APIs, create service accounts/keys, and assign project-level roles.
* Kubernetes: You have kubeconfig access and rights to create the service account / RBAC bindings needed.

**Linking steps**

1. Open Facets → **Settings → Accounts**.
2. Choose provider, give account a name, click **Next**.
3. Copy the one-line command shown.
4. Paste & run in provider Cloud Shell or authenticated CLI (for Kubernetes, ensure kubeconfig loaded).
5. Confirm the account shows as linked in Facets.

**Post-linking checks**

* [ ] Inspect the created IAM role / service principal / service account and note its scope.
* [ ] Enable and check audit logging for actions performed by the created identity.
* [ ] If required, adjust role permissions or scope to follow your organization’s least-privilege policies.
* [ ] Record who performed the linking and when for your operational runbook.

***

## Need the artifacts for security/audit?

If your security or audit team needs the exact role or policy JSON files that Facets creates (for review), ask them to request those files from your Facets support contact or documentation page. They are the authoritative source for the exact policy contents used during linking.