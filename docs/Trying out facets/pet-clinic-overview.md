---
title: Pet Clinic - Overview
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
The Petclinic application, developed with Spring Boot and buildable via Maven or Gradle, serves as an excellent resource for grasping the deployment and operation of a web application. The [official GitHub repository](https://github.com/spring-projects/spring-petclinic) suggests that users can compile a JAR file and execute it using the command line. However, we will be taking a different approach to demonstrate Facets' capabilities by deploying the application on your preferred cloud service provider and configuring ingress rules to make it publicly accessible. Additionally, we will set up a Postgres database to persistently store data across sessions.

Once operational on Facets.cloud, the Pet Clinic application offers an intuitive interface for managing pet information. Users will have the capability to enter, access, and remove details about their pets directly through the application's user interface.

The forthcoming sections are designed to provide detailed instructions and additional context, equipping you with the necessary tools to fully harness the key features of Facets by engaging in this practical experience.

## Objective

* This guide aims to facilitate deploying a basic Pet Clinic application on Facets.cloud. Upon successful deployment, the application will be globally accessible.
* Specifically, you will learn how to create a Blueprint, create an Environment, add and delete resources, and most importantly, deploy a simple application on the web using Facets. 

## Overview

As part of this guide, we will cover six main steps including a walkthrough of how to monitor your live web application from Facets. 

1. **Creating a Blueprint:** The Blueprint is essentially the Git repository that stores the ideal structure of your project's components, acting as the ultimate source of truth for your resource-level configurations.

2. **Creating and Launching an Environment:** Environments are manifestations of your Blueprint in any particular cloud provider. This is where your resources are deployed and can be managed from the Facets Control Plane.

3. **Adding Resources:** Resources are entities that exist within an environment. For the purpose of this exercise, we will create three resources: 
   1. a **Service** that will specify the details of the Spring Boot application, 
   2. a **Postgres** resource for data storage and retrieval and, 
   3. an **Ingress** resource for managing the external exposure of your services.

4. **Linking Resources:** Linking resources allows them to interact with each other (wiring resources). For example, a service might need to access a database (Postgres resource) to function correctly. 

5. **Accessing the Live Application:** You will be able to access and interact with your application in real-time globally.

6. **Monitoring the deployed application:** Facets includes comprehensive monitoring and logging tools, giving you visibility into the performance and health of your applications. Specifically, you will understand how to access the logs, metrics, and other details necessary to access your deployed resources with Facets.

Refer to the following guides for each step to help you navigate the process successfully. If you have any queries or concerns, please send an email to [support@facets.cloud](mailto:support@facets.cloud).
