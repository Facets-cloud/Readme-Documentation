---
title: Service
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
This guide walks you through the process of deploying your application on Facets, whether it's containerized, non-containerized, or uses Helm charts, YAMLs with Argo CD, or Docker Compose.

## 1. Create a Service Resource in Facets

Begin by creating a Service Resource in the **Blueprint** tab within Facets. This is the first foundational step for bringing your application into Facets, regardless of the application type.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/ccc2ef03e8eeb74e2b2035210b833c9c1abf8f3be62128ed018c04a598426f70-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


Once created, you can configure your service by clicking "Configure" from the context menu.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/223f54112d0dbeebb29cded1c5bbc26b526d72240aaa085456ac812c5350e37d-image.png",
        null,
        ""
      ],
      "align": "center",
      "border": true
    }
  ]
}
[/block]


## 2. Configure Your Application

After creating the Service Resource, you will need to configure it according to the specifics of your application type. Below are the steps for configuring different application types.

### Non-Containerized Applications

#### **Step 1: Containerize Your Application**

For non-containerized application first step is to containerize it, so convert your non-containerized application into a Docker container by creating a Docker image.

#### **Step 2: Push Docker Image to Container Registry**

Once your application is containerized, push the Docker image to your preferred container registry (e.g., Docker Hub, AWS ECR, GCR).

#### **Step 3: Configure the Service Resource**

Typically, environment variables are stored in configuration files like .env, while ports are specified in the application’s configuration. Health checks are usually implemented through endpoints (e.g., /health or /status in the application code). Once all necessary configurations are set, you can integrate your non-containerized application into Facets.

> **Note**: If your application is not containerized yet, you will need to containerize it first, as Facets primarily supports containerized deployments. Additionally, ensure that all dependencies, such as databases and environment variables, are identified and configured.

***

### Containerized Applications

For applications that are already containerized, the process is simpler:

Simply create and configure the Service Resource in the **Blueprint** tab by specifying your container image details. Below is an example of a typical container configuration:

```Text yaml
spec:
      containers:
      - name: my-app
        image: my-app-image:latest
        ports:
        - containerPort: 8080
        env:
        - name: DATABASE_URL
          value: "mongodb://db.example.com:27017"
```

In Facets, you would configure service ports as 8080 in this case, along with all other necessary settings in the same manner.

***

### Helm Applications

For applications that use Helm charts, the configuration is based on the values specified in your Helm chart. Here’s how to configure Helm applications in Facets:

#### **Step 1: Ensure Helm Chart Compatibility**

Make sure your Helm chart aligns with Facets’ service resource configurations (e.g., ports, health checks). In particular, the values.yaml file will contain environment variables, ports, and health check configurations.

#### **Step 2: Map Values from Helm Chart**

Map the necessary values from your Helm chart to the corresponding fields in the Facets Service Resource configuration. Example: 

In values.yaml, you’ll often see something like this:

```Text yaml
env:
  - name: DATABASE_URL
    value: "mongodb://db.example.com:27017"
```

In Facets, environment variables are configured under Environment Variables in the Service Resource settings. You can add the same variables as Key-Value pairs.

***

### Applications Using YAMLs + Argo CD

If you're using YAML files with Argo CD, the process is similar to Helm chart applications:

#### **Step 1: Analyze the YAML Configuration**

Ensure that the existing YAML configurations are properly set up and ready to be integrated with Facets' **Service** Resource.

#### **Step 2: Map YAML Data Fields**

Map the YAML data fields to the appropriate fields in the Facets Service Resource configuration to ensure consistency and functionality. For example:

```Text yaml
livenessProbe:
  httpGet:
    path: /status
    port: 8080
```

In Facets, configure this under the Health Checks section, specifying the Readiness Check Type and Liveness Check Type.

***

### Docker Compose Applications

For applications using Docker Compose:

#### **Step 1: Configuration Analysis**

Review the Docker Compose file to identify the fields that need to be mapped into the Facets service configuration.

#### **Step 2: Configuration Mapping**

Map your application's dependencies, ports, resource requirements, and scaling policies within the Service Configuration Sections. Fill in the corresponding values from your existing Docker Compose setup. For example : 

```Text yaml
version: '3'
services:
  app:
    image: my-app-image:latest
    environment:
      - DATABASE_URL=mongodb://db.example.com:27017
    ports:
      - "8080:8080"
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost/health"]
    
```

In Facets, under Runtime (Main Application Container), configure Ports for 8080 as the Service Port.

## 3. Push Docker Image to Container Registry

Once your Service configuration is done, you can push the Docker image to a container registry (e.g., Docker Hub, AWS ECR, or GCR).

## 4. Attach Docker Image to the Service Resource

You can either manually upload the image to the service resource or integrate the image push into your Continuous Integration (CI) pipeline. Learn more about this process [here](cicd-workflow).

***

By following these steps, you’ll be able to deploy your application seamlessly on Facets, regardless of whether it’s containerized, non-containerized, or uses Helm charts, YAML with Argo CD, or Docker Compose.

If you encounter any issues or need assistance, feel free to reach out to us!