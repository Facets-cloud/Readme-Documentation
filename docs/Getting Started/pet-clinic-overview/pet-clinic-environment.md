---
title: Creating and Launching an Environment
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
After creating your Project and resources, you can now launch the first manifestation of it: an Environment.

Note: If you have already created an environment while Creating your project, you can proceed to the next steps on Launching the Environment.

## How to Create an Environment?

1. Open **Projects** and select the required Project.
2. Now, select the **Environments** tab and you will be greeted with a prompt to create your first Environment.
3. Mention the **Environment Name** and select the **Release Stream. **
4. Click **Create.**

You have successfully created a logical environment.

You can monitor the current status of all your created environments from the **Environments** tab within your project. For any newly created environment, the status will be displayed as **STOPPED** until it is launched.

## How to Launch the Environment?

1. In your project, proceed to the **Environment** tab.  
   Here, you will find a collection of environments associated with your chosen project.
2. Identify the environment you want to launch and click the **Launch** button beside it.
3. This will prompt the **Environment Launch Wizard** to appear on your screen.  
   This wizard comprises of the following steps:
   1. **Connect your Cloud Provider: **
      1. Select the **Cloud Provider** where you plan to provision your infrastructure. 
      2. Choose the **Cloud Account** linked to your selected cloud provider.
   2. **Set up your Network: **
      1. You have the option to either **Create a new VPC** or **Choose an existing one.**
      2. If you opt for an existing VPC, you will need to provide the **VPC ID. **
      3. Finally, specify the **Region, Availability Zone, CIDR range, **and **Time Zone.**
   3. **Kubernetes Setup: **
      1. Define your Kubernetes cluster's Node type(s) based on your specific requirements and constraints.
   4. **Review Secrets and Variables:**
      1. It allows you to view and edit your existing secrets and variables. Refer to the Secrets and Variables guide for detailed instructions on how to create Secrets and Variables.
   5. **Review Resources: **
      1. Enable the Postgres, Service, and Ingress resources that you created earlier.
4. Once you have completed these steps, click **Launch Environment.** 
5. You will be redirected to the **Releases** page of this environment. 

   1. You can find the details of your current deployment under the **Latest Release** widget. 
   2. Under the **Actions** column, you can view the **Terraform Logs** of this deployment.
6. There are two possible outcomes at this point:
   1. If the launch fails, you can navigate to the 'Release Details' page using the Release details icon under the Actions column. This page will provide detailed information about any errors that occurred during the launch, helping you understand and rectify the issue.
   2. If the launch is successful, then congratulations! You have successfully launched an environment in Facets.

## Environment Overview

After launching the environment, you can find all relevant details about it on the environment **Overview** page. This can be accessed by selecting the **Environment** and selecting the **Overview** section.

The **Environment Overview** page consists of several useful widgets and some of them are as follows:

1. **Environment Configuration:** This widget offers a detailed snapshot of the specifics of your environment, helping you understand its configuration at a glance.
2. **Release Stats(Last 30 Days):** This widget provides a summary of the release statistics over the last 30 days, showing trends and changes in your releases.
3. **Kubernetes Cluster Details:** This widget provides information about the node types within your Kubernetes cluster.
4. **Cluster Allocation:** This widget shows the CPU and memory usage within your cluster. monitor your cluster's CPU and memory usage.
5. **Resources:** This widget gives a breakdown of Total Resources, Enabled Resources, and Disabled Resources.
6. **Recent Release:** This widget highlights the most recent release of your Environment.
7. **Secrets & Variables:** This widget displays the count of Overridden Secrets and Overridden Variables.

By exploring these widgets, you can get a well-rounded understanding of your environment's status and functionality.

Let's continue by [Linking the Resources.](doc:pet-clinic-linking-resources)