---
title: Secrets and Variables
excerpt: Managing Secrets and Variables in Services Using Environment Variables
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
## Concept

When developing services, it's often necessary to provide information that changes depending on the environment. This information can't be hardcoded and includes:

- **Feature Flags:** Change the behaviour of the service from one environment to another.
- **Secrets and Variables:** External keys and secrets needed to interact with services like OpenAI.
- **URLs and Passwords:** Credentials and URLs for dependencies like PostgreSQL databases.

## Common Challenges

Currently, organisations use various methods to handle these configurations:

- Creating environment variables for some settings.
- Storing secrets in secret stores.
- Maintaining environment-specific configuration files.

These approaches can **lead to security risks and human errors**, such as:

- Accidentally exposing passwords while adding them to a secret store.
- Inputting incorrect URLs or credentials.

## Our Solution

We address these challenges by modelling all configurations using environment variables. Here's how it works:

- **Project-Level Secrets and Variables:** Define secrets and variables at the project level that can be referenced by multiple resources using different key names.
- **Resource Variables:** Create environment variables for individual resources, such as feature flags.
- **Direct Connections:** Directly connect to databases or other resources and automatically wire values like URLs, usernames, and passwords.

Our platform injects these variables at runtime, determining their values for each environment. Users can provide default values for project-level secrets and variables or resource variables **which can be overridden at the environment level**. This approach centralises the management of common variables, making it easier and more secure.

## Using Environment Variables in Code

Here are examples of how to use these environment variables in ** Node.js,** and **Python** applications.

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