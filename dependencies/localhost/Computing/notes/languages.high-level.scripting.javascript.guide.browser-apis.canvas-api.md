---
id: 09rnp4qz3o024gezrrmuka1
title: 4 - Canvas API
desc: ''
updated: 1714792616372
created: 1714749838842
---

The Canvas API is a powerful tool in web development that **allows for** `dynamic`, `scriptable` `rendering of` `2D shapes` **and** `bitmap images`. It is **part of the HTML5 specification** and is designed `for drawing graphics` **via JavaScript**. Here, I'll provide an introduction to the basic usage of the Canvas API, discussing how to set it up in your HTML document, `draw` **simple** `shapes`, `apply` `styles` **and** `colors`, and handle more complex operations like `transformations` **and** `animations`.



<!-- start of 'canvas' section -->
<details>
    <summary>Definition: canvas</summary>

#
A canvas **is a durable** `fabric` **used as a** `surface for` `painting`. It's commonly `made of` `linen or` `cotton`, **tightly stretched over a** `wooden frame`.

---
</details>
<!-- end of 'canvas' section -->



<!-- start 'canvas (digital)' section -->
<details>
    <summary>Definition: canvas (digital)</summary>

#
In digital contexts, a canvas **refers to the** `area` `designated for` `drawing` **or** `rendering` `graphics` `within` **computer** `applications`.

---
</details>
<!-- end of 'canvas (digital)' section -->



<!-- start of 'rendering' section -->
<details>
    <summary>Definition: rendering</summary>

#
Rendering is the **process of** `generating` **a** `visual image` `from` **a** `model by` **means of computer** `software`. This **involves** `translating information` `from` **a** `scene file` `containing objects` `in` a strictly **defined** `language or` `data structure` `into` **a displayable** `image`. Rendering can be used in various fields such as `video games`, `simulators`, `movie` **or** `TV` `visual effects`, **and** `design visualization`.

---
</details>
<!-- end of 'rendering' section-->



## Setting Up the Canvas Element

To start using the Canvas API, you `first` need to `add` a `<canvas> element to` your `HTML`:

```html
<!-- Canvas element to draw graphics via JavaScript -->
<canvas id="myCanvas" width="480" height="320">
    <!-- Fallback message for unsupported browsers -->
    Your browser does not support the canvas element.
</canvas>
<!-- End of canvas element -->
```

The `width and height` **attributes** specify the size of the canvas. `If` these are `not set`, the **canvas will** `default to` `300 pixels wide` **and** `150 pixels high`.

## Accessing the Canvas with JavaScript

`To draw` on the canvas, you need to `access` **its** `rendering context` **through JavaScript**:

```javascript
// Get canvas element using its ID
const canvas = document.getElementById('myCanvas');

// Get the 2D rendering context for canvas; to draw 2d shapes
const ctx = canvas.getContext('2d');
```

## Drawing Shapes

You can draw various shapes using the Canvas API. Below are **examples of** how to draw some **basic shapes**.

### Drawing a Rectangle

```javascript
// Set fill color for drawing operations to blue
ctx.fillStyle = 'blue'; 

// Draw a solid rectangle (completely filled with a single, uniform color, without any patterns or gradients)
ctx.fillRect(10, 10, 150, 100); // x pos, y pos, width, height
```

### Drawing a Line

```javascript
ctx.beginPath(); // Start a new path
ctx.moveTo(50, 50); // Move pen to (x pos, y pos)
ctx.lineTo(200, 50); // Draw a line to (x pos, y pos)
ctx.strokeStyle = 'red'; // Set stroke (outline) color to 'red'
ctx.stroke(); // Render path
```

### Drawing a Circle

```javascript
ctx.beginPath(); // Begin new path or reset current path

// Draw a circle using the arc method
ctx.arc(95, 50, 40, 0, 2 * Math.PI);
// x pos, y pos, radius, start angle, end angle (in radians)

ctx.fillStyle = 'green'; // Set fill color for shape to 'green'
ctx.fill(); // Fill path with current fill style
```



<!-- start of 'radian' section -->
<details>
    <summary>Definition: radian</summary>

#
A radian **is a** `unit of` `measurement` `for angles`. **One radian is the angle made at the center of a circle by an arc whose length is equal to the radius of the circle**.

[YouTube: What are Radians?](https://www.youtube.com/watch?v=cgPYLJ-s5II)

---
</details>
<!-- end of 'radian' section -->



## Applying Styles and Colors

You can style your drawings using `'fillStyle' for` **the** `color inside` shapes and `'strokeStyle' for` the `color of` **the** `lines`. You can also set `'lineWidth'`, `'lineCap'`, **and** `'lineJoin'` **properties** `to style` `lines`.

```javascript
ctx.lineWidth = 8; // Set width of lines
ctx.strokeStyle = '#ff0000'; // Red line

// Choose style for the ending of lines
ctx.lineCap = 'round'; // Set ending of lines; to be 'round'
// Apply the stroke to the current path with the previously set styles
ctx.stroke(); // Apply stroke to current path with previously set styles
```

## Transformations

The Canvas API also allows you to perform transformations **such as** `translate`, `rotate`, **and** `scale`:

```javascript
ctx.translate(50, 50); // Move canvas origin to (x pos, y pos)

// Rotate canvas around current origin; now at '(50, 50)'
ctx.rotate(Math.PI / 4); // rotation specified in radians; Math.PI / 4 radians equals 45 degrees

// Scale all subsequent drawings (horizontal, vertical)
ctx.scale(2, 2); // Scale everything by 2 times (x2)
```

## Animations

To animate objects on the canvas, you can use `window.requestAnimationFrame()`:

```javascript
// Animation frame function

function drawFrame() { // Handles animation logic
    ctx.clearRect(0, 0, canvas.width, canvas.height); // Clear canvas
    update(); // Update position (of a shape for example)
    draw(); // Redraw (the shape for example) at new position
    requestAnimationFrame(drawFrame); // Request next frame
}

// Start animation
drawFrame();
```

## Conclusion

The `Canvas API` **offers extensive** `capabilities for` `2D graphics` **and can be used** `to create games`, `animations`, **and** `other` `graphical applications` **directly** `in` **the** `browser`. Experiment with different API methods to see what you can create!