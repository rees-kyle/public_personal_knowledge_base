---
id: 2b4b79i09qia1mvyxjbj7nh
title: 3 - CSS Styles
desc: ''
updated: 1713561953408
created: 1713560693352
---

Certainly! In JavaScript, you can manipulate the DOM (Document Object Model) to modify CSS styles of HTML elements dynamically. Here's how you can achieve this:

## 1. Adding/Removing Classes:
You can add or remove CSS classes `to` **an** `element` `to apply` `predefined styles`. **This is considered** `best practice`.

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Manipulation</title>
    <!-- Define CSS styles for the highlight class -->
    <style>
        .highlight {
            background-color: yellow; /* Background color for highlighting */
        }
    </style>
</head>
<body>
    <!-- Div element with id 'myElement' -->
    <div id="myElement">Hello, World!</div>
    <!-- Button triggering the toggleClass function -->
    <button onclick="toggleClass()">Toggle Class</button>

    <script>
        // JavaScript function to toggle class
        function toggleClass() {
            // Retrieve the element with id 'myElement'
            var element = document.getElementById("myElement");

            // Toggle the 'highlight' class on the element
            element.classList.toggle("highlight");
        }
    </script>
</body>
</html>
```

## 2. Changing Inline Styles:
You can directly modify the inline CSS styles **of an element using JavaScript** `by accessing` **the** `style property`.

```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Manipulation</title>
    <!-- CSS styles defined inline -->
    <style>
        #myElement {
            width: 200px;
            height: 100px;
            background-color: yellow; /* Initial background color */
        }
    </style>
</head>
<body>
    <!-- Div element with id 'myElement' -->
    <div id="myElement">Hello, World!</div>
    <!-- Button triggering the changeStyle function -->
    <button onclick="changeStyle()">Change Style</button>

    <script>
        // JavaScript function to change style
        function changeStyle() {
            // Retrieve the element with id 'myElement'
            var element = document.getElementById("myElement");

            // Modify the inline CSS styles
            element.style.backgroundColor = "blue"; // Change background color to blue
            element.style.color = "white"; // Change text color to white
            element.style.fontSize = "20px"; // Change font size to 20 pixels
        }
    </script>
</body>
</html>
```

These are **two common approaches** to dynamically modify CSS styles using JavaScript and DOM manipulation. 