---
title: Overriding Resources in an Environment
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
Facets provides the flexibility to directly modify any resource configurations in an environment from the Control Plane. This feature is particularly useful when there is a need to make modifications in the environment that will deviate from the Blueprint. Using overrides, you can make any specific changes needed as per your use case.

## How to Override Resources for an Environment?

1. Open the **Projects** tab and select your desired project.
2. Select the **Resource Center** tab and select the environment where the values need to be updated.
3. Select the desired resource and Click on **Overrides** tab
4. Update the desired values in the **Form** or **JSON** mode and click **Save Changes.**

**Note:** Any changes made to the overridden configuration will only take effect after the next release.

You have successfully overridden the Resource for an Environment.

## Resource Overrides Delete

Users might want to **delete overridden value of a field across environments** and set it to default or **delete all the overrides of a particular environment**.

* In any such cases, users can go to "Overrides Summary" tab present in the resource side-pane and select the overrides that they want to delete.
* Once **deleted, the values will be set to the default blueprint value** of that field.

<Embed typeOfEmbed="jsfiddle" url="https://app.storylane.io/demo/al9wsvujykru" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Furl%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fal9wsvujykru%26type%3Dtext%252Fhtml%26schema%3Dstorylane%26display_name%3DStorylane%26src%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fal9wsvujykru%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" href="https://app.storylane.io/demo/al9wsvujykru" providerUrl="https://www.storylane.io" providerName="Storylane" />