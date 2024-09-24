---
id: vh0s5vj95k5pw7o4lopr49w
title: 1 - JSX Syntax
desc: ''
updated: 1727151598886
created: 1727149157434
---

### React Basics: JSX Syntax

JSX (`JavaScript XML`) **is a** `syntax extension` `for JavaScript` **that looks similar to HTML and** `allows` `React components` `to render` `what they should look like`. JSX makes it `easier` `to write and visualize` `the structure of` `the user interface` **within React components**.



<!-- start of 'render' section -->
<details>
    <summary>Definition: render (in web development)</summary>

#
In web development, render **refers to** `the process of` `displaying content` `on a webpage`. It **involves** `taking the underlying code` (like HTML, CSS, and JavaScript) `and converting it into` `a visual form` `that users` `can interact with`. **For example**, **when you load a webpage**, **the browser renders the HTML code to show text**, **images**, **and other elements**. 

**In frameworks like React**, **rendering is the process of updating the user interface based on changes in data or state**.

---
</details>
<!-- end of 'render' section -->



Here’s a quick **overview** of JSX:

1. **JSX Elements:**
   JSX **allows you to** `write` `HTML-like code` **directly** `in JavaScript files`. It’s **not mandatory**, **but** it’s a **very popular** way to write React code.

   ```jsx
   const element = <h1>Hello, world!</h1>;
   ```

2. **Embedding Expressions:**
   You can embed any valid JavaScript expression `inside` `curly braces` `{}` in JSX. **For example**, `variables` **or** `function calls` can be included within JSX.

   ```jsx
   const name = "Kyle";
   const element = <h1>Hello, {name}!</h1>;
   ```

3. **JSX Must Have One Parent Element:**
   JSX expressions `must` `be wrapped in` `a single` `parent element`. You **can use** `a div`, `section`, **or** `React.Fragment` (**or** `empty tags` **<>**) **as a wrapper**.

   ```jsx
   return (
     <div>
       <h1>Hello, World!</h1>
       <p>This is a React component.</p>
     </div>
   );
   ```

4. **Attributes in JSX:**
   JSX uses `camelCase` `for attribute names` (**e.g.**, `className` **instead of class**, `onClick` **instead of onclick**).

   ```jsx
   const element = <button className="btn" onClick={handleClick}>Click Me!</button>;
   ```

5. **Self-Closing Tags:**
   `If` `an HTML element` `doesn’t have` `children`, you can use a self-closing tag '` />`'.

   ```jsx
   const element = <img src="image.jpg" alt="An image" />;
   ```

6. **JavaScript Logic in JSX:**
   JSX can contain JavaScript logic, **such as** `conditionals` **or** `loops`.

   ```jsx
   const isLoggedIn = true;
   const element = <h1>{isLoggedIn ? 'Welcome back!' : 'Please sign up.'}</h1>;
   ```



<!-- start of 'conditionals' section -->
<details>
    <summary>Definition: conditionals</summary>

#
Conditionals **are** `statements` `in programming` `that allow` `the code` `to make decisions` `based on` `certain conditions`. They typically use **keywords like** `if`, `else if`, **and** `else` `to execute` `different blocks of code` `depending on` `whether a condition is` `true or false`.

---
</details>
<!-- end of 'conditionals' section -->



7. **Styling in JSX:**
   `Inline styles` **in JSX are** `written as` `an object` `with camelCase` **property names**.

   ```jsx
   const divStyle = { color: 'blue', backgroundColor: 'lightgray' };
   const element = <div style={divStyle}>Styled Text</div>;
   ```