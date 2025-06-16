---
title: Availability Rules for Environments
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
Facets provides the ability to set up Availability Rules for your ephemeral environments. Using these rules, you can set up launch/destroy and scale up/scale down rules in your environments.

## How to create Availability Rules for Environments?

1. Open **Projects** and select the required Project.
2. Select the **Environments** tab and select the desired Environment.
3. Now, select the **Environment Settings** tab and select the **Time Sensitive** tab.
4. Select the **Environment Type** as **Time Sensitive.**
5. Select the type of rule you want to set up - 
   1. **Scale up / Scale down** - This will scale down all deployments, stateful sets and disable any active cronjobs and scale up based on the set rules.
   2. **Launch / Destroy** - This will delete the cluster and all dependent infrastructure resources, and recreate them based on the set rules.
6. Select if you want to enforce the rule daily, or on set days of the week, and choose the time frame for the same. 
7. Click **Save Changes**, and your Availability Rules will be saved for this environment.

You have successfully created Availability Rules for an environment in Facets. You can repeat this process for each environment in your system and set different rules for each one as needed.
