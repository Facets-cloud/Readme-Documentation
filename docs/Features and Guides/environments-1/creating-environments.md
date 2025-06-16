---
title: Creating Environments
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
Environments in Facets represent the deployment destinations for your Blueprint. Each environment serves as a distinct space where your Blueprint is deployed with its own configuration and resources.

## Common Use Cases

### Development Pipeline

Create environments for different stages of development (DEV, QA, PROD) to maintain separation of concerns.

### Testing Environments

Set up isolated environments for testing new features or running quality assurance processes.

### Production Deployments

Establish stable production environments with specific release streams and configurations.

## How to Create an Environment

1. Access Environment Creation:
   - Navigate to your project
   - Select **Environments** tab
   - Click **Create Environment** button

2. Configure Environment:
   - Enter a unique **Environment Name**
   - Select appropriate **Release Stream**
   - Click **Create**

3. Post-Creation:
   - Environment appears with **STOPPED** status
   - Use **Launch** button to deploy to a cloud of your choice. 
   - Monitor status in the environments page

Your new environment is ready for configuration and deployment after completion.

### Interactive Demo: How to Create an Environment on Facets

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fcfh5tc7h03cw&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemos%2Fcfh5tc7h03cw&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_de58d977-156f-4675-81d0-02f8c6c06971%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demos/cfh5tc7h03cw",
  "title": "Environments | Feb 20 6:43 PM",
  "favicon": "https://assets.storylane.io/apps/prod/99/icons/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_de58d977-156f-4675-81d0-02f8c6c06971/preview.gif",
  "provider": "https://www.storylane.io",
  "href": "https://app.storylane.io/demos/cfh5tc7h03cw",
  "typeOfEmbed": "jsfiddle"
}
[/block]