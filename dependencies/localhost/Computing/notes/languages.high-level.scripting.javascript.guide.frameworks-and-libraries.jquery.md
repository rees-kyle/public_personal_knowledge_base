---
id: t09jel6do9jm2cme5fsg9q5
title: 4 - JQuery
desc: ''
updated: 1715329186552
created: 1715324967513
---

jQuery is a `fast`, `small`, **and** `feature-rich` **JavaScript** `library` `designed to` `simplify` **the** `way you` `interact with` `HTML documents`. It **provides an easy-to-use** `API` **that** `works across` **a** `multitude of` `browsers`. With a **combination of** `versatility` **and** `extensibility`, jQuery has changed the way that millions of people write JavaScript.

> API: Application Programming Interface

<!-- start of 'application programming interface' section -->
<details>
  <summary>Definition: application programming interface</summary>

#
**An** `API` (Application Programming Interface) **is a** `set of` `rules and tools` `that allows` `different software applications to` `communicate with each other`.

---
</details>
<!-- end of 'application programming interface' section -->



<!-- start of 'multitude' section -->
<details>
  <summary>Definition: multitude</summary>

#
The term "multitude" **refers to a** `large` `number of` `people or things` `gathered together or` `considered as` **a** `group`.

---
</details>
<!-- end of 'multitude' section -->



<!-- start of 'extensibility' section -->
<details>
  <summary>Definition: extensibility</summary>

#
Extensibility **refers to** the `ability of` **a** `system or software` `to be` `expanded or enhanced` `by adding` `new features or functionality` `without` `significant changes to` **its** **existing** `structure`.

---
</details>
<!-- end of 'extensibility' section -->



## Key Features

1. **DOM Manipulation**: jQuery makes it `easy to` `select` `DOM elements`, `traverse` them `and modify` **their** `content` **using its** `cross-browser` `open-source` `selector engine` **called** `Sizzle`.



<!-- start of 'cross-browser' section -->
<details>
  <summary>Definition: cross-browser</summary>

#
"Cross-browser" **refers to the** `capability of` **a** `website`, `web application`, `or software component` `to function` `effectively and consistently` `across different` `web browsers`.

---
</details>
<!-- end of 'cross-browser' section -->



<!-- start of 'open-source' section -->
<details>
  <summary>Definition: open-source</summary>

#
Open-source **refers to** `software` **whose** `source code is` `made` `freely available for` `anyone to` `view`, `modify`, **and** `distribute`.

---
</details>
<!-- end of 'open-source' section -->



<!-- start of 'selector engine' section -->
<details>
  <summary>Definition: selector engine</summary>

#
A selector engine **is a** `component or library in` `web development` `that interprets and processes` `CSS selectors` `to find and manipulate` `HTML elements` **within a webpage**.

---
</details>
<!-- end of 'selector engine' section -->



2. **Event Handling**: An elegant, simplified syntax for `attaching` `event handlers` **to your document**. This can significantly `reduce` **the** `complexity of` **your** `code`.

3. **Animations and Effects**: jQuery comes with built-in animation effects, which you can use to `create` `engaging interfaces`. You can `show`, `hide`, `slide`, `fade`, `and animate` `CSS properties` `easily`.

4. **AJAX**: jQuery provides a powerful yet simple `API for` `AJAX` **that allows you to** `load data` `asynchronously from` **a** `server` `without interfering with` **the** `display and behavior of` **the** `existing page`.

5. **Utilities**: Various `utility functions` **such as** `browser version detection` **and** `each function`, which are helpful in numerous applications.



<!-- start of 'utilities' section -->
<details>
  <summary>Definition: utilities</summary>

#
Utilities **are** `basic services or functions` `that support` `everyday activities`, **such as** `water`, `electricity`, `gas`, `or software tools` `designed to` `perform common tasks` `and assist with` `system management`.

---
</details>
<!-- end of 'utilities' section -->



6. **Plugins**: A broad range of plugins available `for extended functionality`. **If there’s something you need beyond what jQuery provides**, **there’s probably a plugin out there for it**.

### Pros

- **Cross-Browser Compatibility**: jQuery `handles` `many of` **the** `headaches` `caused by` `different browsers` `interpreting JavaScript` `differently`.
- **Simplifies JavaScript Programming**: `Reduces` **the** `need to` `write` `complex loops and` `DOM scripting library calls`.
- **Extensive Documentation and Community**: There's a `vast amount of` `resources`, `tutorials`, **and** `third-party plugins` **available**.



<!-- start of 'vast' section -->
<details>
  <summary>Definition: vast</summary>

#
"Vast" **refers to** `something` `very large in` `size`, `extent`, `or amount`.

---
</details>
<!-- end of 'vast' section -->



- **Method Chaining**: jQuery supports method chaining, **allowing you** `to run` `multiple commands`, **one after the other**, `on` **the** `same` `set of elements`.



<!-- start of 'method chaining' section -->
<details>
  <summary>Definition: method chaining</summary>

#
Method chaining **is a** `programming technique` **where** `multiple methods` **are** `called in` **a** `single line of` `code`, **with** `each method` `operating on` **the** `result of` `the preceding one`, **allowing for** `cleaner and` `more concise` `code`.

---
</details>
<!-- end of 'method chaining' section -->



<!-- start of 'preceding' section -->
<details>
  <summary>Definition: preceding</summary>

#
"Preceding" **refers to** `something that` `comes before` `or occurs earlier than` `something else`.

---
</details>
<!-- end of 'preceding' section -->



### Cons

- **Performance**: **Direct** `DOM manipulation` `without jQuery` `might be` `faster in` `modern browsers`.
- **Size**: Although not extremely large, the `file size` **is something to consider**, **especially for very performance-sensitive applications**.
- **Dependency**: Your `project becomes` `dependent on` `another library`, **which** `might be` `unnecessary with` modern JavaScript (`ES6+`), **which has incorporated many features that jQuery was used for**.

## Getting Started

To get started, you can `include` `jQuery` **in your web project** `by adding` **the** `following tag in` **your HTML file's** `<head>` **tag**:

```html
<!-- Link to the jQuery library -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
```

Here’s a **basic example** of using jQuery:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>jQuery Example</title>
    <!-- Include the jQuery library from CDN -->
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script>
        // Wait for the document to be fully loaded
        $(document).ready(function(){
            // Attach a click event handler to all button elements
            $("button").click(function(){
                // Toggle visibility of all <p> elements with a sliding animation
                $("p").slideToggle();
            });
        });
    </script>
</head>
<body>
    <!-- Button to trigger the slide toggle effect on paragraphs -->
    <button>Toggle Paragraph</button>
    <!-- Paragraph that will be shown/hidden when the button is clicked -->
    <p>This is a paragraph with some text.</p>
</body>
</html>

```

In this example, **when the button is clicked**, **the paragraph’s visibility toggles due to the 'slideToggle' effect**.

## Conclusion

While `jQuery` was `indispensable in` **the early** `2010`s, the `modern JavaScript` landscape `includes` `many features` `that reduce` **the** `need for` `jQuery`. `However`, `it remains` **a** `useful tool`, **especially** `in maintaining` `older projects` `or when` `quick` `development cycles` `are required`. `For new projects`, **it's** `worth considering` `whether` native JavaScript (`Vanilla JS`) `can meet` **your** `needs`, **as it** `avoids` `unnecessary dependencies and` `keeps projects` `lighter and` **potentially** `more maintainable`.