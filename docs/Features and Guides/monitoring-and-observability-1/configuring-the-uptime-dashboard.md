---
title: Configuring the Status Check Monitoring Dashboard
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
> 📘 
> 
> **Note:** This feature is only available in the Enterprise Plan.

## How to configure the Status Check Monitoring Dashboard?

1. Open **Projects** and select the required Project. 
2. Select the **Blueprint** tab.
3. In the **Add Resources** pop-up, search for and select the resource type **Status Check.**
4. Select the Flavor and provide a **Name** for the resource and click **Add.**  
   **Note:** When creating a resource, it is initially set with default sample values that can be modified after the resource has been created.
5. Override the resource and customize the checks to match your specific needs. A sample status check is provided below:

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
2. Click to **Open** the **Grafana** tab.
3. Click on the Search button, search for the **Status Check Monitoring** dashboard in the search menu, and open the same.
4. You can now view the status of the resources in a tabular format.

## How to subscribe to Status Check Alert Notifications?

1. Navigate to **Settings > Notification Center** to access the Notifications section.
2. Select the **Subscriptions** tab and click **Create Subscription.**
3. Here, mention the **Subscription Name, Notification Type, Blueprint, Channel Type, **and** Channel Name.**
4. Next, click on **Add Filters.** Select **Environment Name** from the dropdown and select the environment.
5. Click **Add Filters** again. This time, select **Alert Name** from the dropdown and select **health_check.**
6. To ensure everything is set up correctly, click **Test Notifications.** This will send a test alert to your chosen channel.
7. Click **Create.**

You have successfully set up Status Check Alert Notifications.