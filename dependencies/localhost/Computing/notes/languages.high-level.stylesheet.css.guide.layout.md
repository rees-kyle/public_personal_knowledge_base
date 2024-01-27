---
id: zk5mi243vj048ktt6blfzpy
title: 4 - Layout
desc: ''
updated: 1706385854425
created: 1706318527040
---

In CSS (Cascading Style Sheets), layout **refers to the** `arrangement` **and** `positioning` **of** `elements` on a web page. CSS provides `several` `properties` **and** `techniques` for controlling the layout of HTML elements. Here are some commonly used CSS properties for layout:

1. **Display Property:**
   - `display`: Determines `how` an `element` **is** `rendered` **on** the `page`. Common values include:
     - `block`: **Elements are displayed** as blocks, `one below the other`.
     - `inline`: **Elements are displayed** inline, `next to each other`.
     - `flex`: Enables a flex **container for** `flexible box layout`.
     - `grid`: Enables a grid **container for** `grid layout`.

   ```css
   /* Example: */
   .container {
     display: flex;
   }
   ```

2. **Positioning:**
   - `position`: Specifies the `positioning method` of an element.
     - `static`: Default value; elements are `positioned` **according to** the `normal flow` **of** the `document`.
     - `relative`: Positioned `relative` **to** its `normal position`.
     - `absolute`: Positioned `relative` **to** the `nearest` `positioned ancestor`.
     - `fixed`: Positioned `relative` **to** the `viewport`.
     - `sticky`: A `hybrid` **of** `relative` **and** `fixed` `positioning`.

   ```css
   /* Example: */
   .header {
     position: fixed;
     top: 0;
     left: 0;
     width: 100%;
     background-color: #333;
     color: #fff;
   }
   ```

3. **Flexbox:**
   - Flexbox is a `one-dimensional` `layout method` **for laying out items in** `rows` **or** `columns`. It provides properties for the container (parent) and the items (children).
   
   ```css
   /* Example: */
   .container {
     display: flex;
     justify-content: space-between;
   }
   ```

4. **Grid:**
   - CSS Grid Layout is a `two-dimensional` layout system for the web. It allows you to create `complex grid-based layouts` with `rows` **and** `columns`.

   ```css
   /* Example: */
   .container {
     display: grid;
     grid-template-columns: repeat(3, 1fr);
     gap: 20px;
   }
   ```

5. **Box Model:**
   - The box model `describes` the `structure` **of** an `HTML element` **as a** `box`, which **consists of** `content`, `padding`, `border`, **and** `margin`.

   ```css
   /* Example: */
   .box {
     width: 200px;
     padding: 20px;
     border: 1px solid #ccc;
     margin: 10px;
   }
   ```

These are just a **few examples**, and there are `many other` **CSS** `properties` **and** `techniques` for layout depending on the specific requirements of your project. It's `often` **a** `combination` **of** these `properties` **that helps** `achieve` **the** `desired layout` for a web page.