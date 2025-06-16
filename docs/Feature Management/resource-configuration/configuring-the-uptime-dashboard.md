---
title: Configuring the Status Check Monitoring Dashboard
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
## How to configure the Status Check Monitoring Dashboard?

1. Open **Blueprints** and select the required Blueprint. 
2. Select the **Designer** tab and click **Add Resources.**
3. In the pop-up window, search for and select the resource type **Status Check.**
4. Provide a **Name** for the resource and click **Add and View.**  
   **Note:** When creating a resource, it is initially set with default sample values that can be modified after the resource has been created.

   [block:image]{"images":[{"image":["https://files.readme.io/ecd3f78-image.png",null,"Click on the image to expand"],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]
5. Customize the checks to match your specific needs. A sample status check is provided below:

**Example status check:**

In the following case, this configuration will perform a GET request to retrieve the status of the resource. If the status code is 200, it will be marked as healthy.

```Text JSON
"be-check": {
        "url": "http://${service.be.out.interfaces.http.host}/",
        "method": "GET",
        "expected_status_code": "200"
        },
```

You have successfully configured the Uptime Dashboard.

## How to Access the Dashboard?

1. Select the Environment in your defined Blueprint and select the **Tools** tab at the top.
2. Select the **Grafana** tab.
3. Click on the Search button, search for the **Status Check Monitoring** dashboard in the search menu, and open the same.
4. You can now view the status of the resources in a tabular format.

## How to subscribe to Status Check Alert Notifications?

1. Navigate to **Settings > Notifications** to access the Notifications section.
2. Select the **Subscriptions** tab and click **Create Subscription.**
3. Here, mention the **Subscription Name, Notification Type, Blueprint, Channel Type, **and** Channel Name.**
4. Next, click on **Add Filters.** Select **Environment Name** from the dropdown and select the environment.
5. Click **Add Filters** again. This time, select **Alert Name** from the dropdown and select **health_check.**
6. To ensure everything is set up correctly, click **Test Notifications.** This will send a test alert to your chosen channel.
7. Click **Create.**

   [block:image]{"images":[{"image":["https://files.readme.io/0a82864-image.png",null,null],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]

You have successfully set up Status Check Alert Notifications.