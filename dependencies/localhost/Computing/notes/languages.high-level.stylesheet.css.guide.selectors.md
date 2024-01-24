---
id: z44qlu7e1gbm4g241ry132x
title: Selectors
desc: ''
updated: 1706121096850
created: 1706121093116
---

In CSS (Cascading Style Sheets), selectors are patterns that are used to select and style HTML elements. Selectors target specific elements on a web page, allowing you to apply styles to them. Here are some common types of CSS selectors:

1. **Universal Selector (*):**
   - Selects all elements on a page.
   ```css
   * {
       /* styles */
   }
   ```

2. **Type Selector (Element Selector):**
   - Selects all instances of a specified HTML element.
   ```css
   p {
       /* styles */
   }
   ```

3. **Class Selector (.class):**
   - Selects all elements with a specific class attribute.
   ```css
   .my-class {
       /* styles */
   }
   ```

4. **ID Selector (#id):**
   - Selects a single element with a specific id attribute.
   ```css
   #my-id {
       /* styles */
   }
   ```

5. **Attribute Selector ([attribute=value]):**
   - Selects elements with a specific attribute and value.
   ```css
   input[type="text"] {
       /* styles */
   }
   ```

6. **Descendant Selector (ancestor descendant):**
   - Selects all descendants of a specified ancestor.
   ```css
   div p {
       /* styles */
   }
   ```

7. **Child Selector (parent > child):**
   - Selects all direct children of a specified parent.
   ```css
   ul > li {
       /* styles */
   }
   ```

8. **Adjacent Sibling Selector (prev + next):**
   - Selects an element that is immediately preceded by a specified element.
   ```css
   h2 + p {
       /* styles */
   }
   ```

9. **General Sibling Selector (prev ~ siblings):**
   - Selects all elements that are siblings of a specified element.
   ```css
   h2 ~ p {
       /* styles */
   }
   ```

10. **Pseudo-classes (:pseudo-class):**
    - Selects elements based on their state or position.
    ```css
    a:hover {
        /* styles for hover state */
    }
    ```

11. **Pseudo-elements (::pseudo-element):**
    - Selects parts of an element, such as the first line or first letter.
    ```css
    p::first-line {
        /* styles for the first line of a paragraph */
    }
    ```

These are some of the most commonly used selectors in CSS. By combining and using these selectors, you can target specific elements on a web page and apply styles to create the desired layout and appearance.