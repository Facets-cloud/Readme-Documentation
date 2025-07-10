---
title: Bring Dependencies
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
## Bringing Existing Databases to Facets

Facets makes it easy to onboard your existing databases by offering structured blueprints and configurations. Whether you're migrating from traditional setups or cloud-hosted solutions, follow these steps to ensure a smooth migration:

<Image align="center" className="border" border={true} src="https://files.readme.io/f1750aa8afa6101b69c555ba534a008c39bda2af607ed172790a495cb9a1496b-image.png" />

### 1. Database Creation

* **Add DB Resource to Blueprint**: Choose a database resource from Facets' blueprints that matches your existing setup (e.g., RDS, MongoDB, Redis).
* **Configure Specifications**: Define parameters such as instance size, storage, and replication settings to mirror your current database.

### 2. Application Connection

* **Update Connection Details**: Modify the application’s database connection strings, credentials, and endpoints to point to the new database instance on Facets.

### 3. Data Migration

For databases like Redis, use existing tools and scripts to migrate data. This may involve:

* Taking snapshots or dumps.
* Exporting the data from the existing database.
* Importing it into the new database instance on Facets.

### 4. Cutover

* **Validate Migration**: Ensure the data migration was successful.
* **Redirect Connections**: Update the application to exclusively use the new database instance on Facets.
* **Decommission the Old Database**: If no longer needed, safely decommission the old database.

***

## Bringing Existing Cloud Dependencies to Facets

To transition your existing cloud dependencies to Facets, follow these steps:

### 1. Resource Provisioning

* **Select the Resource**: Choose a matching resource for your resource type (e.g., SQS, SNS, Lambda).
* **Mirror Configurations**: Configure the resource to match the settings of your existing setup, including attributes like queue delay, visibility timeout, or concurrency limits.

### 2. IAM Permission Setup

* **Define Access Policies**: Assign IAM roles and policies to allow the application to interact with the provisioned resources.

### 3. Environment Variables

* **Update Sensitive Information**: Add endpoints, ARNs, and credentials as environment variables within the Facets service configuration.

### 4. Application Integration

* **Modify Application Configuration**: Update the application’s configuration or code to reference the new resource endpoints and credentials.
* **Test Connectivity**: Verify that the application interacts with the new cloud resources as intended.

> **Note**: You can also mark resources as Provided which will allow you to seamlessly incorporate externally provided infrastructure components, services, and cloud resources into their workflows.