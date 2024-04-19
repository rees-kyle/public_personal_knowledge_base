---
id: n1tsjn4uymuwmwmpgs9k6wl
title: 4 - Creating and Removing Elements
desc: ''
updated: 1713564656104
created: 1713562513121
---

In JavaScript, you can manipulate the Document Object Model (DOM) to dynamically create and remove elements from a web page. Using JavaScript to create elements **can** `reduce` the amount of `HTML` **you** `manually write` `in` **your** `files`. Here's how you can do it:

## Creating Elements:

To create an element, you **can use the** `document.createElement()` **method**. You `specify` **the** `type of` `element` **you want to create as an** `argument`. `Then`, **you can** `manipulate` **its** `properties` `and` `attributes` **as needed** `before` `appending` **it** `to` **the** `DOM`.

```javascript
// Create a new <div> element
var newDiv = document.createElement("div");

// Set its attributes or properties
newDiv.className = "my-div";
newDiv.id = "unique-id";
newDiv.textContent = "Hello, World!";

// Append the element to the document body or any other element
document.body.appendChild(newDiv);
```

## Removing Elements:

To remove an element from the DOM, you **need to** `select` **the** `element` `first` **and** `then` `call` **the** `remove()` **method** on it.

```javascript
// Select the element to remove
var elementToRemove = document.getElementById("unique-id");

// Remove the element
elementToRemove.remove();
```

You **can also** `remove` **an** `element` `by targeting` **its** `parent` **and** `calling` `removeChild()` **with the element you want to remove**.

```javascript
// Select the parent element
var parentElement = document.getElementById("parent-element-id");

// Select the element to remove
var elementToRemove = document.getElementById("unique-id");

// Remove the element
parentElement.removeChild(elementToRemove);
```

## Example:

Here's a **more comprehensive** example of creating and removing elements:



<!-- start of 'comprehensive' section -->
<details>
    <summary>Definition: comprehensive</summary>

#
"Comprehensive" **means** `thorough` **and** `complete`, `covering` `everything important` `about` **a** `topic` `in detail`.

---
</details>
<!-- end of 'comprehensive' section -->



<!-- start of 'thorough' section -->
<details>
    <summary>Definition: thorough</summary>

#
"Thorough" **means** `doing` `something` `very carefully` **and** `making sure` `not to` `miss anything` `important`.

---
</details>
<!-- end of 'thorough' section -->



```javascript
// Create a new <div> element
var newDiv = document.createElement("div");
newDiv.className = "my-div";
newDiv.id = "unique-id";
newDiv.textContent = "Hello, World!";

// Append the element to the document body or any other element
document.body.appendChild(newDiv);

// Wait for a while (just for demonstration)
setTimeout(function() {
    // Remove the element after 3 seconds
    newDiv.remove();
}, 3000); // 3000 milliseconds = 3 seconds
```

This example **creates a new 'div' element**, **appends it to the document body**, and **then removes it after 3 seconds**.