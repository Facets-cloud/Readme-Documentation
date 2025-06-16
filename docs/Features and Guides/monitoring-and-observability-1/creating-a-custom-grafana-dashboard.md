---
title: Creating a Custom Grafana Dashboard
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
> 📘 
> 
> **Note:** This feature is only available in the Enterprise Plan.

### Prerequisite

Ensure you have write access to the Blueprint, access to overrides, and the ability to perform a full release.

## How to create a Custom Grafana Dashboard?

1. Open the **Projects** tab and select the required project. 
2. Select the desired environment in which you wish to create a grafana dashboard.
3. Here, select **Tools > Grafana.**
4. In Grafana, select **Dashboard > New Dashboard **and click **Add a new panel.**
5. Under the **Query** section, input your queries and click **Apply.**  
   For instance, creating a dashboard to monitor the node count in time series.
6. Click the **Save** icon. Here, mention the **Dashboard Name** and click **Save.**

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/0b8ef2e-creating_grafana_dashboard.gif",
        null,
        "Click on the image to expand"
      ],
      "align": "center",
      "sizing": "450px",
      "border": true,
      "caption": "Click on the image to expand"
    }
  ]
}
[/block]


You have successfully created a custom Grafana dashboard.

## How to add the Custom Grafana Dashboard in Facets?

1. Click on the **Share dashboard or panel** icon.
2. In the pop-up, select the **Export** tab and click **Save to file.** The JSON file will be saved locally.
3. Navigate to the **Designer** tab of this Project.
4. Click **Add Resource,** then search for and select the **Grafana dashboard.**
5. Select the **Flavor,** enter the **Resource Name** and click **Add & View.**
6. Edit the JSON. In `annotations` section, replace the current contents with the contents of the locally saved JSON file.
7. Click **Save Changes.**
8. Enable the resource and perform a **Full Release.**

You have successfully deployed a custom Grafana dashboard tailored to your specific monitoring needs.