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
In this document, we will discuss how to link resources using Dollar Referencing at the environment level. The objective of linking resources is to facilitate communication between them, enabling the seamless sharing of essential data, and promoting a more efficient and coordinated operation.

### Wiring PostgreSQL with a Service Resource

The first step involves wiring PostgreSQL with a Service. This is crucial as it allows the service to communicate directly with the database, thus facilitating data storage and exchange.

Let's walk through the process of wiring a Service to a Postgres database. Follow these steps:

1. **Create a Service and a Postgres Resource**\
   First, ensure you have both a Service and a Postgres resource created within your Blueprint.
2. **Edit the JSON Configuration**
   1. Navigate to **Blueprint > Designer** and locate the Service resource you want to connect to the Postgres resource.
   2. Click on the **Edit** icon adjacent to it in the table mode or select the node from the graph mode and click the **Edit** icon beside the JSON configuration.
   3. Under **spec > env**, provide the Postgres URL, username, and password in your configuration.

```Text JSON
"POSTGRES_URL": "jdbc:postgresql://${postgres.default-db.out.interfaces.writer.host}:${postgres.default-db.out.interfaces.reader.port}/postgres",
"POSTGRES_USER": "${postgres.default-db.out.interfaces.writer.username}",  
"POSTGRES_PASS": "${postgres.default-db.out.interfaces.writer.password}"
```
```Text Example
"env": {
			"LOG_LEVEL": "INFO",
			"SPRING_PROFILES_ACTIVE": "postgres",
			"POSTGRES_URL": "jdbc:postgresql://${postgres.default-db.out.interfaces.writer.host}/postgres",  
			"POSTGRES_USER": "${postgres.default-db.out.interfaces.writer.username}",  
			"POSTGRES_PASS": "${postgres.default-db.out.interfaces.writer.password}"
		}
```

In this example,\
**`"default-db":`** Name of our Postgres resource.\
**`"POSTGRES_URL":`** URL for the Postgres database.\
**`"POSTGRES_USER":`** Username of the Postgres database.\
**`"POSTGRES_PASS":`** Password of the Postgres database.

**Note:** The variables `POSTGRES_URL`, `POSTGRES_USER`, and `POSTGRES_PASS` are placeholders in the configuration. While these can be named differently, it is crucial to ensure that the values are correctly mapped to the respective variables.

### Wiring a Service with Ingress

The next step is to link the service with an ingress resource. 

To ensure that your application is accessible, you will need to create an ingress resource and link it to your service. This makes your application accessible to the public using the ingress public URL.

Let's walk through the process of wiring a Service with an Ingress. Follow these steps:

1. **Create a Service and an Ingress Resource**\
   First, ensure you have both a Service and an Ingress resource created within your Blueprint.
2. **Edit the JSON Configuration**
   1. Navigate to **Blueprint > Designer** and locate the Ingress resource you want to connect to the Service resource.
   2. Click on the **Edit** icon adjacent to it in the table mode or select the node from the graph mode and click the **Edit** icon beside the JSON configuration.
   3. Under **spec > rules,** provide the service name and port in your configuration.

```Text JSON
"service_name": "${service.default-service.out.interfaces.http.name}",
"path": "/",
"port": "${service.default-service.out.interfaces.http.port}",
```

In this example,

**`"default-service":`**&#x4E;ame of the Service resource.

By following these steps, you can effectively link your resources using the Dollar Ref mechanism, ensuring efficient intercommunication and public accessibility of your application.

Once you have successfully linked the resources, your next steps involve performing a release and then [accessing the application.](doc:pet-clinic-accessing-the-live-application)
