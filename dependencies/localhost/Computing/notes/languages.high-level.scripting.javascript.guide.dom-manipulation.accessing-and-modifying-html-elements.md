---
id: iod6uextjy12p68m8p9qjdq
title: 1 - Accessing and Modifying HTML Elements
desc: ''
updated: 1713295713084
created: 1713202734252
---

Here's a basic overview of how you can access and modify HTML elements using JavaScript:

### Accessing HTML Elements:

**You can access HTML elements using** `various methods` `provided by` **the** `DOM API`. Here are a few common ones:



<!-- start of 'various' section -->
<details>
    <summary>Definition: various</summary>

#
"Various" simply **means** `different` **or** `multiple`.

---
</details>
<!-- end of 'various' section -->



1. **getElementById**: This method allows you to `access` **an** `element` `by` **its unique** `ID`.
```javascript
// Use document.getElementById() to retrieve the HTML element with the specified ID attribute
// "elementId" is a placeholder for the ID of the element you want to retrieve
var element = document.getElementById("elementId");

// Now, the variable "element" contains the HTML element with the specified ID
// You can manipulate this element, access its properties, or modify its content as needed
```


2. **getElementsByClassName**: This method allows you to access elements by their class names. It returns a collection of elements.
```javascript
var elements = document.getElementsByClassName("className");
// Now, the variable "elements" contains a collection of HTML elements that have the specified class name
// You can iterate over this collection to access and manipulate each element individually
```



<!-- start of 'iterate over' section -->
<details>
    <summary>Definition: iterate over</summary>

#
"Iterate over" just **means** `going through` `each item` `in` **a** `collection`, like going through each page in a book one by one. **In programming**, **it means looping through a list or collection to do something with each item**, **such as reading or modifying it**.

---
</details>
<!-- end of 'iterate over' section -->



3. **getElementsByTagName**: This method allows you to access elements by their tag names. It also returns a collection.
```javascript
var elements = document.getElementsByTagName("tagName");
// Now, the variable "elements" contains a collection of HTML elements that have the specified tag name
// You can iterate over this collection to access and manipulate each element individually
```

4. **querySelector**: This method allows you to select elements using CSS selectors. It returns the first matching element.
```javascript
var element = document.querySelector("selector");
// Now, the variable "element" contains the first HTML element that matches the specified CSS selector
// You can manipulate this element, access its properties, or modify its content as needed
```

5. **querySelectorAll**: This method returns a NodeList of all elements matching a specified CSS selector.
```javascript
var elements = document.querySelectorAll("selector");
// Now, the variable "elements" contains a NodeList that includes all elements matching the specified CSS selector
// You can iterate over this NodeList to access and manipulate each selected element individually
```

### Modifying HTML Elements:

**Once you have accessed an HTML element**, **you can** `modify` **its** `properties`, `attributes`, **and** `content` **using JavaScript**.

1. **Changing Text Content**:
   ```javascript
   element.textContent = "New Text"; // by default use this
   // or
   element.innerText = "New Text";
   ```

2. **Changing HTML Content**:
   ```javascript
   element.innerHTML = "<p>New HTML Content</p>";
   ```

3. **Changing Attributes**:
   ```javascript
   // Set the value of the specified attribute on the HTML element referenced by the variable 'element'
   element.setAttribute("attributeName", "attributeValue");
   // 'attributeName' is a placeholder, it is the name of the attribute you want to set or modify
   // 'attributeValue' is a placeholder, it is the value you want to assign to the attribute
   ```

4. **Changing Styles**:
   ```javascript
   // '.property' represents the name of the CSS property being modified, examples are color, backgroundColor, fontSize
   element.style.property = "value";
   ```

5. **Adding/Removing Classes**:
   ```javascript
    // Adds a CSS class to the list of classes for a DOM element
    element.classList.add("className");

    // Removes a CSS class from the list of classes for a DOM element
    element.classList.remove("className");
    ```

6. **Creating New Elements**:
   ```javascript
   // Creates a new DOM element with the specified tag name
   var newElement = document.createElement("tagName");

   // 'tagName' should be replaced with the name of the HTML tag for the element you want to create, for example 'div', 'span' or 'p'
   ```

7. **Appending Elements**:
   ```javascript
   // Appends a child element to a parent element in the DOM hierarchy
   parentElement.appendChild(newElement);
   ```



<!-- start of 'append' section -->
<details>
    <summary>Definition: append</summary>

#
**To append means to** `add` `something to` **the** `end of` **a** `written` **or** `spoken` `document`, `list`, **or** `record`. In computer science, appending often refers to adding data or content to the end of an existing file, string, or data structure. For example, **in programming**, **you might append a new item to the end of an array or a list**.

---
</details>
<!-- end of 'append' section -->



### Example:

Let's say you have an **HTML element** like this:
```html
<!-- Defines a <div> element with the ID "myDiv" and containing the text "Hello World!" -->
<div id="myDiv">Hello World!</div>
```

You can **access and modify it using JavaScript** like this:
```javascript
// Retrieves the DOM element with the ID "myDiv" and assigns it to the variable 'element'
var element = document.getElementById("myDiv");

// Changes the text content of the element to "Goodbye World!"
element.textContent = "Goodbye World!";

// Sets the text color of the element to red
element.style.color = "red";
```

**This would change the text content of the div to "Goodbye World!" and set its text color to red**.