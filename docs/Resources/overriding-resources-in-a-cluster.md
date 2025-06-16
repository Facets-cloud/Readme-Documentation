---
title: Overriding Resources in an Environment
excerpt: Learn how to override different types of resources defined in your blueprint
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Facets provides the capability to override the configuration for any resources in an environment from the Control Plane.

## Prerequisites

* The environment you are using should have at least one defined resource in it to be able to override it. 

## Override a resource from the Control Plane

> 📘
>
> For a given blueprint and environment, you can find all the defined resources under the Resources tab in the sidebar.

1. Login to Facets Control Plane. 
2. Select the Environment in your defined Blueprint.

<Image alt="Select the environment (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/e847578-env_page.png">
  Select the environment (Click on the image to expand)
</Image>

3. Navigate to the Resources tab from the sidebar and select the resource that you want to override.

<Image alt="Select the Resource (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/981f29d-appingress.png">
  Select the Resource (Click on the image to expand)
</Image>

4. You will now be able to view the Configuration screen where you can find currently defined values for that resource.

> 📘 NOTE
>
> All defined resources except for type `application `will directly open the **Configuration** screen for that resource.
>
> Resources that are of type `application `will direct the user to the **Live Release** tab. The **Configuration** tab can be accessed next to the Live Release tab. 
>
> See [Override resources of type `application `](https://readme.facets.cloud/docs/overriding-resources-in-a-cluster#override-resources-of-type-application)for more information.

5. Click on the Override button, this will open a new page.

<Image alt="Override Button (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/afae04d-override_appingress.png">
  Override Button (Click on the image to expand)
</Image>

6. You can set new values or update any of the predefined values in this page. You can also view the original configuration as defined in the blueprint.

<Image alt="View current configuration (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/3370d3b-blueprint_config.png">
  View current configuration (Click on the image to expand)
</Image>

7. Click the Submit button to submit your override. 

<Image alt="Submit the override (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/00dcf81-submit_override.png">
  Submit the override (Click on the image to expand)
</Image>

8. You will now be able to view the Review Changes screen.

<Image alt="Review Changes (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/9a68d2a-review_changes.png">
  Review Changes (Click on the image to expand)
</Image>

9. Click Save Changes button and you will see a popup toaster confirming the change with a message that this change will be applied in the next release.

<Image alt="Success Toaster (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/e5fb656-success_toaster.png">
  Success Toaster (Click on the image to expand)
</Image>

### Override resources of type `application `

> 📘
>
> The override screen for resources that are of type `application` has two modes:
>
> * **Form Mode**
> * **JSON Mode**

You can override defined parameters for **Container Configuration** and **User-defined Variables** in **Form Mode**. 

<Image alt="Override `application` (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/955960a-override_backend.png">
  Override `application` (Click on the image to expand)
</Image>

You can also toggle to **JSON Mode** to get an override page matching all the other resources where you can input values from your keyboard. 

<Image alt="Toggle JSON Mode (Click on the image to expand)" align="center" width="450px" border={true} src="https://files.readme.io/259c897-json_mode.png">
  Toggle JSON Mode (Click on the image to expand)
</Image>

## Constraints

The overridden configuration as changed by a user will only be enforced on the next release of the environment.
