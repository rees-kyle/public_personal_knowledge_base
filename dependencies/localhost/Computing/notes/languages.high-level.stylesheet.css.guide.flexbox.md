---
id: wzgeoxj3u6f78316mkyvksn
title: 7 - Flexbox
desc: ''
updated: 1707165142691
created: 1707164593196
---

1. **Display Property:**
   - **To enable** `Flexbox` **on a** `container`, `set` **its** `display` **property to** `flex` **or** `inline-flex`. For example:

     ```css
     .flex-container {
       display: flex;
     }
     ```


2. **Flex Direction:**
   - `Controls` the `direction` **of** the `main axis`. `Options` **include** `row`, `column`, `row-reverse`, **and** `column-reverse`.

     ```css
     .flex-container {
       flex-direction: row;
     }
     ```


3. **Justify Content:**
   - `Aligns items` **along** the `main axis`. `Options` **include** `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, **and** `space-evenly`.

     ```css
     .flex-container {
       justify-content: center;
     }
     ```


4. **Align Items:**
   - `Aligns items` **along** the `cross axis`. `Options` **include** `flex-start`, `flex-end`, `center`, `baseline`, **and** `stretch`.

     ```css
     .flex-container {
       align-items: center;
     }
     ```


5. **Align Self:**
   - `Overrides` the `align-items` **for** `individual items` **in** the `container`.
     ```css
     .flex-item {
       align-self: flex-end; /* or flex-start, center, baseline, stretch */
     }
     ```

6. **Flex Property:**
   - `Combines` `flex-grow`, `flex-shrink`, **and** `flex-basis` **in** `one` `property`. 
     ```css
     .flex-item {
       flex: 1 0 auto; /* flex-grow flex-shrink flex-basis */
     }
     ```

**These** `properties` **give you the power to** `sculpt` **your** `layout` like a digital Michelangelo.