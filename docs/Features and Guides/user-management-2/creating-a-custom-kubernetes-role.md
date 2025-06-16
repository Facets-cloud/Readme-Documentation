---
title: Custom Kubernetes Role
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
Create and customise Kubernetes roles and cluster roles, by defining specific permissions tailored to the project's needs. Additionally, you can modify the permissions of default roles and cluster roles provided by Facets.

## Default Roles and Cluster Roles Provided by Facets

### Roles:

* `cc-read-role`
* `cc-debug-role`

### Cluster Roles:

* `facets-reader-cluster-role`
* `facets-reader-cluster-role-v2`
* `facets-debug-cluster-role`

## Goal

To manage Kubernetes roles and cluster roles via the configuration module (`k8s_access_controls`).

## Steps to Create Custom Kubernetes Roles and Cluster Roles

### 1. Add a Configuration Intent

In your blueprint repository, create a file named `k8s_access_controls.json` under the `configuration/instances` directory with the following content:

```c json
{  
  "kind": "configuration",  
  "for": "k8s_access_controls",  
  "disabled": false,  
  "version": "latest",  
  "spec": {  
    "roles": {},  
    "cluster_roles": {}  
  }  
}
```

### 2. Define Roles and Cluster Roles:

Populate the roles and cluster\_roles sections within the spec as needed. Syntax for Adding Roles and Cluster Roles:

```c json
{  
  "kind": "configuration",  
  "for": "k8s_access_controls",  
  "disabled": false,  
  "version": "latest",  
  "spec": {  
    "roles": {  
      "<role-name>": {  
        "metadata": {  
          "namespace": "default",  
          "annotations": {},  
          "labels": {}  
        },  
        "rules": {  
          "<rule-name>": {  
            "api_groups": [""],  
            "resources": ["pods"],  
            "verbs": ["get"]  
          }  
        }  
      }  
    },  
    "cluster_roles": {  
      "<cluster-role-name>": {  
        "metadata": {  
          "annotations": {},  
          "labels": {}  
        },  
        "rules": {  
          "<rule-name>": {  
            "api_groups": [""],  
            "resources": ["nodes", "persistentvolumes"],  
            "verbs": ["get", "list"]  
          }  
        }  
      }  
    }  
  }  
}
```

### Parameters

* **spec.roles**: List of Kubernetes roles.
  * `<role-name>`: The role name should adhere to the regex `^[a-zA-Z0-9_.-]*$`. If you use the same role name as the default ones, that role will be replaced with the new permissions defined. This is only applicable to default roles created by Facets.
  * **metadata**: Standard role's metadata.
    * **namespace**: Defines the space within which the name of the role must be unique.
    * **annotations**: An unstructured key-value map stored with the role that may be used to store arbitrary metadata.
    * **labels**: Map of string keys and values that can be used to organize and categorize (scope and select) the role.
  * **rules**: Defines a set of permissions for the role. You can add multiple rules with the following attributes:
    * `<rule-name>`: Rule name.
    * **api\_groups**: Name of the APIGroup that contains the resources.
    * **resources**: List of resources that the rule applies to.
    * **verbs**: List of verbs that apply to all the ResourceKinds and AttributeRestrictions contained in this rule.

* **spec.cluster\_roles**: List of Kubernetes cluster roles.
  * `<cluster-role-name>`: The cluster role name should adhere to the regex `^[a-zA-Z0-9_.-]*$`. If you use the same cluster role name as the default ones, that role will be replaced with the new permissions defined. This is only applicable to default cluster roles created by Facets.
  * **metadata**: Standard role's metadata.
    * **annotations**: An unstructured key-value map stored with the role that may be used to store arbitrary metadata.
    * **labels**: Map of string keys and values that can be used to organize and categorize (scope and select) the role.
  * **rules**: Defines a set of permissions for the cluster role. You can add multiple rules with the following attributes:
    * `<rule-name>`: Rule name.
    * **api\_groups**: Name of the APIGroup that contains the resources.
    * **resources**: List of resources that the rule applies to.
    * **verbs**: List of verbs that apply to all the ResourceKinds and AttributeRestrictions contained in this rule.
    * **non\_resource\_urls**: A set of partial URLs that a user should have access to. Since non-resource URLs are not namespaced, this field is only applicable for ClusterRoles referenced from a ClusterRoleBinding. Rules can either apply to API resources (such as "pods" or "secrets") or non-resource URL paths (such as "/api"), but not both.

### 3. Commit and Push Changes

After defining the roles and cluster roles, commit and push the changes to your blueprint repository.

### 4. Perform a Full Release

To apply the changes, perform a FULL release in the environment. It is recommended to first perform a FULL PLAN, review it carefully, and if satisfactory, proceed to APPLY the PLAN.

### 5. Assign Custom Kubernetes Roles to Users

Navigate to the User Management section in Facets.

Select the Roles tab and click.

<br />

# FAQs

1. **Are the custom Kubernetes roles applicable across Projects?** Custom Kubernetes roles are project-specific. If you need the same role in multiple projects, the role definition must be replicated with the same name in each project.
2. **How to assign different Kubernetes roles for a user across different Projects?** Define the same roles in different projects using the same name. Create multiple roles, which would lead to multiple user groups with those roles. Assign multiple user groups to the user.
