---
title: Availability Rules for Environments
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
Facets provides the ability to set up Availability Rules for your ephemeral environments. Using these rules, you can set up launch/destroy and scale up/scale down rules in your environments.

> 📘 
> 
> Availability rules can only be configured if the **Environment Type** is set as **Ephemeral** under Advanced Options in Create Environment screen.  
> Facets recommends setting only development environments as Ephemeral.

## How to create Availability Rules for Environments?

1. Open **Blueprints** and select the required Blueprint.
2. Select the **Environments** tab and select the desired Environment.
3. Now, select the **Overview** tab.
4. Click on the **Create Availability Rules** button in the **Availability Rules** widget.  
   If you want to edit the existing rules, click on the **Edit** button in the **Availability Rules** widget.
5. Select the type of rule you want to set up - 
   1. **Scale up / Scale down** - This will scale down all deployments, stateful sets and disable any active cronjobs and scale up based on the set rules.
   2. **Launch / Destroy** - This will delete the cluster and all dependent infrastructure resources, and recreate them based on the set rules.
6. Select if you want to enforce the rule daily, or on set days of the week, and choose the time frame for the same. 
7. Click **Save Changes**, and your Availability Rules will be saved for this environment.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/5e9eec1-image.png",
        null,
        null
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


You have successfully created Availability Rules for an environment in Facets. You can repeat this process for each environment in your system and set different rules for each one as needed.