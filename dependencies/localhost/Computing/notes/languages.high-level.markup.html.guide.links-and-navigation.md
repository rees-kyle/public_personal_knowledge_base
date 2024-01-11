---
id: 5yp3z8d2a3tenkacn5wjkam
title: 005 - Links and Navigation
desc: ''
updated: 1704991707009
created: 1702573388016
---

In HTML (Hypertext Markup Language), links and navigation are essential `elements` for `creating interactive` and `interconnected web pages`. The primary HTML element for `creating links` is the `<a>` (`anchor`) `element`. Here's an overview of how to create links and navigation in HTML:

## Links

### Basic
The basic `syntax` for creating a link is as follows:

```html
<a href="URL">Link Text</a>
```

- `href`: Specifies the `destination URL` that the link points to.

- `Link Text`: The `text that appears as` a `clickable link`.

- `Example`:

```html
<a href="https://www.example.com">Visit Example.com</a>
```


### Local Pages
You can create links to `other pages within your website` using `relative URLs`:

```html
<a href="about.html">About Us</a>
```


### Sections
You can create internal links to `sections within the same page` using anchor tags and the `id` attribute:

```html
<a href="#section1">Go to Section 1</a>

<!-- ... -->

<section id="section1">
  <h2>Section 1</h2>
  <p>This is the content of Section 1.</p>
</section>
```


### Images
You can use the anchor element to create `links around images`:

```html
<a href="https://www.example.com">
  <img src="image.jpg" alt="Example Image">
</a>
```


### New Tab
To `open` a `link in a new tab`, you can use the `target` attribute:

```html
<a href="https://www.example.com" target="_blank">Visit Example.com</a>
```


### Email
To create a link that `opens` the `user's email client` to send an email, use the `mailto:` scheme:

```html
<a href="mailto:info@example.com">Send Email</a>
```


## Navigation 

You can `create` a navigation `menu using lists and` styling them with `CSS`:

```html
<!-- In body section. -->
<ul>
  <li><a href="home.html">Home</a></li>
  <li><a href="about.html">About Us</a></li>
  <li><a href="contact.html">Contact</a></li>
</ul>
```

These are basic concepts for creating links and navigation in HTML. You `can further enhance` and `style navigation elements using CSS` and `JavaScript` for more `dynamic behavior`.