---
title: Environment Specific Configurations
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
When developing applications, it's often necessary to provide information that changes depending on the environment.

This information can't be hardcoded and includes:

* **Feature Flags:** Change the behavior of the application from one environment to another.
* **Secrets and Variables:** External keys and secrets needed to interact with services like OpenAI.
* **URLs and Passwords:** Credentials and URLs for dependencies like PostgreSQL databases.

## Common Challenges

Currently, organizations use various methods to handle these configurations:

* Creating environment variables for some settings.
* Storing secrets in secret stores.
* Maintaining environment-specific configuration files.

These approaches can lead to security risks and human errors, such as:

* Accidentally exposing passwords while adding them to a secret store.
* Inputting incorrect URLs or credentials.

## Our Solution

We address these challenges by modeling all configurations using environment variables. Here's how it works:

* **Service-Specific Variables:** Create environment variables for individual services, such as feature flags.
* **Project-Level Secrets and Variables:** Define secrets and variables at the project level that can be referenced by multiple services using different key names.
* **Direct Connections:** Directly connect to databases or other resources and automatically wire values like URLs, usernames, and passwords.

Our platform injects these variables at runtime, determining their values for each environment. You can provide default values for project-level or service-level variables and secrets, which can be overridden at the environment level. This approach centralizes the management of common variables, making it easier and more secure.

## Using Environment Variables in Code

Here are examples of how to use these environment variables in **Spring Boot, Node.js,** and **Python** applications.

### Spring Boot

In Spring Boot, if you define an environment variable with the same key as in your `application.properties` file, the value from Facets.cloud will automatically take precedence over the value set in the file. This means you don't need to change anything in your `application.properties`.

#### Using `@Value Annotation`

```Text Java
import org.springframework.beans.factory.annotation.Value;
import org.springframework.stereotype.Component;

@Component
public class MyService {

    @Value("${MY_ENV_VARIABLE}")
    private String myEnvVariable;

    public void printEnvVariable() {
        System.out.println("Environment Variable: " + myEnvVariable);
    }
}
```

#### Using `application.properties`

In `application.properties`, you can have a default value:

```java java
properties

spring.datasource.url=jdbc:postgresql://localhost:5432/mydb
```

When you set spring.datasource.url as an environment variable in Facets.cloud, it will override the value from the file at runtime.

### Node.js

```Text Javascript
const myEnvVariable = process.env.MY_ENV_VARIABLE;

console.log(`Environment Variable: ${myEnvVariable}`);
```

### Python

```Text Python
import os

my_env_variable = os.getenv('MY_ENV_VARIABLE')

print(f'Environment Variable: {my_env_variable}')
```

By following these practices and using Facets.cloud, you can efficiently manage environment-specific configurations, reduce security risks, and minimize human errors.
