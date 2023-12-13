---
id: j2m8o7jqco8b2x6pgcfzpqc
title: 3 - Structure of Document
desc: ''
updated: 1702485785678
created: 1702320621409
---

An HTML `document follows` a `specific structure to define` the `content` and `layout of` a `web page`. 

## Basic Structure and Components

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Page Title</title>
    <!-- Additional head elements (stylesheets, scripts, etc.) go here -->
</head>
<body>
    <!-- Your page content goes here -->
    <header>
        <!-- Header content (e.g., logo, navigation) -->
    </header>
    
    <main>
        <!-- Main content of the page -->
    </main>
    
    <footer>
        <!-- Footer content (e.g., copyright information) -->
    </footer>

    <!-- Additional body elements (scripts, etc.) go here -->
</body>
</html>
```

## Structure Breakdown

- `<!DOCTYPE html>`: This declaration **defines** the **document type and version of HTML**. In **modern web development**, it's common to use **HTML5**, and the **declaration is** simply `<!DOCTYPE html>`.

- `<html lang="en">`: The **root element of** the HTML **document**. The `lang` **attribute specifies the language** of the document, typically using a **two-letter language code**.



<!-- start of 'metadata' section -->
<details>
    <summary>Definition: metadata</summary>

#
Refers to `data` **that provides** `information` **about** `other data`.

---
</details>
<!-- end of 'example' section -->



<!-- start of 'internationalization' section -->
<details>
    <summary>Definition: Internationalization</summary>

#
Internationalization (`i18n`) is the `process of designing` and `developing software` or `content` to be `easily adaptable` for `users from different languages` and `cultures`.

---
</details>
<!-- end of 'internationalization' section -->



- `<head>`: This **section contains meta-information** about the HTML document, such as **character set**, **viewport settings**, and the **page title**.

    - `<meta charset="UTF-8">`: **Specifies** the **character encoding** for the document (**UTF-8** is **widely used** for **internationalization**).

    - `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: **Configures** the **viewport** for **responsive design** on **various devices**.

    - `<title>Your Page Title</title>`: **Sets** the **title of** the **web page**, which **appears** in the **browser tab**.

- `<body>`: This **section contains** the actual **content** of the HTML document.

    - `<header>`: Typically includes elements like the **site logo**, **navigation menu**, or any **content** that appears **at the top of** the **page**.
    - `<main>`: Contains the main content of the page. This is where **most of** your **text**, **images**, and **other elements will be placed**.
    - `<footer>`: Includes elements like **copyright information**, links to **terms of service**, and other footer content.

This `structure provides` a `framework for creating well-organized` and `semantically meaningful HTML documents`. Remember that the specific `content and styling will vary depending on` the `purpose and design of` your `web page`.