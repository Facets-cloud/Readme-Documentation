---
title: Types of Validations
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
> 📘
>
> **Note:** This feature is only available in the Enterprise Plan.

The Validation Summary Panel tracks all validation issues that may arise from faults in the resource JSON configuration, serving as a central hub for identifying potential errors and broken references. By providing immediate visibility into these issues, the panel helps you quickly pinpoint errors, avoid release failures, and boost developer productivity.

## What are the types of Validations?

**Note:** All validations have a severity of either `Error` or `Warning`. If any validation issues with "Error" severity are present, the release will not be triggered.

The following are the types of validations:

* REFERENCE\_ERROR("Non-Existent Resource Reference"),
* DISABLED\_RESOURCE\_REFERENCE("Disabled Resource References"),
* INVALID\_REFERENCE\_EXPRESSION("Invalid Reference Expression"),
* SYNTAX\_ERROR("Syntax Error"),
* GUARDRAILS\_POLICY\_ERROR("GuardRails Compliance Issues");

### Non-Existent Resource Reference

This error occurs when a resource JSON refers to a resource that does not exist.

**Example:** This error occurs if the resource "new-test-service" referred to in the rules below does not exist.

```
{  
  "spec": {  
    "basicAuth": false,  
    "private": false,  
    "force_ssl_redirection": true,  
    "rules": {  
      "backend": {  
        "comment": "back-end",  
        "domain_prefix": "",  
        "path": "/api/employees/",  
        "port": "${service.new-test-service.out.interfaces.http.port}",  
        "service_name": "${service.new-test-service.out.interfaces.http.name}"  
      }  
    }  
  }  
}
```

### Disabled Resource Reference

This error occurs when a resource JSON refers to a resource that exists but is marked as disabled, meaning the resource JSON is trying to access a resource that is currently not available for use.

**Example:** This error occurs if the resource "new-test-service" referred to in the rules below is disabled.

```
{  
  "spec": {  
    "basicAuth": false,  
    "private": false,  
    "force_ssl_redirection": true,  
    "rules": {  
      "frontend": {  
        "comment": "front-end",  
        "domain_prefix": "",  
        "path": "/",  
        "port": "${service.new-test-service.out.interfaces.main.port}",  
        "service_name": "${service.new-test-service.out.interfaces.main.name}"  
      }  
    }  
  }  
}
```

### Invalid Reference Expression

This error occurs when a reference expression in a resource json is not correctly formed or refers to undefined variables, secrets, or artifacts. This could include syntax errors, incorrect usage of reference expressions, attempts to access non-existing variables, secrets, or artifacts, etc. This error is designed to catch issues with the structure and use of reference expressions in the resource json.

**Example:** This error occurs if the secret "non-existing-secret" referred to in the configuration is not present.

```
{  
  "env": {  
    "secret_for_prod": "${blueprint.self.secrets.non-existing-secret}"  
  }  
}
```

### Syntax Error

This error occurs when the resource JSON is invalid, often due to syntax issues like missing commas or incorrect formatting.

**Example:** In the below JSON file, there is a comma missing in line 2 after "VM". So we will see an error as shown in the image.

```
{  
  "flavor": "VM"  
  "metadata": {  
    "labels": {}  
  },  
  "kind": "service",  
  "disabled": true,  
  "provided": false,  
  "version": "0.11",  
  "spec": {}  
}
```

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/1aab76e36615b35ad9308ff5dc8acc5799a3bc5c6ddd460bcaef27b531b97c80-image.png">
  Click on the image to expand
</Image>

### Guardrails Policy Error

This error occurs when a defined guardrail policy is violated. Guardrail policies are set to enforce specific rules or standards, and any deviation from these can trigger this error.

**Example:** The file shown in the image is not adhering to the guardrails policy defined.

<Image alt="Click on the image to expand" align="center" width="450px" border={true} src="https://files.readme.io/6b55e1303c0652342cd2aff2760f67ef0bff9ccdf41a12e0e2fdce380551d56a-image.png">
  Click on the image to expand
</Image>
