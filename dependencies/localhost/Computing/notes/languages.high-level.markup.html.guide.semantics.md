---
id: sqz02m7jiz0ffniez74mhvx
title: 009 - Semantics
desc: ''
updated: 1704991738937
created: 1704717512020
---

Semantics **refers to the** `meaning` `or` `purpose` **of** the `elements` **used to** `structure content` on a web page. Semantic HTML elements are those that carry meaning about the structure and content of a webpage, **making it** `more` `accessible` **for** both `machines` (like `search engines` and `screen readers`) **and** `humans` reading.

## Examples

### `<header>`
Represents the header of a section or a page.

```html
<header>
    <h1>Page Title</h1>
    <p>Subtitle or tagline</p>
</header>
```

### `<nav>`
Represents a `navigation menu`.

```html
<nav>
    <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>
```

### `<main>`
Represents the `main content` of the document.

```html
<main>
    <section>
        <h2>About Us</h2>
        <p>This is a section about us.</p>
    </section>

    <article>
        <h2>Article Title</h2>
        <p>This is a standalone article with meaningful content.</p>
    </article>
</main>
```

### `<article>`
Represents an `independent`, `self-contained` piece of **content**.

```html
<article>
    <h2>Article Title</h2>
    <p>This is a standalone article with meaningful content.</p>
</article>
```

### `<section>`
Represents a `generic` section of content.

```html
<section>
    <h2>Section Title</h2>
    <p>Content of the section.</p>
</section>
```

### `<aside>`
Represents content that is `tangentially related` to the content around it.

```html
<aside>
    <h2>Related Links</h2>
    <ul>
        <li><a href="#link1">Link 1</a></li>
        <li><a href="#link2">Link 2</a></li>
    </ul>
</aside>
```



<!-- start of 'tangentially' section -->
<details>
    <summary>Definition: tangentially</summary>

#
"Tangentially" means `related`, **but** `not` directly or closely `connected`. It describes something that is somewhat connected but `not` **the** `main focus`.

---
</details>
<!-- end of 'tangentially' section -->



### `<footer>`
Represents the footer of a section or a page.

```html
<footer>
    <p>&copy; 2024 My Website. All rights reserved.</p>
</footer>
```

By **using** `semantic elements` appropriately, **provides** `additional information` **to** `browsers` **and** `other tools` about the structure of your content, which can improve accessibility and search engine optimization. For example, a `screen reader` **can** `better interpret` **the** structure of a `page` **and** `convey` **it to** `visually impaired` **users**.