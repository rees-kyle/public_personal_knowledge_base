---
id: 69utj9c3xlz19id9z3m7hwz
title: 2 - Components and Props
desc: ''
updated: 1727213797938
created: 1727210992807
---

### React Basics: Components and Props

#### 1. **Components in React:**
   - **Definition**: Components are `the building blocks` **of any React application**. **They allow you** `to split` `the UI` `into independent`, `reusable pieces`, `making` **the** `code` `easier` `to manage and reason about`.



<!-- start of 'reason about' section-->
<details>
    <summary>Definition: reason about</summary>

#
"Reason about" **means** `to think` `carefully and logically` `in order` `to understand or solve` `something`. **In programming**, it **refers to** `the process of` `understanding how` `a piece of code` `works` `and how` `its different parts` `interact`.

---
</details>
<!-- end of 'reason about' section -->



   - **Types of Components**:
     - **Function Components**: The **most common type** in modern React, where a `function` `returns JSX` (the HTML-like syntax).
     - **Class Components**: **Older method**, `using ES6 classes` `that extend from` `React.Component`.
   - **Example of a Functional Component**:
     ```jsx
     function Welcome() {
       return <h1>Hello, React!</h1>;
     }
     ```

#### 2. **JSX (JavaScript XML)**:
   - `React components` `return` `JSX`, **which looks like HTML but allows you** `to write` `components` `in JavaScript`.
   - Example of JSX in a component:
     ```jsx
     const Greeting = () => {
       return <h1>Welcome to my React App!</h1>;
     };
     ```

#### 3. **Props (Properties)**:
   - **Definition**: Props are `the way` `components` `communicate` `with each other`. They **are** `inputs` `to components` `that are passed` `as attributes` **in JSX**.



<!-- start of 'attributes' section -->
<details>
    <summary>Definition: attributes</summary>

#
In HTML and React, attributes **are** `additional information` `added` `to elements` (**like** `class`, `id`, `src`, **etc**.) `that define` `properties or behaviors` **of that element**. **In React**, **they are also used to pass props to components**.

---
</details>
<!-- end of 'attributes' section-->



   - **Passing Props**: You can `pass data` `to components` `using props`.
     ```jsx
     function Welcome(props) {
       return <h1>Hello, {props.name}!</h1>;
     }
     ```
     **Here**, `name` **is a** `prop` `being passed to` **the** `Welcome` `component`.

   - **Rendering a Component with Props**:
     ```jsx
     function App() {
       return (
         <div>
           <Welcome name="Kyle" />
           <Welcome name="Rees" />
         </div>
       );
     }
     ```
     **In this example**, **the** `Welcome` `component` **is** `rendered twice` `with different props`.

#### Key Points:
   - **Components** are `like JavaScript functions`. **They** `accept inputs` (**called** "`props`") `and return` `React elements` `that describe` `what should appear` `on the screen`.
   - **Props** are `read-only`. **A** `component` `must never` `modify` **its** `own` `props`.
   - **JSX** allows `React components` **to be** `written in` `a syntax` **that looks** `like HTML`, `but` **it's** `compiled into` `JavaScript`.



<!-- start of 'compiled' section -->
<details>
    <summary>Definition: compiled (in programming)</summary>

#
In programming, "compiled" **means** `converting code` `written in a high-level language` (**like** `JavaScript` **or** `C++`) `into` `a lower-level language` (**like** `machine code` **or** `bytecode`) `so that it can be executed` `by the computer`. **For example**, **JSX** (used in React) **is compiled into regular JavaScript** **before it runs in the browser**.

---
</details>
<!-- end of 'compiled' section -->



**This is how React handles components and props at a basic level**.