---
title: Scheduling Releases
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
Facets is a tool that provides the ability to define separate release schedules for each environment. This step-by-step guide will help you create a schedule for your releases in Facets:

## How to Schedule Releases in Facets?

1. Open **Projects** and select the project that contains the desired environment.
2. Select the **Environments** tab and select the Environment.
3. In the **Environment Settings** tab, select **Releases.**
4. Toggle **Available** under **Release Schedule** to create a schedule.
5. If a schedule already exists for this release, you will see the current schedule displayed.
6. Select the desired **Frequency** (in minutes, hours, days, or weeks) and specify the required interval.
7. Enable the **Pause** toggle if you wish to pause this schedule.
8. Click **Save Changes.**

You have successfully created a release schedule in Facets. You can repeat this process for each environment in your system and set a different schedule for each one if needed.

## FAQ

### 1. What happens to a scheduled release when there is a release already queued?

In such scenarios, the scheduled release gets skipped. It does not enter the queue or interrupt the current release process.
