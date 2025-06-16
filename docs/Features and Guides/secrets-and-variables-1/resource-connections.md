---
title: Resource Connections
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
## The Traditional Challenge

In microservices architecture, managing dependencies and connections between services often involves hardcoding endpoints, maintaining environment-specific connection strings, or creating complex service discovery mechanisms. This leads to brittle configurations, difficult maintenance, and potential security risks when sensitive connection details are exposed.

***

## Facets' Approach: Resource Connections Through Dollar Referencing

Resource connections in Facets provide a elegant way to handle inter-resource dependencies. Through dollar referencing in JSON, resources can seamlessly access properties of other resources within the blueprint. This connection system creates a visual and functional representation of resource dependencies, making it easy to understand and manage relationships between different components of your infrastructure.

At the blueprint level, apart from dollar referencing in JSON, users can also establish these connections through a simple interface, selecting the target resource and specific fields they need to reference. These connections, once established, become part of your infrastructure's DNA - unchangeable at the environment level, ensuring consistency and preventing environment-specific connection issues.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/05fee15ee34648d9c2e1cd84e167219bcd66ba03d259dd84403b4ac3ad213ff7-Screenshot_2025-02-12_at_1.04.47_PM.png",
        "",
        ""
      ],
      "align": "center"
    }
  ]
}
[/block]


### Real-World Application

Consider a web service that needs to connect to a database and use its endpoint. In the blueprint, the service JSON will have:

```json
test-service {
  "env": {
    "POSTGRES_USERNAME": "${postgres.test-pg.out.interfaces.reader.username}"
  }
}
```

When this blueprint is deployed, Facets automatically 

- Establishes the connection between the service and postgres
- Visualises this connection in the UI with directional arrows
- Ensures the reference remains consistent across all environments
- Maintains the relationship throughout the application lifecycle

This approach transforms what was once a complex web of environment-specific configurations into a clear, visually represented set of resource relationships that are easy to track and maintain.