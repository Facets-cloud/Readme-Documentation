---
title: Creating and Launching an Environment
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## How to Create an Environment?

1. Open **Projects** and select the required Project.
2. Now, select the **Environments** tab and you will be greeted with a prompt to create your first Environment.
3. Mention the **Environment Name** and select the **Release Stream. **
4. Click **Create.**

You have successfully created a logical environment.

You can monitor the current status of all your created environments from the **Environments** tab within your project. For any newly created environment, the status will be displayed as **STOPPED** until it is launched.

The next step is to launch your environment, which initiates the process of creating the cluster and provisioning the resources.

## How to Launch an Environment?

1. To Launch an environment, open the **Projects** menu and select your desired project. 
2. Proceed to the **Environment** tab located on the top panel.  
   Here, you will find a collection of environments associated with your chosen project.
3. Identify the environment you want to launch and click the **Launch** button beside it.
4. This will prompt the **Environment Launch Wizard** to appear on your screen.  
   This wizard comprises of the following steps:
   1. **Connect your Cloud Provider: **
      1. Select the **Cloud Provider** where you plan to provision your infrastructure. 
      2. Choose the **Cloud Account** linked to your selected cloud provider.
   2. **Set up your Network: **
      1. You have the option to either **Create a new VPC** or **Choose an existing one.**
      2. If you opt for an existing VPC, you will need to provide the **VPC ID. **
      3. Finally, specify the **Region, Availability Zone, CIDR range, **and **Time Zone.**
   3. **Kubernetes Setup: **
      1. Mention the node type, Root Volume, Max Nodes and Node Lifecycle based on the requirement.
   4. **Review Secrets and Variables:**
      1. You can input the actual values for variables declared in the Blueprint either now or after the launch. However, if you prefer, you can skip the 'Secrets and Variables' tab at this time.
   5. **Review Resources: **
      1. It provides a comprehensive overview of all resources in your environment. 
      2. It also allows you to enable or disable resources prior to launching the environment.
5. Once you have completed these steps, click **Launch Environment.**
6. There are two possible outcomes at this point.
   1. If the launch fails, you can navigate to the 'Release Details' page. This page will provide detailed information about any errors that occurred during the launch, helping you understand and rectify the issue.
   2. If the launch is successful, then congratulations! You have successfully launched an environment in Facets.