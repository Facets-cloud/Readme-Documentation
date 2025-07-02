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

**Custom Templates**: These are user-defined templates that can be created from existing blueprints and reused across different projects. They help teams standardize infrastructure patterns across environments and organisations.

### How to Use an Existing Template

* Templates can be found in the right pane under **Templates Tab**. Facets provided templates are listed under "Capabilities" and Custom templates are listed under "Custom" category.
* To add a template, user needs to select the template to be added and provide a prefix. This prefix will be automatically appended to all the resource names inside the template to avoid naming conflicts

***Note:** Users can add the same template multiple times to a blueprint by using different prefixes each time.*

<Embed url="https://app.storylane.io/demo/hanchz7mronz" href="https://app.storylane.io/demo/hanchz7mronz" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fhanchz7mronz%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fhanchz7mronz%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_e9700a5a-81c4-4e52-a57a-df5075d0ba18%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

### How to Create a Template

* Facets allows users to save the current blueprint as a template with a **"Save as Template"** option.
* Enter name of the template, description and the account in which the template should be saved (the github repo of that blueprint will be created in the selected account).

<Embed url="https://app.storylane.io/demo/ewrvoor6cdqn" href="https://app.storylane.io/demo/ewrvoor6cdqn" typeOfEmbed="jsfiddle" html="%3Ciframe%20class%3D%22embedly-embed%22%20src%3D%22%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Fsrc%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fewrvoor6cdqn%26display_name%3DStorylane%26url%3Dhttps%253A%252F%252Fapp.storylane.io%252Fdemo%252Fewrvoor6cdqn%26image%3Dhttps%253A%252F%252Fapp-pages.storylane.io%252Fcompany%252Fcompany_8c4ce947-95e7-4f47-ab9c-89edf23fd0e3%252Fproject%252Fproject_ff8ffe25-cbee-4320-a836-df180fdc5e5b%252Fpreview.gif%26type%3Dtext%252Fhtml%26schema%3Dstorylane%22%20width%3D%22750%22%20height%3D%22449%22%20scrolling%3D%22no%22%20title%3D%22Storylane%20embed%22%20frameborder%3D%220%22%20allow%3D%22autoplay%3B%20fullscreen%3B%20encrypted-media%3B%20picture-in-picture%3B%22%20allowfullscreen%3D%22true%22%3E%3C%2Fiframe%3E" />

<br />

## Advantages of Using Templates

* **Time-Saving:** Add multiple related resources in one go instead of configuring them individually.
* **Standardization:** Maintain consistency in resource configurations across environments and teams.
* **Reusability**: Reduce duplication of effort by reusing pre-tested infrastructure setups.
* **Version Control:** Templates are managed in Git, enabling collaborative updates and rollback if needed.
* **Error Reduction:** Minimize manual configuration errors by using predefined and tested resource combinations.