---
id: 495j1e31zg5gxdmtp0gsipt
title: 001 - Introduction
desc: ''
updated: 1711793495281
created: 1705936155682
---

CSS, or `Cascading Style Sheets`, **is a** `styling language` **used for** `describing` **the** `presentation` **of a** `document` written **in** `HTML` (Hypertext Markup Language). HTML provides the structure and content of a web page, while CSS **is** `responsible` **for the** `layout`, `appearance`, **and** `design`. It **allows developers to** `separate` the `structure` of a document `from` its visual `presentation`, making it `easier` **to** `manage` **and** `maintain` **websites**.

Here's a brief introduction to key concepts in CSS:

1. **Selectors:**
   - Selectors **are** `patterns` **that** `match` `elements` in an **HTML** document. They are used to `apply styles` **to** `specific elements`.
   - **Examples** of selectors include `element` **selectors** (e.g., `p` for paragraphs), `class` **selectors** (e.g., `.myClass`), **and** `ID` **selectors** (e.g., `#myID`).

2. **Properties:**
   - Properties **define** the `style characteristics` **of an element**. `Each` **property has a** `name` **and** a `value`.
   - **Examples** of properties include `color`, `font-size`, `margin`, and `padding`.

3. **Values:**
   - Values are assigned to properties and `determine` `how` **the** `style` **is** `applied`.
   - For **example**, `color: blue;` sets the text color to blue, and `font-size: 16px;` sets the font size to 16 pixels.

4. **Selectors and Declarations:**
   - `CSS rules` `consist of` `selectors` **and** `declarations`. Selectors target specific HTML elements, and declarations define the styles applied to those elements. The `declaration block` **is** `enclosed` **in** `curly braces` `{}` and `can contain` `many` `declarations`.
   - Example:
     ```css
     p {
       color: red;
       font-size: 18px;
     }
     ```

5. **Box Model:**
   - The box model `describes` **the** `layout` **of** `elements` **on a web page**, including `content`, `padding`, `border`, **and** `margin`.
   - Understanding the box model is `crucial` **for** `controlling` `spacing` **and** `layout`.

6. **Cascade and Specificity:**
   - The term "`cascading`" **in** `CSS` **refers to** `the way` `styles` **are** `applied` **and can be** `overridden`.
   - `Specificity` **determines** `which styles` `take precedence` **when** `conflicting rules` **are** `applied` **to the same element**. `More specific styles` `have` `higher priority`.



<!-- start of 'precedence' section -->
<details>
   <summary>Definition: precedence</summary>

#
Precedence generally **refers to the** `condition` **of** `being considered` `more important` **or** `taking priority over` `something else` in a particular context.

---
</details>
<!-- end of 'precedence' section -->



7. **Responsive Design:**
   - CSS is essential for creating `responsive designs` **that** `adapt` **to** `different` `screen sizes` **and** `devices`.
   - `Media queries` are **used to** `apply styles` `based on` `characteristics` **like** `screen width`.

8. **External, Internal, and Inline Styles:**
   - `CSS` **can be** `applied` `externally` (in a separate stylesheet file), `internally` (within the HTML file using `<style>` tags), **or** `inline` (directly within HTML tags using the `style` attribute).

**Example** of **inline** style:
```html
<p style="color: green; font-size: 20px;">This is a styled paragraph.</p>
```

`CSS` plays a `crucial` role **in** `web development`, allowing developers to **create** `visually appealing` **and** `responsive` **websites by** `controlling` **the** `presentation` **of** `HTML content`.