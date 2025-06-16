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
Once the blueprint has been created, the next step involves creating the resources required for the pet clinic application. Here, we will opt to create a **Service** resource, a **Postgres** resource, and an **Ingress** resource.

The **Postgres** resource in this context is a PostgreSQL database, used by your application for data storage and retrieval. The **Service** resource is where the Spring Boot application resides, and the **Ingress** resource manages the exposure of your services to the external world.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/13a2260-image.png",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


## How to Add Resources?

1. Navigate to **Blueprint > List** and select the required Blueprint. 
2. Open **Designer** and click **Add Resources.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/46fdf7d-pet_-_Add_resources.gif",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


### Adding a Postgres Resource

1. In the Add Resource pop-up window, search for and select the resource type **Postgres.**
2. Select the desired **Flavor** for your resource.
3. Mention the **Resource Name** and click **Add.**
4. To create the resource and view its configuration, click **Add & View.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/93a1bc9-pet_-_add_res_postgres.gif",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


#### Default Postgres JSON

```Text JSON
{
  "$schema": "https://facets-cloud.github.io/facets-schemas/schemas/postgres/postgres.schema.json",
  "provided": false,
  "kind": "postgres", //This represents the type of object described by the JSON, in this case, a PostgreSQL database.
  "version": "0.1",
  "depends_on": [],
  "disabled": true,
  "metadata": {       //This object includes additional information about the database, such as its name.
    "name": "daw"    
  },
  "flavor": "k8s",
  "spec": {
    "postgres_version": "12.11", //Specifies the version of PostgreSQL used.
    "size": {
      "writer": {
        "instance": "db.t3.medium",
        "instance_count": 1
      },
      "reader": {
        "instance": "db.t3.medium",
        "instance_count": 1
      }
    }
  }
}
```

### Adding a Service Resource

1. In the Add Resource pop-up window, search for and select the resource type **Service.**
2. Select the desired **Flavor** for your resource.
3. Mention the **Resource Name** and click **Add.**
4. To create the resource and view its configuration, click **Add & View.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/1c95706-pet_-_add_res_service.gif",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


#### Default Service JSON

```Text JSON
{
  "$schema": "https://facets-cloud.github.io/facets-schemas/schemas/service/service.schema.json",
  "flavor": "default",
  "metadata": {
    "labels": {}
  },
  "kind": "service",
  "disabled": true,
  "provided": false,
  "version": "0.1",
  "spec": {
    "enable_host_anti_affinity": false,
    "type": "application",
    "release": {
    "image": "facetscloud/petclinic:1.0", //Specifies the Docker image to be used for the service.
      "strategy": {
        "type": "RollingUpdate"
      },
      "build": {
        "artifactory": "default",
        "name": "replace-with-app-name" //The placeholder text "replace-with-app-name" should be replaced with the actual name of your application.
      }
    },
    "runtime": {
      "autoscaling": {  
        "min": "1", // The minimum number of pods that should always be running for this service.
        "max": "1", //If the CPU usage surpasses the specified threshold, Kubernetes will attempt to create additional pods.
        "cpu_threshold": "50" //This setting signifies the CPU usage threshold, expressed as a percentage. If the CPU usage goes beyond this 50% mark, Kubernetes' autoscaling feature will initiate the creation of new pods to maintain performance.
      },
      "ports": {
        "http": {
          "port": "8080", //This denotes the network port on which the service is exposed and will be accessible.
          "protocol": "tcp"
        }
      },
      "size": {
        "cpu": "300m",
        "memory": "1Gi",
        "cpu_limit": "1000m"
      },
      "health_checks": {
        "timeout": "10",
        "period": "30",
        "port": "8080",
        "start_up_time": "15"
      },
      "volumes": {}
    },
    "env": {
      "LOG_LEVEL": "INFO"
      "SPRING_PROFILES_ACTIVE": "postgres", //This is an environment variable that determines the active profile during runtime. Here, "SPRING_PROFILES_ACTIVE": "postgres" sets the active profile to "postgres". 

    }
  }
}
```

### Adding an Ingress Resource

1. In the Add Resource pop-up window, search for and select the resource type **Ingress.**
2. Select the desired **Flavor** for your resource.
3. Mention the **Resource Name** and click **Add.**
4. To create the resource and view its configuration, click **Add & View.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d3a434c-pet_-_add_res_ingress.gif",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


#### Default Ingress JSON

```Text JSON
{
  "kind": "ingress",
  "$schema": "https://facets-cloud.github.io/facets-schemas/schemas/loadbalancer/ingress.schema.json",
  "flavor": "nginx_ingress_controller",
  "disabled": true,
  "version": "0.2",
  "provided": false,
  "depends_on": [],
  "metadata": {
    "name": "test-nginx",
    "annotations": {}
  },
  "spec": {
    "private": false,
    "basic_auth": false,
    "grpc": false,
    "domains": {},
    "rules": {
      "pet-clinic": {
        "service_name": "prometheus-operator-grafana", //This denotes the service to which this Ingress is connected.
        "path": "/",
        "port": 8080, //This denotes the network port on which the service is exposed and will be accessible.
        "domain_prefix": "pet-clinic"
      }
    },
    "force_ssl_redirection": true
  }
}
```

**Note: **When creating a resource, it is initially set with default sample values that can be modified after the resource has been created.

You have successfully created the necessary resources for the Pet Clinic application.

## How to Enable the Added Resources?

Upon creation, all resources are in a **disabled** state. To enable them, please follow the below steps:

1. Navigate to **Environment > Resource Center.** 
2. Select the Postgres, Service, and Ingress resources you just created and click the **Enable** button at the bottom.
3. In the Enable Resource pop-up, type **Confirm** in the text box and click **Enable.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ce9c79e-pet_-_enable_resource.gif",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


You have successfully enabled the created resources.

Let's continue by [Linking the Resources.](doc:pet-clinic-linking-a-resource)