---
title: Get your Control Plane (GCP)
excerpt: Your first step towards effortless deployments with Facets!
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Welcome to Facets! In this getting started guide, we will walk you through the process of getting your control plane. 

1. **Get a Demo **: To get started, simply request a [demo by contacting the Facets team](https://www.facets.cloud/demo). Our team will understand the requirements and will help you get started. 
2. **Submit Service Account Details**:  
   You will receive a form to submit your **Google Cloud Service Account** details. Ensure that:
   - You use a **dedicated GCP project** for better security and isolation.  
     A dedicated subscription is recommended to set up the Facets control plane.
   - Enable the following google APIs in the project where Facets control plane resources are to be deployed.
     ```
     "analyticshub.googleapis.com"
     "artifactregistry.googleapis.com"
     "autoscaling.googleapis.com"
     "certificatemanager.googleapis.com"
     "cloudapis.googleapis.com"
     "cloudkms.googleapis.com"
     "cloudresourcemanager.googleapis.com"
     "cloudtrace.googleapis.com"
     "compute.googleapis.com"
     "container.googleapis.com"
     "containerfilesystem.googleapis.com"
     "containerregistry.googleapis.com"
     "dataform.googleapis.com"
     "dataplex.googleapis.com"
     "datastore.googleapis.com"
     "deploymentmanager.googleapis.com"
     "dns.googleapis.com"
     "gkebackup.googleapis.com"
     "iam.googleapis.com"
     "iamcredentials.googleapis.com"
     "logging.googleapis.com"
     "monitoring.googleapis.com"
     "networkconnectivity.googleapis.com"
     "oslogin.googleapis.com"
     "pubsub.googleapis.com"
     "redis.googleapis.com"
     "servicemanagement.googleapis.com"
     "servicenetworking.googleapis.com"
     "serviceusage.googleapis.com"
     "sql-component.googleapis.com"
     "sqladmin.googleapis.com"
     "storage-api.googleapis.com"
     "storage-component.googleapis.com"
     "storage.googleapis.com"
     "secretmanager.googleapis.com"
     ```
   - Ensure the service account has the necessary permissions :
   ```
   "alloydb.clusters.create"
     "alloydb.clusters.delete"
     "alloydb.clusters.get"
     "alloydb.clusters.update"
     "alloydb.instances.create"
     "alloydb.instances.delete"
     "alloydb.instances.get"
     "alloydb.instances.update"
     "alloydb.operations.get"
     "cloudkms.cryptoKeyVersions.destroy"
     "cloudkms.cryptoKeyVersions.list"
     "cloudkms.cryptoKeys.create"
     "cloudkms.cryptoKeys.get"
     "cloudkms.cryptoKeys.getIamPolicy"
     "cloudkms.cryptoKeys.setIamPolicy"
     "cloudkms.cryptoKeys.update"
     "cloudkms.keyRings.create"
     "cloudkms.keyRings.get"
     "cloudsql.databases.create"
     "cloudsql.databases.delete"
     "cloudsql.databases.get"
     "cloudsql.instances.create"
     "cloudsql.instances.delete"
     "cloudsql.instances.get"
     "cloudsql.instances.list"
     "cloudsql.instances.update"
     "cloudsql.users.create"
     "cloudsql.users.delete"
     "cloudsql.users.list"
     "cloudsql.users.update"
     "compute.addresses.create"
     "compute.addresses.delete"
     "compute.addresses.get"
     "compute.disks.delete"
     "compute.disks.list"
     "compute.firewalls.create"
     "compute.firewalls.delete"
     "compute.firewalls.get"
     "compute.forwardingRules.create"
     "compute.forwardingRules.delete"
     "compute.forwardingRules.get"
     "compute.forwardingRules.setLabels"
     "compute.globalAddresses.createInternal"
     "compute.globalAddresses.deleteInternal"
     "compute.globalAddresses.get"
     "compute.globalOperations.get"
     "compute.healthChecks.create"
     "compute.healthChecks.delete"
     "compute.healthChecks.get"
     "compute.healthChecks.useReadOnly"
     "compute.instanceGroupManagers.create"
     "compute.instanceGroupManagers.delete"
     "compute.instanceGroupManagers.get"
     "compute.instanceGroups.delete"
     "compute.instanceGroups.use"
     "compute.instanceTemplates.create"
     "compute.instanceTemplates.delete"
     "compute.instanceTemplates.get"
     "compute.instances.list"
     "compute.networks.create"
     "compute.networks.delete"
     "compute.networks.get"
     "compute.networks.removePeering"
     "compute.networks.updatePolicy"
     "compute.networks.use"
     "compute.regionBackendServices.create"
     "compute.regionBackendServices.delete"
     "compute.regionBackendServices.get"
     "compute.regionBackendServices.use"
     "compute.regionOperations.get"
     "compute.routers.create"
     "compute.routers.delete"
     "compute.routers.get"
     "compute.routers.update"
     "compute.sslPolicies.create"
     "compute.sslPolicies.delete"
     "compute.sslPolicies.get"
     "compute.sslPolicies.update"
     "compute.subnetworks.create"
     "compute.subnetworks.delete"
     "compute.subnetworks.get"
     "compute.subnetworks.use"
     "compute.zoneOperations.get"
     "compute.zones.list"
     "container.clusterRoleBindings.create"
     "container.clusterRoleBindings.delete"
     "container.clusterRoleBindings.get"
     "container.clusterRoles.bind"
     "container.clusterRoles.create"
     "container.clusterRoles.escalate"
     "container.clusterRoles.get"
     "container.clusters.create"
     "container.clusters.delete"
     "container.clusters.get"
     "container.clusters.getCredentials"
     "container.clusters.list"
     "container.clusters.update"
     "container.configMaps.create"
     "container.configMaps.get"
     "container.cronJobs.create"
     "container.cronJobs.delete"
     "container.cronJobs.get"
     "container.deployments.create"
     "container.deployments.get"
     "container.namespaces.create"
     "container.namespaces.delete"
     "container.namespaces.get"
     "container.operations.get"
     "container.priorityClasses.create"
     "container.priorityClasses.delete"
     "container.priorityClasses.get"
     "container.replicaSets.list"
     "container.roleBindings.create"
     "container.roleBindings.delete"
     "container.roleBindings.get"
     "container.roles.bind"
     "container.roles.create"
     "container.roles.delete"
     "container.roles.escalate"
     "container.roles.get"
     "container.secrets.create"
     "container.secrets.delete"
     "container.secrets.get"
     "container.secrets.list"
     "container.secrets.update"
     "container.serviceAccounts.create"
     "container.serviceAccounts.delete"
     "container.serviceAccounts.get"
     "container.storageClasses.create"
     "container.storageClasses.delete"
     "container.storageClasses.get"
     "dns.changes.create"
     "dns.managedZones.list"
     "dns.resourceRecordSets.create"
     "dns.resourceRecordSets.delete"
     "dns.resourceRecordSets.list"
     "iam.roles.create"
     "iam.roles.delete"
     "iam.roles.get"
     "iam.roles.list"
     "iam.serviceAccounts.actAs"
     "iam.serviceAccounts.create"
     "iam.serviceAccounts.delete"
     "iam.serviceAccounts.get"
     "iam.serviceAccounts.getIamPolicy"
     "iam.serviceAccounts.list"
     "iam.serviceAccounts.setIamPolicy"
     "monitoring.metricDescriptors.list"
     "monitoring.timeSeries.list"
     "redis.instances.create"
     "redis.instances.delete"
     "redis.instances.get"
     "redis.instances.getAuthString"
     "redis.instances.list"
     "redis.instances.update"
     "redis.instances.updateAuth"
     "redis.operations.get"
     "resourcemanager.projects.get"
     "resourcemanager.projects.getIamPolicy"
     "resourcemanager.projects.setIamPolicy"
     "servicenetworking.operations.get"
     "servicenetworking.services.addPeering"
     "servicenetworking.services.get"
     "storage.buckets.create"
     "storage.buckets.delete"
     "storage.buckets.get"
     "storage.buckets.getIamPolicy"
     "storage.buckets.list"
     "storage.buckets.setIamPolicy"
     "storage.buckets.update"
     "storage.objects.delete"
     "storage.objects.get"
     "storage.objects.list"
   ```
   <br />
3. **The Facets team launches the Control Plane**: After receiving your **service account details**, the Facets team will launch the **control plane** in your GCP environment. The setup is usually completed within **60 minutes**.
4. **Welcome Email with Control Plane URL**:  
   Once the deployment is successful, you will receive a **welcome email** containing:
   - Your **Facets Control Plane URL**
   - A **username**
   - A **password reset link**  
     Use these credentials to log in and start configuring your Facets environment.

## **Resources Deployed on GCP**

The **Facets Control Plane** will include the following Google Cloud resources:

### **Networking**

- **Virtual Private Cloud (VPC)**: A dedicated VPC for the Facets control plane. In Custom cases we optionally work with shared vpc as well. [Read More](https://readme.facets.cloud/docs/launching-facets-control-plane-in-gcp-shared-vpc)
- **Subnets**:
  - **Private Subnets**: Located in two separate **GCP regions/zones**, with **Cloud NAT Gateways** for outbound internet access.
  - **Public Subnets**: Designed for managing external access.

### **Compute & Container Orchestration**

- **Google Kubernetes Engine (GKE)**:
  - **Cluster**: A **GKE cluster** with **encryption at rest** enabled.
  - **Nodes**: A **GKE node pool** with **8 vCPUs, 32GB RAM**, and a **100GB root volume**.
  - **Auto-scaling**: Ensuring efficient resource allocation.
- **Google Cloud Load Balancer (GLB)**:
  - **Two external HTTP(S) Load Balancers** to distribute traffic across availability zones.

### **Storage & Security**

- **Database**: **postgres db** for managing terraform state.
- **Cloud IAM**: Role-based access controls (RBAC) for **fine-grained security policies**.
- **Cloud Logging & Monitoring**:
  - **Google Cloud Operations Suite** (formerly Stackdriver) integration for **real-time monitoring** and **logging**.

## Deployment Options

You can choose any **Google Cloud Region** upto two **Availability Zones** for deploying your control plane. 

For custom configurations such as **resource scaling** or **high-availability setups**, communicate your preferences to the **Facets team**.

## Managing Your Control Plane

After deployment, you can:

- Create **custom blueprints** to automate cloud infrastructure.
- Manage resources using the **Facets UI** or **CLI**.
- Monitor your workloads through **integrated dashboards**.

***

# Get GCP Secret Manager for Control Plane

The Facets GCP Secret Manager feature enables secure storage and management of secrets using Google Cloud Platform (GCP) Secret Manager. This feature is specific to GCP control planes and provides multiple replication and storage options to accommodate different security and compliance requirements.

## Quick Steps

1. Ensure the Secret Manager API is enabled in your GCP Project. You can enable it through the Google Cloud Console or using the following gcloud command: `gcloud services enable secretmanager.googleapis.com`
2. Choose one of the Secret Manager Modes.
3. Connect and share the details with Facets team to enable this for the CP. [Connect here](https://www.facets.cloud/demo).

### Secret Manager Modes

The feature supports three operational modes, implemented in the GcpSecretsService:

- `AUTOMATIC_REPLICATION`: Secrets are automatically replicated across multiple regions by GCP (default setting)
- `USER_MANAGED_REPLICATION`: Customer specifies which regions the secret should be replicated to
- `REGIONAL`: Secrets are available only in a specific region

### Mode Selection Guide

Automatic vs. User-Managed Replication

When choosing between automatic and user-managed replication, consider these factors as described in [GCP documentation](https://cloud.google.com/secret-manager/docs/choosing-replication):

#### Automatic Replication: Provides greater availability by replicating secrets to all available regions

Pros: Higher availability, simpler management  
Cons: May conflict with organizational policies, higher costs

##### User-Managed Replication: Allows you to specify exactly which regions contain your secrets

Pros: Fine-grained control, potentially lower costs, compliance with location restrictions  
Cons: Manual management overhead, potentially lower availability

### Regional Secrets

Regional secrets are only available in [specific regions supported by Secret Manager](https://cloud.google.com/secret-manager/docs/locations). Consider using regional secrets when:

- You have strict data residency requirements
- You want to minimize costs for rarely accessed secrets
- Your applications only run in a specific region

For a detailed comparison between regional and global secret options, see [Google's comparison documentation](https://cloud.google.com/secret-manager/regional-secrets/global-regionalized-service-comparison).

### Organizational Policy Considerations

If your organization has implemented location restriction policies, you may be blocked from creating automatically replicated secrets. These restrictions are enforced through [Organization Resource Location Restrictions](https://cloud.google.com/resource-manager/docs/organization-policy/defining-locations).

In such cases, you must use either:

- `USER_MANAGED_REPLICATION` mode with approved regions
- `REGIONAL `mode with an approved region

#### Important Implementation Notes

The `SecretManagerMode` should not be changed after secrets have been migrated to avoid access issues.  
When using modes other than `AUTOMATIC_REPLICATION`, the `gcp.secret.manager.region.id` must be set to a supported region.

Regional secrets are only available in the regions listed in the [Secret Manager locations documentation](https://cloud.google.com/secret-manager/docs/locations).

## **Support & Assistance**

For any issues or additional configurations, contact **Facets Support** at **[support@facets.cloud](mailto:support@facets.cloud)**.