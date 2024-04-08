---
id: 2gckowyfyr132g6iel0s2kd
title: 1 - Variables
desc: ''
updated: 1712611440432
created: 1712606566529
---

Variables **are** `used` **to** `store` `data values`. **In JavaScript**, **variables can be** `declared using` `three` `different keywords`: `var`, `let`, and `const`. Here's a breakdown of each:

1. **`var`:**
   - Declares a variable that **can be** `reassigned` **and** `re-declared` `within` **its** `scope`.
   - Variables declared with var **are** `function-scoped` **or** `globally-scoped`, **but** `not` `block-scoped`.

     ```javascript
     var name = "John";
     var age = 30;

     function greet() {
         var message = "Hello, " + name;
         console.log(message);
     }
     ```

2. **`let`:**
   - Declares a variable that **can be** `reassigned` `within` **its** `scope`.
   - Variables declared with let **are** `block-scoped`, **which means they're** `limited to` **the** `block`, `statement`, **or** `expression` **where they're defined**.

     ```javascript
     let name = "John";
     let age = 30;

     if (age >= 18) {
         let status = "adult";
         console.log(name + " is an " + status);
     }
     ```

3. **`const`:**
   - Declares a `constant` **variable whose** `value` `cannot be` `reassigned` `once` **it's** `set`.
   - Variables declared with const **are** `block-scoped`.

     ```javascript
     const PI = 3.14;
     const student = {
         name: "Alice",
         age: 20
     };

     // You can't reassign a constant variable
     // PI = 3.14159; This will throw an error because constants cannot be reassigned.

     // However, you can mutate the properties of a constant object using dot notation.
     student.age = 21;
     ```

**Tips:**
- **Use** `const` **by** `default` **for** `variables` **that** `won't be` `reassigned`.
- **Use** `let` **when you need to** `reassign variables`.
- `Avoid` **using** `var` **unless you have specific reasons** to use it, as `let` **and** `const` **provide** `better scoping` **and** `avoid` **some common** `pitfalls` **associated with var**.

Understanding these different types of variable declarations **will help you** `write` `cleaner` **and** `more maintainable` **JavaScript** `code`. Practice using each type of variable declaration to become comfortable with their usage.