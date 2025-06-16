---
title: Steps to create a Shared VPC (GCP)
excerpt: >-
  This doc will explain you all that are required for customers to create a
  shared vpc  and provided it to facets.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## 1. Prerequisites

a. GCP organizational account

b. Host project with permissions like : 

* Compute Network Admin
* Compute Network User
* Organization Administrator
* Owner

c. Other custom permissions

* `compute.organizations.disableXpnHost`
* `compute.organizations.disableXpnResource`
* `compute.organizations.enableXpnHost`
* `compute.organizations.enableXpnResource`
* `compute.projects.get`
* `resourcemanager.projects.get`
* `resourcemanager.projects.getIamPolicy`
* `resourcemanager.projects.list`

## 2. Key Steps:

1. Create the required (2 or 3 subnets ) VPC subnets with /16  CIDR ranges in your host project and also add 2 secondary CIDR ranges (also with /16 CIDR range) for the subnet created ➝ this is required for the creation of kubernetes clusters from facets end
2. Now we can go ahead and create the shared VPC and attach the projects that we want to share the subnets with.

   <Image align="center" className="border" width="1000px" border={true} src="https://files.readme.io/a4d4755ffd4ddede9f26cb2a60ee63d93dbb5d11f0999b6d55156f562af5e47e-image.png" />

<br />

<Image align="center" className="border" width="750px" border={true} src="https://files.readme.io/e535f6bcda0dfc17b31288c2001475f624f3c37bf720dd0745c93a53bca119af-image.png" />

<Image align="center" className="border" width="750px" border={true} src="https://files.readme.io/55a8acd6465f33cbd139cb2623f8767fb37a4144d98e6f11c060ec55ee645911-image.png" />

<Image align="center" className="border" width="750px" border={true} src="https://files.readme.io/849e8fb910b6b3c8fab3230d0e6e5f71af24aef0c4ebe459416aa45f44e3021b-image.png" />

<Image align="center" className="border" width="750px" border={true} src="https://files.readme.io/84f50a1ea057cdacb2b3c8ffec2bd673ce2ca0bebee4dc6e4654b8c35121b8c1-image.png" />

3. Once this is enabled, you can provide the appropriate details via the Facets UI

`Note: You can’t specify which subnet can be used by which service project. When you shared a subnet, it is shared with each of your service projects. If you want to specify the subnet and project together, you need to configure user permissions per subnet by giving permissions to accounts or service accounts used by the particular project(s).`

4. Enable the "private Google Access" for Kubernetes Nodes to access private Google resources.\
   Settings available in Host VPC > subnet details > private google access ➝ true

<Image align="center" className="border" width="750px" border={true} src="https://files.readme.io/3927abfced29d4a68fe610b4d0e5666266730f6bba4f6c1f0ef5b159ed4792a2-image.png" />
