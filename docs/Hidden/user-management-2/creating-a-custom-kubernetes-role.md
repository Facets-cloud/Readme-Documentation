---
title: Creating a Custom Kubernetes Role
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
Facets allows you to create custom Kubernetes roles, enabling you to define specific permissions tailored to your project's needs. This guide provides concise steps for setting up and assigning these roles, ensuring users have appropriate access to Kubernetes resources.

## How to create a Custom Kubernetes Role?

1. Open the **Projects** tab and select the desired project.
2. In the **Blueprint** tab, search for and click on the **k8s\_access\_control** resource.
3. Select **Configurations** from the dropdown.
4. In the **Configurations** tab, select the **JSON** tab and edit the resource JSON.
5. Under `"spec"` create the required roles.
6. Refer to the [Add k8s roles and cluster roles](https://doc.clickup.com/3443930/p/h/3936u-76896/b69a21f55727847) runbook for detailed instructions on how to configure the resource.
7. Click **Save Changes.**

You have successfully created the Kubernetes Roles in Facets.

## How to assign Custom Kubernetes Roles to Users?

1. Open the **Settings** tab and select **User Management.**
2. Select the **Roles** tab and click on the **Create Custom Role** button.
3. Add basic information for this custom role, such as **Name** (mandatory) and **Description.**
4. In the **Kubernetes Permissions** dropdown, select **Custom.**
5. Now, mention the **Role** and/or **Cluster Role** you created in [this section. ](doc:creating-a-custom-kubernetes-role#how-to-create-a-custom-kubernetes-role)
6. You can also select other specific permissions you want to assign to this custom role. 
7. Click on the **Add Role** button.

You have successfully created a Custom Role.

## FAQs

### 1. Can I assign multiple Kubernetes roles to a single user?

No, you can only assign one role and one cluster role to a single user by mentioning Role and Cluster Role.

## 2. How do I assign specific permissions to a custom Kubernetes role?

In the `spec` section`k8s_access_control` resource, specify the required permissions. Refer to the [Add k8s roles and cluster roles](https://doc.clickup.com/3443930/p/h/3936u-76896/b69a21f55727847) runbook for detailed instructions on how to configure the resource.
