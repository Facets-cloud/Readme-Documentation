---
title: Linking Resources
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
## How to link Resources?

Linking resources refers to establishing connections between different resources, enabling them to interact and share information with each other.

## Linking a Postgres resource to a Service resource

In this example, we will be linking a Postgres resource to a Service resource using Environment Variables.

1. First, ensure you have both a Service and a Postgres resource created within your Blueprint.
2. Navigate to the **Blueprint** tab and select the **Service** resource you want to connect to the **Postgres resource**.

   [block:image]{"images":[{"image":["https://files.readme.io/15310b98bfd72bc5e3db5ae533779af37a8457b055b83792745d1c332f37b1a9-image.png",null,null],"align":"center","border":true}]}[/block]
3. Select **Configure** in the drop-down.

   [block:image]{"images":[{"image":["https://files.readme.io/cc797c752d69670043801af712a49e546fabc29c1e9280f95c407101b53d9242-image.png",null,null],"align":"left","sizing":"300px","border":true}]}[/block]
4. Select **Environment Variables** from the left pane and click **Add Environment Variables. **

   [block:image]{"images":[{"image":["https://files.readme.io/f0496e73d03473d0e0f5bdea8554f2aa560d1b53f66f5de25254558c30fbcfe3-image.png",null,null],"align":"center","border":true}]}[/block]
5. In the pop-up that appears, select **Resource Reference.**

   [block:image]{"images":[{"image":["https://files.readme.io/69967ab82cf81c2b8ae955b65c00a1689e792774b447313f22c71e63a1748d05-image.png",null,null],"align":"left","sizing":"400px","border":true}]}[/block]
6. Now, select the corresponding Postgres database, enter the Key and select the required Value.

   [block:image]{"images":[{"image":["https://files.readme.io/83f189847980085e6db0228086b1f7436b497a0a4ee52857bff451027bacc0b2-image.png",null,null],"align":"center","border":true}]}[/block]
7. Click **Save.**

You have successfully linked a Service resource with a Postgres database.

## Linking a Service resource to an Ingress resource

In this example, we will be linking a Service resource to an Ingress resource using Ingress Rules.

1. First, ensure you have both a Service and an Ingress resource created within your Blueprint.
2. Navigate to the **Blueprint** tab and select the **Ingress** resource you want to connect to the Service resource.
3. Select **Configure** from the drop-down.
4. In the Form mode, under **Ingress Rules,** click **Add New Entry.**
5. Mention the **Service Name, Path, **and** Port. **

   [block:image]{"images":[{"image":["https://files.readme.io/286a28b2766e1eea7af74757eefd7b14e2df5bc53d749658539cf6ccf5742da3-image.png",null,null],"align":"center","border":true}]}[/block]
6. Click **Save Changes.**

   ![](https://files.readme.io/47b401d3b21fc2ac7a012e64cc065110f88a6b50896eaedb7d628ddaf40df89c-image.png)

You have successfully linked a Service resource with an Ingress resource.