---
title: Dependent Environments
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
The Dependent Environment feature in Facets introduces a new paradigm in environment management by allowing it to inherit infrastructure, tools, and any deployed resources from a designated Base Environment.

This promotes consistency, reduces duplication of efforts, and simplifies maintenance by allowing dependent environments to be updated with changes made to the base environment if needed.

## [When to use this feature?](https://readme.facets.cloud/docs/using-dependent-environments)

## How to create a dependent environment?

1. To Launch an environment as a dependent environment, open the **Projects** menu and select your desired project. 
2. Proceed to the **Environment** tab located on the top panel.\
   Here, you will find a collection of environments associated with your chosen project.
3. Identify the environment you want to launch and click the **Launch** button beside it.
4. This will prompt the **Environment Launch Wizard** to appear on your screen.\
   This wizard comprises of the following steps:
   1. **Connect your Cloud Provider:**
      1. Under the **Infrastructure Type,** choose the option to **Use Existing Infrastructure** to create a dependent environment.
      2. Select the **Base Environment** from which the dependent environment will inherit its infrastructure and settings.
      3. Specify a **Namespace** for where this environment will be set up in the Kubernetes cluster, to organize and isolate resources effectively.
   2. **Review Secrets and Variables:**
      1. You can input the actual values for variables declared in the Blueprint either now or after the launch. However, if you prefer, you can skip the 'Secrets and Variables' tab at this time.
   3. **Review Resources:**
      1. It provides a comprehensive overview of all resources in your environment. 
      2. It also allows you to enable or disable resources prior to launching the environment.
5. Once you have completed these steps, click **Launch Environment.**
6. There are two possible outcomes at this point.
   1. If the launch fails, you can navigate to the 'Release Details' page. This page will provide detailed information about any errors that occurred during the launch, helping you understand and rectify the issue.
   2. If the launch is successful, then congratulations! You have successfully launched an environment in Facets.

### Interactive Demo: How to use Dependent Environments on Facets

<Embed url="https://app.storylane.io/demos/tbrquzt30gkl" title="Releases | Feb 17 3:56 PM" favicon="https://assets.storylane.io/apps/prod/97/icons/favicon.ico" provider="app.storylane.io" href="https://app.storylane.io/demos/tbrquzt30gkl" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Furl%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemos%252Ftbrquzt30gkl%26type%3Dtext%252Fhtml%26schema%3Dstorylane%26display_name%3DStorylane%26src%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Ftbrquzt30gkl%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
