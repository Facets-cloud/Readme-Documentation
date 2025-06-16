---
title: Time Sensitive Environments
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
Time Sensitive Environments allow you to automatically schedule when your clusters launch/destroy and scale up/down. This helps optimize resource usage and reduce costs by running environments only when needed.

## Key Features

* Schedule automatic launch and destroy times for environments
* Set up weekly or daily recurring schedules
* Choose between Launch/Destroy or Scale Up/Down operations
* Configure timezone-specific scheduling
* Override schedules manually when needed

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
   * Launch/Destroy: For complete environment shutdown
   * Scale up/Scale down: For resource adjustment
4. Set your frequency:
   * Weekly: For work week schedules
   * Daily: For specific day patterns
5. Configure launch and destroy times:
   * Select days of operation
   * Set specific times for actions
   * Choose your timezone
6. Save your changes

The environment will now automatically follow your schedule, helping optimize resource usage and reduce costs.

### Interactive Demo: How to setup 'Time Sensitive' environments on Facets

<Embed url="https://app.storylane.io/demo/vtq5xxqrc62p" title="Environment Settings | Feb 17 4:17 PM" favicon="https://app.storylane.io/favicon.ico" image="https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_09dd4ea7-8b38-48bf-9009-edf6d2d1f5bc/preview.gif" provider="app.storylane.io" href="https://app.storylane.io/demo/vtq5xxqrc62p" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fvtq5xxqrc62p%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fvtq5xxqrc62p%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_09dd4ea7-8b38-48bf-9009-edf6d2d1f5bc%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22473%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />
