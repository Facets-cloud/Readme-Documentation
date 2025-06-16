---
title: Scheduling Releases
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
Release Scheduling allows you to automate and control the deployment of releases across different environments. This feature helps maintain consistent deployment patterns and ensures regular updates to your applications.

## Key Features

- Schedule releases at custom intervals (minutes, hours, days, or weeks)
- Set different schedules for each environment
- Pause scheduled releases without affecting manual deployments
- Maintain separate release cycles for different environments
- Override schedules when needed with manual releases

# Release Scheduling in Facets

## Common Use Cases

### Development Environment

Schedule frequent releases (every few hours) to ensure rapid integration of new features and bug fixes.

### QA Environment

Set up daily releases to provide testers with the latest stable code for thorough testing.

### Staging Environment

Configure weekly releases to match production deployment patterns and validate major changes.

## How to Configure Release Scheduling

1. Navigate to your environment:
   - Open **Projects**
   - Select your project
   - Go to **Environments** tab
   - Choose your environment

2. Access release settings:
   - Select **Environment Settings**
   - Click on **Releases**

3. Configure your schedule:
   - Toggle **Available** to enable scheduling
   - Select frequency:
     - Minutes: For rapid deployment cycles
     - Hours: For daily development cycles
     - Days: For longer testing cycles
     - Weeks: For production-like environments
   - Enter the release interval
   - Use **Pause** toggle to temporarily stop scheduled releases

4. Save your configuration
   - Click **Save Changes** to activate the schedule

Your environment will now automatically deploy releases according to the configured schedule while still allowing manual releases when needed.

### Interactive Demo: How to schedule a release on Facets.

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fmaciqnme2jja&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fmaciqnme2jja&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_daf0ad98-ee90-4d76-8392-d94a2403ac00%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"473\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/maciqnme2jja",
  "title": "Overview | Feb 17 4:36 PM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_daf0ad98-ee90-4d76-8392-d94a2403ac00/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/maciqnme2jja",
  "typeOfEmbed": "jsfiddle"
}
[/block]