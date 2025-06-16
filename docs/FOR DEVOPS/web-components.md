---
title: Web Components
excerpt: Use to embed custom dashboards, workflows and integrations.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Web Components come into the picture when you're looking to extend **Facets** with tools tailored to your team's specific needs.

Instead of switching between different tools and dashboards, you can now **embed your own web apps directly into Facets.cloud**, creating a more unified experience for you and your team — all in one place.

#### The best part?

- Your Web Components render inside their **own shadow DOM**, so they won’t mess with Facets’ styles or behavior.
- They **inherit the active session token**, so you can make secure, authenticated API calls just like any native part of the platform.
- Create context-aware components that inherit user roles and resource data and reduce context-switching.
- And since all **Facets APIs are available via Swagger**, it’s super easy to hook into environment provisioning, workflow triggers, or anything else you need — making your custom tools feel like a natural part of the platform.

With Web Components, you get flexibility without fragmentation. Everything stays connected, consistent, and developer-friendly.

## Prerequisites

Permission to register Web Component and familiarity with Web Components development.  
Example of how to write a web-component : [sample-web-component](sample-web-component)

## Creating Your First Web Component

1. Navigate to Organizational Settings from left sidebar.
2. Locate and click on the Web Component option.
3. This will take you to the Web Component Listing page, where you can:
   - View all existing Web Components.
   - See component types, remoteURLs, and respective creators.
   - Track which components are enabled or disabled.
   - Delete components that are no longer needed.

### Adding a Microfrontend Web Component

Navigate to the Microfrontends Dashboard, locate and click on the Add Component button.  
This will open a dialog where you can:

- **Name**: Enter the web-component name  (e.g., If component is  <custom-dashboard> then the name will be custom-dashboard)
- **Type**: The Option to choose between the position of local and global will come soon
- **Remote URL**: Provide the hosted url of your component script.
- **Icon URL**: Enter the URL for the icon to be displayed in the Facets UI for that component.
- **Enabled**: Toggle on to make the component immediately available after creation.
- **Tooltip Text**: For a brief description that appears when users hover over the component icon.

After filling in all required fields (marked with \*), click the Add button to register your component.

Now Your new component will appear in the Sidebar below the Organization Setting button immediately after registration, ready to be accessed by your team members.

### To Disable components:

1. Navigate to the Web Components Dashboard.
2. Locate the component you wish to disable.
3. Click edit  and toggle the Enabled field to disable and Save,

### To Delete components:

1. Navigate to the Web Components Dashboard.
2. Locate the component you wish to delete.
3. Click the Delete button and Confirm deletion when prompted.

## See it in Action:

[block:image]
{
  "images": [
    {
      "image": [
        "https://files.readme.io/350d35214000ae4487ae2255b5910dcb4982ccb7648d9fea0936af3d7dab0b63-image.png",
        null,
        ""
      ],
      "align": "center",
      "sizing": "600px",
      "border": true
    }
  ]
}
[/block]


## Component Development Guidelines

Your Web Component must:

1. Be properly registered as a custom element.
2. Handle contextual data passed as attributes.
3. Be self-contained to avoid conflicts with other components.

Facets by default passes contextual data to your components:

For Sidebar Apps you will have user-related data in the "user" attributes, which you can parse at your web-component end. 

Additional contextual attributes for nav-bar web component types will be available in future releases.