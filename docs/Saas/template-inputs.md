---
title: Template Inputs
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
In many business contexts, it is often necessary to deploy multiple instances of the same resource, whether those are applications or other infrastructure components. For example, you might need to provide a unique instance of an application for each tenant within an environment. Facets allows you to achieve this through **Templated Resources.**

This setup is completely transparent to the end-user. The underlying infrastructure is shared but logically isolated, with fully centralized services.

With templated resources, you can establish distinct silos for users and configurations within a single environment. These silos can be tailored to represent different customers, business units, subsidiaries, or other divisions aligned with your business structure.

## Getting Started with Template Inputs

This guide will help you define your own templated resources in Facets and assign values per tenant. We will walk you through the entire process, covering the definition, setup, instantiation, and release process when using template inputs.

1. [Define Templated Resources](doc:template-inputs#how-to-define-a-new-template-input)
2. [Define Mustache Files](doc:template-inputs#how-to-define-a-mustache-file-for-resource-types-that-need-to-be-templatized)
3. [Create a Template Input in Control Plane](doc:template-inputs#how-to-create-a-template-input-in-the-control-plane)
4. [Perform a Release](doc:template-inputs#how-to-perform-a-release)

### Steps to configure Template Inputs

1. **Define a New Template Input Type:** Start by specifying the new template input type in your blueprint definition.
2. **Define a Mustache File:** Define a mustache file for the resource type that needs to be templated in your blueprint definition.
3. **Create Inputs in the Control Plane:** Next, create inputs of this type in the Control Plane for the environment where you intend to use the template.
4. **Perform a Release:** Finally, perform a release to instantiate multiple replicas of a resource in your multitenant setup with Facets.

## How to define a new Template Input?

To define a Template Input, follow these steps:

1. **Create the Required Folder Structure:**\
   Create a folder named `template_input_type/instances` within your blueprint definition.
2. **Define Your Template Input:**\
   Inside the instances folder, create a JSON file to specify your Template Input.
   * The Template Input will appear in the Control Plane with the name of the file you have created.
   * For instance, if you name the file **customers.json**, it will be displayed as **customers** on the Template Input UI in your Control Plane.
3. **Configure the JSON:**\
   The JSON file you create should include the necessary fields that will define your template based on your business logic.
   * `"fields":` An array of field names that will be used to define the template input. These fields should correspond to the attributes you need to specify for each tenant or instance.
   * Replace `<field1>`, `<field2>`, and `<field3>` with actual field names relevant to your setup.

```Text JSON
{
  "spec": {
    "fields": ["<field1>", "<field2>", "<field3>"]
  }
}
```
```Text Example
{
  "spec": {
    "fields": ["designation", "customer_id"]
  }
}
```

In the example JSON, the `"fields"` array includes the keys `designation` and `customer_id`, which will be used to define the template input. Adjust these fields according to your specific business needs.

## How to define a Mustache file for resource types that need to be templatized?

Facets uses Mustache, a logic-less templating system. Using Mustache allows you to create and use pre-written text files with placeholders that will be replaced at run-time with values specific to a given request. For more information, refer to the [Mustache Manual.](https://mustache.github.io/mustache.5.html)

To Create a Mustache File, follow these steps:

1. **Create the Mustache File:**\
   Create a `.mustache` file in the `<resource_type>/instances` directory of the resource where you want to create template inputs.
2. **Specify the Template Input:**\
   In your Mustache file, use the JSON key `"templatedOn"` to specify which template input to use with the template.\
   **For example:** `"templatedOn": "customers"`

This setup will generate one replica for each tenant defined in your Control Plane.

### Sample Mustache file

#### Sample Application

As an example, if your application takes `customer_id` and `designation` as inputs, the following Mustache JSON file creates one instance per defined customer and passes the respective `customer_id` and `designation` fields as arguments to the application.

* Notice the key `templatedOn` is mapped to the defined Template Input file name.

```Text JSON

{
  "kind": "service",
  "version": "0.1",
  "disabled": false,
  "templatedOn": "customers",
	"spec": {
		"type": "application",
		"enable_host_anti_affinity": false,
		"release": {
			"build": {
				"artifactory": "default",
				"name": "demo_be"
			},
			"strategy": {
				"type": "RollingUpdate",
				"max_available": 1,
				"max_unavailable": 0
			},
			"image": "${blueprint.self.artifacts.demo-be}"
		},
		"env": {
			"TITLE": "${blueprint.self.variables.TITLE}-{{current.uid}}",
			"DESIGNATION": "{{current.data.designation}}",
      "CUSTOMER_ID": "{{current.data.customer_id}}"
		},
		"runtime": {
			"health_checks": {
				"liveness_url": "/api/employees",
				"readiness_url": "/api/employees",
				"port": "5200",
				"start_up_time": 21,
				"timeout": 100,
				"period": 10
			},
			"ports": {
				"http": {
					"port": "5200",
					"protocol": "tcp"
				}
			},
			"size": {
				"cpu": "100m",
				"memory": "110Mi"
			}
		}
	}
}
```

* To refer to any field in the template input, you can use `current.data.<field_name>`.
  * For example, `{{current.data.customer_id}}` or `{{current.data.designation}}`.
* However, to refer to the unique ID assigned when creating a new customer in the Control Plane, use `{{current.uid}}`.

#### Sample Ingress

The following Mustache JSON file demonstrates how to create an ingress configuration that links to multiple services. This configuration uses the `uid` to uniquely identify each customer's frontend and backend services. 

* Notice the key `templatedOn` is not used here because the same ingress configuration can be shared across different applications, and it dynamically links to the services.

```Text JSON
{
  "flavor": "nlb_nginx",
  "disabled": false,
  "version": "0.1",
  "kind": "ingress",
  "metadata": {
    "name": "main",
    "annotations": {
      "nginx.ingress.kubernetes.io/use-regex": "true"
    }
  },
  "spec": {
    "basicAuth": false,
    "private": false,
    "force_ssl_redirection": true,
    "rules": {
        {{/customers}}
      "frontend-{{uid}}": {
        "comment": "front-end {{uid}}",
        "domain_prefix": "",
        "path": "/",
        "port": "${service.ui-{{uid}}.out.interfaces.main.port}",
        "service_name": "${service.ui-{{uid}}.out.interfaces.main.name}"
      },
      "backend-{{uid}}": {
        "comment": "back-end {{uid}}",
        "domain_prefix": "",
        "path": "/",
        "port": "${service.be-{{uid}}.out.interfaces.http.port}",
        "service_name": "${service.be-{{uid}}.out.interfaces.http.name}"
      },
        {{/customers}}
      "common": {
        "comment": "common",
        "domain_prefix": "common",
        "path": "/",
        "port": "${service.common.out.interfaces.http.port}",
        "service_name": "${service.common.out.interfaces.http.name}"
      }
    }
  }
}
```

* In this example, any rules inside the `{{#customers}}...{{/customers}}` block will be replicated for each key in `customers` template input. 
* The placeholder `{{uid}}` is used to uniquely identify each customer's frontend and backend services.

## How to create a template input in the Control Plane?

Template Inputs in your Control Plane will require you to provide a unique ID for each defined input. This can be any string of alphanumeric characters. The other fields are parsed directly from the defined JSON file in your blueprint definition.

1. Navigate to the environment where you want to define the template and select the **Template Inputs** tab.
2. Click on the **Create New customers** button.
   * The button says **customers** here because it reflects the name of the file in the `template_input_type/instances` folder. You can change this by renaming the file in that folder.
3. Enter the necessary details in the pop-up that appears.
4. Click **Save.**

## How to Perform a Release?

Perform a Full Release from the Releases screen, and all your templated resources should materialize as defined. For more information refer to the [Performing a Release](doc:performing-releases) documentation. 

Your templated resources have been successfully created and deployed.
