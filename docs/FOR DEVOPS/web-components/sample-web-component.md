---
title: Sample Web Component
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
# How to Create and Use a Simple Web Component

To get a Web Component working, you only need **two files**:

1. `index.html` – acts as the entry point for your page  
2. `my-greeting.js` – contains the logic for your custom component

***

## 1. `index.html`

This is the main HTML entry point. It references the Web Component script and uses the custom tag.

```html
<!DOCTYPE html>
<html>
  <body>
    <my-greeting></my-greeting>

    {/* Load the component logic */}
    <script type="module" src="my-greeting.js"></script>
  </body>
</html>
```

## 2. `my-greeting.js`

This is where you write the main logic of your Web Component. The example below registers the `<my-greeting>` tag and renders it.

```js
class MyGreeting extends HTMLElement {
  constructor() {
    super();
    const shadow = this.attachShadow({ mode: 'open' });

    const box = document.createElement('div');
    box.textContent = 'CI Pipeline Dashboard Loaded';
    box.style.cssText = 'padding: 12px; border: 1px solid #ccc; font-family: sans-serif;';

    shadow.appendChild(box);
  }
}

customElements.define('my-greeting', MyGreeting);
```

Post this, you can upload them to any static hosting service of your choice (e.g. S3, GitHub Pages, Cloudflare Pages, etc) just make sure both files are publicly accessible over HTTPS.

## 3. How to Render inside Facets?

Once hosted, you can load the component by referencing the .js file directly.\
For example: [https://your-host.com/my-greeting.js](https://your-host.com/my-greeting.js) in the remote url section of web-components.