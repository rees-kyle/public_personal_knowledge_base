---
id: e4drn2pehmmwkp0200suezk
title: 6 - Images
desc: ''
updated: 1702669058275
created: 1702667468922
---

In HTML, you can include images using `<img>` tags. The image element `does not have` a `closing tag` and is used to embed images into your web pages. Here's a basic example:

```html
<!-- In body section. -->
<img src="path/to/your/image.jpg" alt="Descriptive text about the image">
```


## Breakdown

### src
This `attribute` `specifies` the `path to the image file`. It can be a `relative path` from your HTML file `or` an `absolute URL`. Replace "path/to/your/image.jpg" with the actual path or URL of your image.

### alt
This `attribute` provides `alternative text for the image`. It is displayed **if** the `image cannot be loaded` **or by** `screen readers` **for** `accessibility`. **Always include** `descriptive` **and** `meaningful` `alt text`.

Additionally, you can use **other** `attributes` like `width` and `height` to **specify** the `dimensions` **of** the `image` **in** `pixels`.

```html
<img src="path/to/your/image.jpg" alt="Descriptive text" width="300" height="200">
```

Keep in mind that it's generally `good practice` **to use** `responsive images` **and provide** `multiple sizes` **for** `different screen resolutions` using the `srcset` **attribute**, especially **for** `larger projects` **or** `websites` **with** `diverse user devices`. This example provides `different image files` **for** `different screen widths`.

```html
<img
  srcset="path/to/your/image-320w.jpg 320w,
          path/to/your/image-480w.jpg 480w,
          path/to/your/image-800w.jpg 800w"
  sizes="(max-width: 320px) 280px,
         (max-width: 480px) 440px,
         800px"
  src="path/to/your/image-800w.jpg"
  alt="Descriptive text">
```

the `src` **attribute** is `still relevant` even **when** you are **using** the `srcset` **attribute**. The src attribute **provides a** `fallback` **for** `browsers` **that** `do not support` the `srcset` attribute **or in case** `none` **of the** `conditions` in the sizes attribute `are met`. It **acts as a** `default source` **for** the `image`.