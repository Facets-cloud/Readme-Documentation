---
title: Time Sensitive Environments
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
Time Sensitive Environments allow you to automatically schedule when your clusters launch/destroy and scale up/down. This helps optimize resource usage and reduce costs by running environments only when needed.

## Key Features

- Schedule automatic launch and destroy times for environments
- Set up weekly or daily recurring schedules
- Choose between Launch/Destroy or Scale Up/Down operations
- Configure timezone-specific scheduling
- Override schedules manually when needed

## Common Use Cases

### Development Environments

Run dev clusters only during work hours (9 AM - 6 PM) and automatically shut down on weekends to save costs.

### Testing Environments

Schedule test environments to launch before QA team starts and scale down during off-hours.

### Demo Environments

Automatically provision demo environments before client presentations and clean up afterward.

## How to Configure Time Sensitive Environments

1. Access your environment settings in Facets dashboard
2. Select "Time Sensitive" as Environment Type
3. Choose your scheduling rule:
   - Launch/Destroy: For complete environment shutdown
   - Scale up/Scale down: For resource adjustment
4. Set your frequency:
   - Weekly: For work week schedules
   - Daily: For specific day patterns
5. Configure launch and destroy times:
   - Select days of operation
   - Set specific times for actions
   - Choose your timezone
6. Save your changes

The environment will now automatically follow your schedule, helping optimize resource usage and reduce costs.

### Interactive Demo: How to setup 'Time Sensitive' environments on Facets

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fvtq5xxqrc62p&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fvtq5xxqrc62p&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_09dd4ea7-8b38-48bf-9009-edf6d2d1f5bc%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/vtq5xxqrc62p",
  "title": "Environment Settings | Feb 17 4:17 PM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_09dd4ea7-8b38-48bf-9009-edf6d2d1f5bc/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/vtq5xxqrc62p",
  "typeOfEmbed": "jsfiddle"
}
[/block]