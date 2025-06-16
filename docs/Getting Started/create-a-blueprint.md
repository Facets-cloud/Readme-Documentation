---
title: Create a Blueprint
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
We recommend going through the [Blueprint](https://readme.facets.cloud/docs/blueprint) concepts documentation to better understand the concept of Blueprint and associated functionality.

## How to Create a Blueprint?

1. Navigate to **Blueprints > List,** and click **New Blueprint.**
2. You have two options when creating a Blueprint: you can start from scratch by choosing **No Template**, or you can utilize an existing template.
3. Begin by assigning a unique **Name** to your Blueprint. 
4. Proceed to the **Repository Setup.** Choose if you want to **Create a new repository** or **Use an existing repository.**
   1. If you opt to **Use an existing repository,** you will need to provide the **Repository URL**(mandatory).  
      **Note:** A **stack.json** file is required in the repository when creating a Blueprint using an existing one.
5. Select your VCS **Account** from the available list. If you need to set up a new account, refer to the [Integrate Version Control Systems (VCS) with Facets](https://readme.facets.cloud/docs/integrating-vcs-accounts) documentation.
6. Decide if you want to **Mark this Blueprint as a Template.** By doing so, it can be later reused by everyone in the organization.
   1. If you choose to **Mark this Blueprint as a Template** enter the **Template Description.**
7. Specify the master **Branch Name** (for example, "main" for GitHub or "master" for Bitbucket) and **Relative Path.**
8. Select your **Primary Cloud** provider and begin with the default JSON for resources. If you need to set up a new account, refer to the [Integrating Cloud Accounts](https://readme.facets.cloud/docs/integrating-cloud-accounts) documentation for more details.
9. After completing the above steps, click the **Create** button to initiate the Blueprint creation process.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/6796a87-Create_a_blueprint.gif",
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


You have successfully created your first Blueprint!

## How to Create a Blueprint Template?

Marking the Blueprint as a Template ensures it will be accessible and can be used the next time a Blueprint is created. There are two methods to save a Blueprint as a template:

1. For a new Blueprint:

   1. Enable **Mark this Blueprint as a Template** and enter the **Template Description** in the Blueprint creation page.

   [block:image]{"images":[{"image":["https://files.readme.io/fe591c6-image.png",null,"Click on the image to expand"],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]
2. For an existing Blueprint:

   1. Navigate to **Blueprint > Lists** and select the Blueprint you wish to save as a Template.
   2. From the **Designer** tab, click the **ellipsis** icon in the top right corner and select **Save as Template.**
   3. In the pop-up, mention the **Template Name** and **Template Description.**
   4. Finally, click **Create** to save your Blueprint as a Template.

   [block:image]{"images":[{"image":["https://files.readme.io/93ae1e6-Create_a_blueprint_template.gif",null,null],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]

You have successfully created a Blueprint Template.

## FAQ

### 1. What is a Blueprint Template in the context of projects?

A Template is a pre-constructed Blueprint that contains predefined resources with a predefined structure. This can streamline and standardize the creation of new Blueprints and serves as an efficient starting point for creating new Blueprints.

### 2. Why should I create a Blueprint Template?

Creating a template saves time by allowing you to reuse configurations. It also promotes consistency across all your related Blueprints.

### 3. Can I use an existing Blueprint as a template for new projects?

Yes, by marking a Blueprint as a template, you can use it as a starting point while creating new Blueprints. Refer to [this section](https://readme.facets.cloud/v0.10/docs/discards#how-to-create-a-template) of the documentation.