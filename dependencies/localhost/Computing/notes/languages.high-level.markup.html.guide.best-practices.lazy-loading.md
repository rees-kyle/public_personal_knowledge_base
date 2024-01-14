---
id: q47h2or0emoi0k9h7q2zib8
title: 2 - Lazy Loading
desc: ''
updated: 1705252234050
created: 1705251838276
---

Lazy loading is a technique used to defer the loading of images until they are needed. This can improve the initial loading time of a web page, particularly for pages with a large number of images. Lazy loading ensures that only the images that are currently in the user's viewport (visible on the screen) are loaded, reducing the initial page load time and saving bandwidth.

Here's how you can implement lazy loading for images:

### Standard Image Tag:

```html
<!-- Without Lazy Loading -->
<img src="image.jpg" alt="Description">

<!-- With Lazy Loading -->
<img src="placeholder.jpg" data-src="image.jpg" alt="Description" loading="lazy">
```

### Explanation:

1. **`data-src` Attribute:**
   Instead of using the traditional `src` attribute to specify the image source, use `data-src` to store the actual source URL. This is because browsers will ignore images with the `loading="lazy"` attribute if the `src` attribute is present.

2. **`loading` Attribute:**
   The `loading="lazy"` attribute is what triggers the lazy loading behavior. Browsers that support lazy loading will load the image only when it comes into the user's viewport.

3. **Placeholder Image:**
   You can use a small, low-resolution placeholder image as the initial source. This placeholder image will load quickly and be replaced by the actual image when it enters the viewport.

### JavaScript-based Lazy Loading:

While the `loading="lazy"` attribute is widely supported, it's not supported in older browsers. For broader compatibility, especially with older versions of browsers, you can use JavaScript-based lazy loading.

```html
<!-- Image with a specific class -->
<img class="lazy" data-src="image.jpg" alt="Description">

<!-- JavaScript to implement lazy loading -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    var lazyImages = [].slice.call(document.querySelectorAll(".lazy"));

    if ("IntersectionObserver" in window) {
      var lazyObserver = new IntersectionObserver(function(entries, observer) {
        entries.forEach(function(entry) {
          if (entry.isIntersecting) {
            var lazyImage = entry.target;
            lazyImage.src = lazyImage.dataset.src;
            lazyImage.classList.remove("lazy");
            lazyObserver.unobserve(lazyImage);
          }
        });
      });

      lazyImages.forEach(function(lazyImage) {
        lazyObserver.observe(lazyImage);
      });
    } else {
      // Fallback for browsers that do not support IntersectionObserver
      // Load all images immediately
      lazyImages.forEach(function(lazyImage) {
        lazyImage.src = lazyImage.dataset.src;
        lazyImage.classList.remove("lazy");
      });
    }
  });
</script>
```

### Explanation:

- The JavaScript code uses the `IntersectionObserver` API to check when the images come into the viewport.
- If `IntersectionObserver` is supported, it updates the `src` attribute of the image to trigger the loading.
- If `IntersectionObserver` is not supported, it falls back to loading all images immediately.

Keep in mind that the `IntersectionObserver` approach is more efficient and performs better, but the JavaScript-based fallback ensures compatibility with older browsers. Choose the approach that best fits your project's requirements and target audience.