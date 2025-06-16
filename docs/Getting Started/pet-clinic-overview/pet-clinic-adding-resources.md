---
title: Adding Resources
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
Once the project has been created, the next step involves creating the resources required for the pet clinic application. Here, we will opt to create a **Service** resource, a **Postgres** resource, and an **Ingress** resource.

The **Postgres** resource in this context is a PostgreSQL database, used by your application for data storage and retrieval. The **Service** resource is where the Spring Boot application resides, and the **Ingress** resource manages the exposure of your services to the external world.

1. Open the **Projects** tab and select the required project. 
2. In the **Blueprint** tab, click **Add Resource.**

### Adding a Postgres Resource

1. In the Add Resource pop-up window, search for and select the resource type **Postgres** and the required flavor.
2. Mention the **Postgres Name** and click **Add.**

### Adding a Service Resource

1. In the Add Resource pop-up window, search for and select the resource type **Service.**
2. Mention the **Service Name** and click **Add.**

### Adding an Ingress Resource

1. In the Add Resource pop-up window, search for and select the resource type **Ingress.**
2. Mention the **Ingress Name** and click **Add.**

**Note:** When creating a resource, it is initially set with default sample values that can be modified after the resource has been created.

You have successfully created the necessary resources for the Pet Clinic application.

Let's move forward to the next step, [Creating and Launching an Environment.](doc:pet-clinic-environment)
