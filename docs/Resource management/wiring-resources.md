---
title: Wiring Resources in Facets
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
Facets dynamic referencing assists users in wiring resources using dollar notation with autocomplete suggestions, ensuring quick and accurate integration. Dollar referencing is the method of accessing the value of a variable in a different resource.

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/f8cc89a-Dol-ref.gif",
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


## How to Wire Resources using Dollar referencing?

1. Navigate to **Environment > Resource Center** and select the resource that has to be wired with another resource.
2. Go to the **Spec Overrides** tab and click **Edit.**
3. While editing the resource JSON in the editor, use dollar referencing to wire the resources. Dollar referencing allows the integration of dynamic values into your configurations. 

   1. **Using Autocomplete:**  
      As you edit, the autocomplete feature provides relevant suggestions, enabling efficient wiring of resources without manual input.

      [block:image]{"images":[{"image":["https://files.readme.io/d972326-auto.gif",null,"Click on the image to expand"],"align":"center","sizing":"450px","border":true,"caption":"Click on the image to expand"}]}[/block]
   2. **Locating Dollar References:**  
      Additionally, you can find the dollar reference for a resource in the **Resource Details > Overview**, under the **Interfaces and Attributes** widget.  
      **Note:** The dollar references provided in the **Resource Overview** are accessible only after the environment is launched. 
4. Now, **Save the Changes.**

You have successfully wired a resource with another resource using dollar-referencing.

## Guidelines for Dollar Referencing

1. **Ensuring Correct Syntax**  
   Maintain the correct syntax for dollar referencing. Double-check your usage to avoid errors and ensure that the references point to the intended values.  
   **Syntax:** `${\<resource_type>.\<resource_name>.out.\<respective_attributes>}`  
   **Example:** `${postgres.default-db.out.interfaces.writer.host}`
2. **Select Options from Autocomplete**  
   When using dollar references in the JSON editor, the autocomplete feature is your ally. It suggests options based on available dollar references, reducing the need for manual lookups.

### Example: Wiring a Postgres Database to a Service

Let's walk through the process of wiring a Postgres database to a Service. Follow these steps:

1. **Create a Service and a Postgres Resource**  
   First, ensure you have both a Service and a Postgres resource created within your Blueprint.
2. **Edit the JSON Configuration**
   1. Navigate to **Environment > Resource Center** and select the Service resource you want to wire with the Postgres database.
   2. Access the **Spec Overrides** tab and click **Edit.**
   3. In the **Environment** column, under **spec > env**, provide the Postgres URL, username, and password in your configuration.

```
"POSTGRES_URL": "jdbc:postgresql://${postgres.default-db.out.interfaces.writer.host}/postgres",  
"POSTGRES_USER": "${postgres.default-db.out.interfaces.writer.username}",  
"POSTGRES_PASS": "${postgres.default-db.out.interfaces.writer.password}"
```

In this example,  
**`"default-db"`:** Name of the Postgres resource.  
**`"POSTGRES_URL"`:** URL for the Postgres database.  
**`"POSTGRES_USER"`:** Username of the Postgres database.  
**`"POSTGRES_PASS"`:** Password of the Postgres database.

**Note: **The variables `POSTGRES_URL`, `POSTGRES_USER`, and `POSTGRES_PASS` are placeholders in the configuration. While these can be named differently, it is crucial to ensure that the values are correctly mapped to the respective variables.

## FAQ

### 1. What happens if I use an incorrect dollar reference?

Incorrect dollar references may lead to misconfigurations. To avoid this, it is recommended to utilize the autocomplete feature in the JSON editor or refer to the dollar references provided in the Resource Overview.

### 2. Where can I find information about incorrect dollar references in my configurations?

To identify and address incorrect dollar references, check the [Validations](https://readme.facets.cloud/docs/validation-summary-panel) page in the Releases tab. This page provides insights into any configuration issues, including incorrect dollar references.

### 3. Can I use custom dollar references for wiring resources, or are they predefined?

Dollar references are predefined based on the Blueprint's structure. 

### 4. Is the autocomplete feature in the JSON editor essential for dollar referencing?

While the autocomplete feature streamlines the editing process, you can manually input dollar references. However, using autocomplete enhances the accuracy.