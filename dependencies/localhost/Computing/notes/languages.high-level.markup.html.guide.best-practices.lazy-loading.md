---
id: q47h2or0emoi0k9h7q2zib8
title: 2 - Lazy Loading
desc: ''
updated: 1713808643929
created: 1705251838276
---

Lazy loading is **a** `technique` **used to** `defer` **the** `loading` **of** `images` `until` **they are** `needed`. This **can** `improve` the `initial` `loading time` **of a** `web page`, particularly for pages with a large number of images. Lazy loading **ensures** that `only` the `images` **that are** `currently` **in the** `user's viewport` (`visible on` **the** `screen`) **are** `loaded`, reducing the initial page load time and `saving` `bandwidth`.



<!-- start of 'defer' section -->
<details>
  <summary>Definition: defer</summary>

#
To defer **means to** `delay` **or**  `postpone` **an** `action` **or** `event` **to a** `later time`.

---
</details>
<!-- end of 'defer' section -->



#
Here's how you can implement lazy loading for images:

## Standard Image Tag

```html
<!-- Without Lazy Loading -->
<img src="image.jpg" alt="Description">

<!-- With Lazy Loading -->
<img src="placeholder.jpg" data-src="image.jpg" alt="Description" loading="lazy">
```

### Explanation:

1. **`data-src` Attribute:**
   `Do not` `use` the **traditional** `src` **attribute** to specify the image source, `use` `data-src` to store the actual source URL. This is `because` `browsers` will `ignore lazy loading images` **if** the `src` attribute **is** `present`.

2. **`loading` Attribute:**
   The `loading="lazy"` attribute is what `triggers` the `lazy loading` behavior. Browsers that support lazy loading will load the image only when it comes into the user's viewport.

3. **Placeholder Image:**
   You can `use` **a** `small`, `low-resolution` `placeholder image` **as** the `initial source`. This placeholder image **will** `load quickly` **and be** `replaced by` the `actual image` **when it** `enters` the `viewport`.

## JavaScript-based Lazy Loading

While the `loading="lazy"` attribute is widely supported, it's `not supported` **in** `older browsers`. For broader compatibility, especially with older versions of browsers, you **can** `use` `JavaScript-based` `lazy loading`.

```html
<!-- Image with a specific class -->
<img class="lazy" data-src="image.jpg" alt="Description">

<!-- JavaScript to implement lazy loading -->
<script>
  // Add an event listener to run the code after the entire DOM has been fully loaded
  document.addEventListener("DOMContentLoaded", function() {
    // Select all elements with the 'lazy' class and convert NodeList to an Array
    var lazyImages = [].slice.call(document.querySelectorAll(".lazy"));

    // Check if browser supports IntersectionObserver
    if ("IntersectionObserver" in window) {
      // Create a new IntersectionObserver instance
      var lazyObserver = new IntersectionObserver(function(entries, observer) {
        // Iterate over each entry (each observed element)
        entries.forEach(function(entry) {
          // Check if the element is intersecting with the viewport
          if (entry.isIntersecting) {
            // Get the element that is intersecting
            var lazyImage = entry.target;
            // Set the 'src' attribute to 'data-src' to start loading the image
            lazyImage.src = lazyImage.dataset.src;
            // Remove the 'lazy' class since the image is now loading/loaded
            lazyImage.classList.remove("lazy");
            // Stop observing the image as it is no longer needed to be tracked
            lazyObserver.unobserve(lazyImage);
          }
        });
      });

      // Iterate over each lazy-loaded image in the array
      lazyImages.forEach(function(lazyImage) {
        // Call the 'observe' method of the IntersectionObserver instance
        lazyObserver.observe(lazyImage); // This method starts watching the specified element (lazyImage) for entering or leaving the viewport
      });

      // Fallback for browsers that do not support IntersectionObserver
    } else {
      // Iterate over each image marked with the 'lazy' class
      lazyImages.forEach(function(lazyImage) {
        // Set the 'src' attribute of each lazy image to the URL stored in 'data-src'
        lazyImage.src = lazyImage.dataset.src; // This causes the image to load immediately without waiting for it to enter the viewport
        // Remove the 'lazy' class from the image, indicating that it no longer needs lazy loading
        lazyImage.classList.remove("lazy");
      });
    }
  });
</script>
```

### Explanation:

- The JavaScript code uses the `IntersectionObserver` `API` **to** `check` **when** the `images` **come into** the `viewport`.
- **If** `IntersectionObserver` is `supported`, it `updates` the `src` attribute of the image **to** `trigger` the `loading`.
- **If** `IntersectionObserver` is `not supported`, it **falls back to** `loading all images` `immediately`.

Keep in mind that the `IntersectionObserver` **approach** is `more efficient` **and** `performs better`, **and** the **JavaScript-based** `fallback` **ensures** `compatibility` **with** `older browsers`. `Choose` the `approach` **that** `best fits` **your** `project's requirements` **and** `target audience`.