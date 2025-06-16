---
title: Templates for Blueprint
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
Templates in Facets are reusable groups of pre-configured resources that can be added to a blueprint with a single action. Rather than manually adding and configuring each resource individually, users can streamline their workflow by incorporating templates that encapsulate a logical set of components.

Templates enable consistency, reduce human error, and accelerate blueprint creation—especially when commonly used patterns or modules are involved (e.g., service + database + monitoring stack).

## Types of Templates

Facets supports two types of templates:

**Facets-Provided Templates**: These are built-in templates offered by Facets for common infrastructure setups. They represent best practices and standard configurations, ready to be reused.

**Custom Templates**: These are user-defined templates that can be created from existing blueprints and reused across different projects. They help teams standardize infrastructure patterns across environments and organizations.

### How to Use an Existing Template

- Templates can be found in the right pane under **Templates Tab**. Facets provided templates are listed under "Capabilities" and Custom templates are listed under "Custom" category.
- To add a template, user needs to select the template to be added and provide a prefix. This prefix will be automatically appended to all the resource names inside the template to avoid naming conflicts

_**Note: **Users can add the same template multiple times to a blueprint by using different prefixes each time._

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fhanchz7mronz&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fhanchz7mronz&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_e9700a5a-81c4-4e52-a57a-df5075d0ba18%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"449\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/hanchz7mronz",
  "title": "Designer | May 30 11:17 AM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_e9700a5a-81c4-4e52-a57a-df5075d0ba18/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/hanchz7mronz",
  "typeOfEmbed": "jsfiddle"
}
[/block]


### How to Create a Template

- Facets allows users to save the current blueprint as a template with a** "Save as Template"** option.
- Enter name of the template, description and the account in which the template should be saved (the github repo of that blueprint will be created in the selected account).

[block:embed]
{
  "html": "<iframe class=\"embedly-embed\" src=\"//cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fewrvoor6cdqn&display_name=Storylane&url=https%3A%2F%2Fapp.storylane.io%2Fdemo%2Fewrvoor6cdqn&image=https%3A%2F%2Fapp-pages.storylane.io%2Fcompany%2Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%2Fproject%2Fproject_ff8ffe25-cbee-4320-a836-df180fdc5e5b%2Fpreview.gif&type=text%2Fhtml&schema=storylane\" width=\"750\" height=\"449\" scrolling=\"no\" title=\"Storylane embed\" frameborder=\"0\" allow=\"autoplay; fullscreen; encrypted-media; picture-in-picture;\" allowfullscreen=\"true\"></iframe>",
  "url": "https://app.storylane.io/demo/ewrvoor6cdqn",
  "title": "Designer | May 30 11:36 AM",
  "favicon": "https://app.storylane.io/favicon.ico",
  "image": "https://app-pages.storylane.io/company/company_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3/project/project_ff8ffe25-cbee-4320-a836-df180fdc5e5b/preview.gif",
  "provider": "app.storylane.io",
  "href": "https://app.storylane.io/demo/ewrvoor6cdqn",
  "typeOfEmbed": "jsfiddle"
}
[/block]


<br />

## Advantages of Using Templates

- **Time-Saving: **Add multiple related resources in one go instead of configuring them individually.
- **Standardization:** Maintain consistency in resource configurations across environments and teams.
- **Reusability**: Reduce duplication of effort by reusing pre-tested infrastructure setups.
- **Version Control:** Templates are managed in Git, enabling collaborative updates and rollback if needed.
- **Error Reduction:** Minimize manual configuration errors by using predefined and tested resource combinations.