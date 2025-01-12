---
id: k3xx5ykkmipnzcrqzlq6002
title: 015 - Additional Concepts
desc: ''
updated: 1736665697858
created: 1705251063807
---

Here are some **additional** `concepts` **and** `techniques` you can consider in HTML.


## Data Attributes

Use data attributes **to** `store` `custom data` `private` **to the page or application**. This data **can be** easily `accessed` **and** `manipulated` **using** `JavaScript`.

```html
<!-- Div element with a custom data attribute -->
<div data-custom="your-data-value">Content</div>
```

- `<div>`: This is an HTML block-level `element` **used to** `define` **a** `division` **or** `section` in a document.

- `data-custom="your-data-value"`: This is a `custom data` **attribute** named `"custom."` Custom data attributes are **used to** `store` private `data private` **to the** `page` **or** `app`lication, and their `names` should `begin` **with** "`data-`" followed by a descriptive name. In this case, `"your-data-value"` **is a** `placeholder`, and you can replace it with the actual data value you want to associate with the element.

- `Content`: This is the content `inside` the `<div>` **element**, which could be text, other HTML elements, or a combination of both.

### Access it with JavaScript

```javascript
// Selecting the first 'div' element in the document
var customData = document.querySelector('div');

// Accessing the value of the 'data-custom' attribute using the dataset property
// The 'dataset' property provides access to all custom data attributes (data-* attributes)
// In this case, it retrieves the value of the 'data-custom' attribute
var customDataValue = customData.dataset.custom;
```

- `var customData`: This **declares a** `variable` **named** `customData`.

- `document.querySelector('div')`: This method `searches for` the `first occurrence` **of a** `<div>` **element in** the `document`. It `returns` **the** `reference` to the element `if found`.

- `.dataset.custom`: The `dataset` **property** is **used to** `access` the `custom data` **attributes of an** `element`. In this case, **it** `retrieves` the `value` **associated with** the `'data-custom'` **attribute of the selected** `<div>` **element and** `assigns` **it to** the `variable` `customDataValue`.


## HTML Metadata

Utilize `meta tags` **in** the `<head>` **section** to **provide** `metadata` **about** the `document`, **such as** `character set`, `viewport settings`, **and** `descriptions`.

```html
<meta charset="UTF-8">
<meta name="description" content="Your page description">
<meta name="keywords" content="HTML, CSS, JavaScript">
```


## HTML Entities

Use HTML entities **for** `characters` **that have** `special meaning` **in** `HTML`, **like** `<` (`&lt;`), `>` (`&gt;`), **and** `&` (`&amp;`). This **helps** `avoid conflicts` **with** HTML `syntax`.

```html
<p>This is an &lt;example&gt; paragraph.</p>
```


## ~~HTML Imports~~

Note that `HTML Imports`, once a feature in web components, **have been** `deprecated`. It's `recommended` **to** `use` `other` `module systems` **like** `ES6` imports **for** `JavaScript` **and** `CSS` **for** `styling`.



<!-- start of 'deprecated' section -->
<details>
   <summary>Definition: deprecated</summary>

#
"Deprecated" **means** `something` **in software is** `outdated` **and** `not recommended` **for use anymore**. Developers are `advised` **to** `use` `newer` **and** `better` `alternatives` `because` **the deprecated** `feature` `may be` `removed` **or** `unsupported` **in the** `future`. 

---
</details>
<!-- end of 'deprecated' section -->



## Custom Elements

Explore the concept of custom elements in HTML, which allows you **to** `define` your own `custom` **HTML** `elements` **with** associated `JavaScript` behavior. This is **part of** the `Web Components standard`.

```html
<my-custom-element></my-custom-element>
```

### Define it with JavaScript

```javascript
// Define a class named MyCustomElement that extends the HTMLElement class
class MyCustomElement extends HTMLElement {
   
   // connectedCallback() is a lifecycle callback called when the element is inserted into the DOM
   connectedCallback() {
      
      // Set the inner HTML content of the custom element to 'Hello, Custom Element!'
      this.innerHTML = 'Hello, Custom Element!';
   }
}

// Register the custom element with the browser, associating it with the tag name 'my-custom-element'
customElements.define('my-custom-element', MyCustomElement);
```

#
**These** `concepts` will broaden your   understanding of HTML and `help` **you** `create` **more** `dynamic` **and** `feature-rich` `web pages`. **Always** `refer to` the `latest specifications` **and** `best practices` **as** `web technologies` `continue` **to** `evolve`.