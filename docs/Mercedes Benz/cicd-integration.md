---
title: CI/CD Integration
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
Facets integrates with CI systems to streamline application deployments across environments. Acting as a deployment orchestration layer, it automates build routing, promotion, and release management, simplifying CI/CD workflows and improving visibility and control over deployments. To set up and integrate Facets with your CI/CD pipeline, follow the steps in the [CI/CD Workflow](doc:cicd-workflow) documentation.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/99e4dc089b00ae2db0c4858f2e033ffc3cfc22476f10419f23ac1945319983ee-napkin-selection.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "450px"
    }
  ]
}
[/block]


## Key Features

### Build Routing

- Configure deployment rules to route builds to specific environments.  
  **Example:  **
  - `master` branch → staging → production.  
  - `development` branch → dev environment.  
- Supports custom deployment strategies for flexible workflows.  

### Build Promotion

- Manage the promotion of builds between environments.  
- Options for manual or automated promotion using predefined rules.  

### CLI Integration

- Facets provides a CLI for seamless integration with CI systems.  
- CLI commands can trigger releases, manage environments, and perform deployment-related tasks.  

### Release Management

- View detailed insights for each release, including:  
  - Modified artifacts and version changes.  
  - Differences between releases.  
- Maintain a complete history of releases to track infrastructure and application changes.  

### Docker Image Management

- Attach container images manually to environments.  
- Push images to a container registry and link them to environments within Facets.  

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/d00b91c750448d4bc15ee6f3dc6df54cc45ad059469ed1f8bcae3486e34be630-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "650px",
      "border": true
    }
  ]
}
[/block]