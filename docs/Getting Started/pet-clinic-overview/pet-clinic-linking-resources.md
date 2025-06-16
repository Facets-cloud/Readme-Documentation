---
title: Linking Resources
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
In this document, we will discuss how to link resources at the environment level. The objective of linking resources is to facilitate communication between them, enabling the seamless sharing of essential data, and promoting a more efficient and coordinated operation.

For further details on wiring different resources in Facets, you can refer to the [Use Dynamic Referencing to Connect Resources](https://readme.facets.cloud/docs/linking-resources-using-dollar-referencing) documentation.

### Wiring PostgreSQL with a Service Resource

The first step involves wiring PostgreSQL with a Service. This is crucial as it allows the service to communicate directly with the database, thus facilitating data storage and exchange.

Let's walk through the process of wiring a Service to a Postgres database. Follow these steps:

1. **Create a Service and a Postgres Resource**  
   First, ensure you have both a Service and a Postgres resource created within your Blueprint.
2. **Edit the JSON Configuration**
   1. Navigate to the **Blueprint** tab and select the Service resource you want to connect to the Postgres resource.
   2. Access the **Configurations** tab and click **Environment Variables.**
   3. Now, click **Add Environment Variables. **
   4. From the first column's drop-down menu, choose **Resource Reference.**
   5. Enter the **Key** as `POSTGRES_URL`, select the corresponding Postgres resource, and select the connection as host. Click **Add New Entry.**
   6. Enter the **Key** as `POSTGRES_USER`, select the corresponding Postgres resource, and select the connection as username. Click **Add New Entry.**
   7. Enter the **Key** as `POSTGRES_PASS`, select the corresponding Postgres resource, and select the connection as password.
   8. Click **Save.**

**Note:** The variables `POSTGRES_URL`, `POSTGRES_USER`, and `POSTGRES_PASS` are placeholders in the configuration. While these can be named differently, it is crucial to ensure that the values are correctly mapped to the respective variables.

### Wiring a Service with Ingress

The next step is to link the service with an ingress resource. 

To ensure that your application is accessible, you will need to create an ingress resource and link it to your service. This makes your application accessible to the public using the ingress public URL.

Let's walk through the process of wiring a Service with an Ingress. Follow these steps:

1. **Create a Service and an Ingress Resource**  
   First, ensure you have both a Service and an Ingress resource created within your Blueprint.
2. **Edit the JSON Configuration**
   1. Navigate to the **Resource Center** and select the Ingress resource you want to connect to the Service resource.
   2. Access the **Configurations** tab and click **Configure.**
   3. In the Form mode, under **Ingress Rules,** click **Add New Entry.**
   4. Mention the **Service Name, Path, **and** Port. **
   5. Click **Save Changes.**

By following these steps, you can effectively link your resources, ensuring efficient intercommunication and public accessibility of your application.

Once you've successfully linked the resources, your next steps involve performing a release and then [accessing the application.](doc:pet-clinic-accessing-the-live-application)