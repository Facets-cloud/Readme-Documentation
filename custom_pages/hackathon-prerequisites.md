---
title: Facets Hackathon
fullscreen: false
hidden: true
metadata:
  title: ''
  description: ''
---
Table of Contents:

- [What is Facets?](https://readme.facets.cloud/page/hackathon-prerequisites#what-is-facets-control-plane)
- [Prerequisites](https://readme.facets.cloud/page/hackathon-prerequisites#prerequisites)
- [Getting Started (To-do before Hackathon)](https://readme.facets.cloud/page/hackathon-prerequisites#getting-started)
- [Agenda for the Hackathon](https://readme.facets.cloud/page/hackathon-prerequisites#agenda-for-the-hackathon)
- [Support](https://readme.facets.cloud/page/hackathon-prerequisites#support)
- [Related Reading](https://readme.facets.cloud/page/hackathon-prerequisites#related-reading)

## What is Facets Control Plane?

Facets Control Plane is a platform as a service (PaaS) that enables your development team to provision, configure and manage your environments in a self-service manner. 

The Control Plane is deployed in your account based on your required set up, so it runs completely within your cloud environments and no permissions and data can ever go out of your control. 

## Prerequisites

- **Cloud Provider account (we support AWS, GCP, and Azure)**

> 📘 
> 
> Facets will deploy your Control Plane in this Cloud Provider account.

- **Git based repository (we support Github, Bitbucket, and Gitlab)**

> 📘 
> 
> This Git based repository will host your Blueprint definition that consists of your environments, variables, and resources.

- **Tech Stack details** (Example in parentheses) 
  - **Warehouse **(e.g., Snowflake)
  - **Database **(e.g., RDS)
  - **Automation **(e.g., Jenkins)
  - **Monitoring **(e.g., Cloudwatch)
  - **Logging **(e.g., Newrelic)
  - **Notification **(e.g., AWS SNS, Pagerduty)
  - **IaC **(e.g., Cloudformation, Ansible, Terraform)
  - **Deployment **(e.g., ArgoCD)
  - **Cluster Management** (e.g., EKS)
  - **Configuration Management** (e.g., Kustomization)

## Getting Started

### To-Do before Hackathon

1. Create a Cloud Provider account to deploy the Control Plane for your organization.
2. Click on the personalized link sent to your registered Email ID to launch a new stack in this account. 
3. Facets will now create IAM roles that are required to launch a Control Plane from this account.
4. Commit the blueprint definition in your Git repository, and share access for the same repository with the following accounts:

| Github    | Bitbucket           | Gitlab              |
| :-------- | :------------------ | :------------------ |
| anshulsao | anshul@facets.cloud | anshul@facets.cloud |
| rr0hit    | rohit@facets.cloud  | rohit@facets.cloud  |

### Information Required from You

We recommend you to compile answers to the following questions before the Hackathon day.

- Do you have a service to onboard to Facets? (Ideally a containerized service)
- How does this service read its configurations?
- How does this service discover other services and databases?
- Do you have a list of all downstream dependencies that are needed to start and run this service?
- How do you plan to test this service after migration?
- How is the build done for this service? Which tool is used for the same? For e.g., Jenkins, AWS Codebuild, etc.
- Where are the docker images stored?

## Agenda for the Hackathon

1. Facets will create a sample blueprint definition and launch the first environment in your Control Plane. 
2. Facets will add resource definitions and any required integrations in this environment for you to be able to test end to end the Facets Control Plane in your account. 
3. You will peer this newly created environment with your existing test environment.
4. You will integrate this environment with your Build (CD/CI) system.
5. You can run an end to end demonstration of a release and test your service using the Facets Control Plane.

## Support

For any questions or doubts regarding this process, kindly reach out to your Point of Contact (PoC) from Facets.

## Related Reading

- [Deploy your Facets Control Plane](https://readme.facets.cloud/v0.5/docs/installation)
- [Important Concepts](https://readme.facets.cloud/docs/concepts)

***



Information as of: September 2022