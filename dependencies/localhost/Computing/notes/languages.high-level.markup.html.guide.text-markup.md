---
id: 94wy4wugt5e34uqhwtml36v
title: 4 - Text Markup
desc: ''
updated: 1702489114613
created: 1702486604328
---

In HTML (Hypertext Markup Language), you use markup tags to structure and format the content of your web page. Here are some commonly used text markup tags in HTML:

## Headings

HTML has `six heading tags` (`<h1>` to `<h6>`), with `<h1>` being the `largest` and `<h6>` the `smallest`.

```html
<h1>This is a Heading 1</h1>
<h2>This is a Heading 2</h2>
<!-- ... -->
<h6>This is a Heading 6</h6>
```


## Paragraphs

To define paragraphs, use the `<p>` tag.

```html
<p>This is a paragraph.</p>
```


## Bold and Italics

Use the `<strong>` tag for `bold` and `<em>` tag for `italic` text.

```html
<strong>This text is bold.</strong>
<em>This text is italic.</em>
```


## Strikethrough

The `<s>` tag is used to represent text that is no longer accurate or relevant. It renders the enclosed text with a `strikethrough line`.

```html
<p>This is <s>no longer relevant</s> outdated information.</p>
```


## Line Breaks

Use the `<br>` tag for `line breaks`.

```html
This is a line.<br>This is a new line.
```


## Horizontal Line

Use the `<hr>` tag to create a `horizontal line`.

```html
<p>Some text above the line.</p>
<hr>
<p>Some text below the line.</p>
```


## Links

Create `hyperlinks` using the `<a>` tag.

```html
<a href="https://www.example.com">Visit Example.com</a>
```


## Lists

You can create `ordered` (`<ol>`) and `unordered` (`<ul>`) lists.
```html
<!-- ordered list -->
<ol>
    <li>First item</li>
    <li>Second item</li>
</ol>

<!-- unordered list -->
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
</ul>
```


## Code Snippets

The `<code>` tag is used to define a piece of code within a text. It is commonly used for displaying `code snippets`, programming code, or any text that should be treated as code.

```html
<code>
    &lt;title&gt;My Web Page&lt;/title&gt;
</code>
```

In HTML, certain characters have special meanings, and `using` the `literal character might interfere with` the HTML `structure`.

- `&lt;`: Less-than sign (`<`)
- `&gt;`: Greater-than sign (`>`)


#
These are just some basic examples. `HTML provides many other tags` and `attributes for additional text formatting and structuring content on a webpage`. Additionally, it's `common to use CSS` (Cascading Style Sheets) `for more advanced` and `consistent styling` across a website.