---
title: Backstage.io Integration
excerpt: Integrate Facets into Backstage to enhance the developer experience.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Facets is now available as a plugin in Backstage, enabling teams to seamlessly integrate release orchestration within their developer portal. With this plugin, you can:

- View and manage controlled shifts directly from Backstage.
- Monitor deployment progress and troubleshoot issues in real time.
- Automate and standardize release workflows across teams.

This plugin is listed in the [Backstage Plugin Marketplace](https://backstage.io/plugins/) under the **Deployment** category.

## Key Features

This integration is designed for platform engineers aiming to reduce developers' cognitive load by providing fast feedback mechanisms. Familiarity with Backstage is essential to effectively implement this integration and offer developers a comprehensive overview of performance, along with entry points for deeper investigations.

The Facets Cloud plugin provides three main components for your Backstage entity pages:

### Environment Overview

Shows all environments deployed for a specific resource in Facets.cloud, helping teams understand what's running where.

![](https://files.readme.io/1f3495597cd2dfae40d2e1cbd84fd9c7b0603c6bf78a9c6d31be5d4680c51416-Release_Approval_Workflow.png)

### Release History

Displays deployment history and lets users trigger new releases directly from Backstage.

![Release History](https://raw.githubusercontent.com/Facets-cloud/facets-backstage-plugin/main/backstage-plugins/plugins/facets-cloud/screenshots/release-history.png)

### Terraform Outputs

Provides access to infrastructure details like endpoints, connection strings, and other Terraform outputs.

![Terraform Outputs](https://raw.githubusercontent.com/Facets-cloud/facets-backstage-plugin/main/backstage-plugins/plugins/facets-cloud/screenshots/terraform-outputs.png)

## **Prerequisites**

- **Backstage Instance**: You can either integrate this into an existing Backstage app or set up a new one.
- **Node.js & Yarn**: Required for package installation.
- **Facets.cloud Account**: Sign up at [Facets.cloud](https://facets.cloud) and generate an API key.
- **Backstage Plugin Knowledge** (optional): Refer to [Backstage Plugin Docs](https://backstage.io/docs/plugins/installing-a-plugin) for additional details.

## Installation Guide

### Step 1: Install Both Plugins

First, install both the frontend and backend plugins:

```bash
# Install backend plugin
yarn workspace backend add @facets-cloud/backstage-plugin-backend

# Install frontend plugin
yarn workspace app add @facets-cloud/backstage-plugin
 
```

### Step 2: Configure the Backend

Register the backend plugin in your Backstage backend:

```bash
// In packages/backend/src/index.ts
backend.add(import('@facets-cloud/backstage-plugin-backend'));
backend.start();
```

### Step 3: Add Configuration

Configure your Backstage instance to connect to Facets.cloud by adding the following to your app-config.yaml:

```
proxy:
  endpoints:
    '/facets/api':
      target: ${FACETS_CONTROL_PLANE_URL}

facets-cloud:
  controlPlaneUrl: ${FACETS_CONTROL_PLANE_URL}
```

You can optionally add shared authentication (though user-level auth is recommended):

```
facets-cloud:
  controlPlaneUrl: ${FACETS_CONTROL_PLANE_URL}
  auth:
    username: ${FACETS_USER_NAME}
    accessToken: ${FACETS_ACCESS_TOKEN}
```

For more information on configuring Backstage, see the [official configuration documentation.](https://backstage.io/docs/conf/)

### Step 4: Add the Settings Page

Add the Facets.cloud settings page to allow users to configure their individual credentials. You can find the same in [packages/app/src/App.tsx.](https://github.com/Facets-cloud/facets-backstage-plugin/blob/c0cc5907967d2de4f4c269002b2c23e184166611/backstage-plugins/packages/app/src/App.tsx#L4)

### Adding Facets Components to Entity Pages

Now that the plugins are installed, you can add Facets components to your entity pages.

**Step 1: Link Entities to Facets Resources** : First, ensure your entities are linked to Facets resources by adding annotations to your entity YAML files:

**Step 2: Add Components to Entity Overview** : Now you can add the Facets components to your entity pages. You can add all components or select just the ones you need for your use case in the [EntityPage.tsx](https://github.com/Facets-cloud/facets-backstage-plugin/blob/c0cc5907967d2de4f4c269002b2c23e184166611/backstage-plugins/packages/app/src/components/catalog/EntityPage.tsx)

## User Authentication

For the best experience, users should configure their own Facets.cloud credentials:

**Obtain credentials from Facets Control Plane:**

1. Log in to Facets Control Plane
2. Click on your profile picture
3. Go to "Account Settings" → "Personal Token"
4. Click "Generate Token" and copy the token

**Configure in Backstage:**

1. Navigate to Settings → Facets.Cloud in Backstage
2. Enter your username and token
3. Click "Save"

***

## Troubleshooting

### Components not appearing

- Verify entity annotations are correctly configured  
- Check user has valid credentials configured  

### Connection errors

- Ensure `controlPlaneUrl` is correct  
- Verify API credentials have proper permissions  
- Check network connectivity to Facets Control Plane  

### Authentication issues

- Try regenerating your personal token  
- Ensure username matches your Facets.Cloud account

***

### Development

For developers who want to contribute to the Facets.Cloud plugin:

#### Clone the repository:

```bash
git clone https://github.com/Facets-cloud/facets-backstage-plugin.git
```

#### Install dependencies:

```bash
cd facets-backstage-plugin
yarn install
```

#### Start the development environment:

```bash
yarn dev
```