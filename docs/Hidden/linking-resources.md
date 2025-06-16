---
title: Linking Resources
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
## How to link Resources?

Linking resources refers to establishing connections between different resources, enabling them to interact and share information with each other.

## Linking a Postgres resource to a Service resource

In this example, we will be linking a Postgres resource to a Service resource using Environment Variables.

1. First, ensure you have both a Service and a Postgres resource created within your Blueprint.
2. Navigate to the **Blueprint** tab and select the Service resource you want to connect to the Postgres resource.
3. Select **Configure** from the drop-down.
4. Select **Environment Variables** from the left pane and click **Add Environment Variables. **
5. In the pop-up that appears, select **Resource Reference.**
6. Now, select the corresponding Postgres database, enter the Key and select the required Value.
7. Click **Save.**

You have successfully linked a Service resource with a Postgres database.

## Linking a Service resource to an Ingress resource

In this example, we will be linking a Service resource to an Ingress resource using Ingress Rules.

1. First, ensure you have both a Service and an Ingress resource created within your Blueprint.
2. Navigate to the **Blueprint** tab and select the **Ingress** resource you want to connect to the Service resource.
3. Select **Configure** from the drop-down.
4. In the Form mode, under **Ingress Rules,** click **Add New Entry.**
5. Mention the **Service Name, Path, **and** Port. **
6. Click **Save Changes.**

You have successfully linked a Service resource with an Ingress resource.