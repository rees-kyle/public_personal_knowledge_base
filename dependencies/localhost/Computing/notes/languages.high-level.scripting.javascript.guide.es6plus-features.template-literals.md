---
id: ps5ltkky7wd03pi41eq6g4o
title: 1 - Template Literals
desc: ''
updated: 1713842846386
created: 1713834004531
---

One of the standout features of ES6 is template literals. Let's dive deeper into what template literals are and how they enhance JavaScript coding.



<!-- start of 'literals' section -->
<details>
    <summary>Definition: literals</summary>

#
In a general context, "literals" **refers to** `things` **that are** `taken` **or** `understood` `exactly as` **they are** `presented`, `without` **any** `change` **or** `interpretation`. For **example**, **taking someone's words literally means you understand them exactly as they said**, **without assuming they meant something different**.

---
</details>
<!-- end of 'literals' section -->



Template literals **are a** `new` **kind of** `string literals` **that provide an** `easy syntax` **to** `embed expressions` **within string literals**. They are `enclosed` **by** `backticks`  **instead of the traditional single or double quotes**. Template literals offer `more functionality` **than traditional strings**, **including** `multiline strings` **and** `string interpolation`. Here's a closer look at these features:



<!-- start of 'embed' section -->
<details>
    <summary>Definition: embed</summary>

#
The term "embed" **means to** `insert` `something` **deeply** `into` `something else` **so that it** `becomes` **an** `integral part` **of it**. For **example**, **embedding a video into a website**, **placing a journalist within a military unit to report first-hand**, or **embedding a stone into a piece of jewelry**.

---
</details>
<!-- end of 'embed' section -->



<!-- start of 'expression' section -->
<details>
    <summary>Definition: expression (in mathematics and programming)</summary>

#
An expression in these fields **refers to a** `combination of` `symbols` **and** `operators` **that** `represent` **a** `particular value` **or** `concept`. For **example**, **in mathematics**, **2 + 2 is an arithmetic expression**, and **in programming**, **variables and functions can be part of expressions that perform calculations or operations**.

---
</details>
<!-- end of 'expression' section -->



<!-- start of 'interpolation' section -->
<details>
    <summary>Definition: interpolation (in programming)</summary>

#
Interpolation **is a** `technique` **in programming that allows you to** `insert values` `from variables` **or** `expressions` **directly** `into` **a** `string`. **This makes creating strings** `with dynamic content` `simpler` **and** `more readable`.

---
</details>
<!-- end of 'interpolation' section -->



```javascript
// Declare a variable 'name' and initialize it with the string value "Alice"
let name = "Alice";

// Declare a variable 'greeting'. Initialize it using a template literal denoted by backticks
let greeting = `Hello, ${name}!`; 
// Inside the template literal, `${name}` is an expression placeholder that gets replaced by the value of the variable 'name'. This process is called string interpolation

console.log(greeting); // The result of the interpolation will be 'Hello, Alice!'
```

## Multiline Strings

**Before ES6**, **creating multiline strings could be cumbersome**, **often requiring the use of** `newline` **characters** '`\n`' **or concatenation**. With template literals, you can simply `create` **them by including** `line breaks` `within` **the** `backticks`.



<!-- start of 'newline characters and concatenation' section -->
<details>
    <summary>Example: multiline strings with newline characters and concatenation</summary>

#
```javascript
// newline characters

let poem = "Roses are red,\nViolets are blue,\nSugar is sweet,\nAnd so are you.";

console.log(poem);
// Output:
// Roses are red,
// Violets are blue,
// Sugar is sweet,
// And so are you.

// -----------------------------------------------------------------------------

// concatenation and newline characters

let greeting = "Hello there,\n" +
               "Welcome to our website.\n" +
               "We hope you enjoy your stay!";

console.log(greeting);
// Output:
// Hello there,
// Welcome to our website.
// We hope you enjoy your stay!
```

---
</details>
<!-- end of 'newline characters and concatenation' section -->



```javascript
// multiline strings with template literals

let address = `123 Main St.
New York, NY 10001`;
console.log(address);
// Output:
// 123 Main St.
// New York, NY 10001
```

## Expression Interpolation

One of the most powerful features of template literals is the ability to embed expressions. `Any` `valid` **JavaScript** `expression`, **including** `function calls` **and** `arithmetic`, `can be` `embedded` **by wrapping it** `with` `${}` `within` **the** `template literal`.

```javascript
let a = 10;
let b = 20;
let sum = `The sum of ${a} and ${b} is ${a + b}.`;
console.log(sum);  // Output: The sum of 10 and 20 is 30.
```

## Tagged Template Literals

**Template literals can also be used with a function**, **called a** `tag function`, **which allows you to** `parse` **and** `modify` **the** `output` **of the template literal** `before` **it's** `output as` **a** `final string`. This can be used for more **sophisticated manipulations like** `sanitization`, `localization`, **and** `more complex` `text transformations`.



<!-- start of 'sophisticated' section -->
<details>
    <summary>Definition: sophisticated</summary>

#
The term "sophisticated" **refers to** `something` **or** `someone` **that is** `very developed`, `advanced`, **or** `refined`. It can describe **complex technologies** or **ideas**, **people who are cultured and have good taste**, **or styles and fashions that are elegant and polished**.

---
</details>
<!-- end of 'sophisticated' section -->



<!-- start of 'refined' section -->
<details>
    <summary>Definition: refined</summary>

#
The word "refined" **means** `something` **that has been** `made` `better` **or** `cleaner`. **Things like art that are done with great care and detail**.

---
</details>
<!-- end of 'refined' section -->



```javascript
// Define a tag function named 'highlight'
function highlight(strings, ...values) {
// It takes the template strings as the first argument and captures all interpolated expressions as subsequent arguments

    // The 'reduce' method is used to process and concatenate elements of the 'strings' array and the 'values'
    return strings.reduce((result, string, i) => {
    // 'result' is the accumulator, 'string' is the current value from the strings array, and 'i' is the current index

        // Each string from the 'strings' array is concatenated with the corresponding value from the 'values' array
        return `${result}${string}${values[i] ? `<strong>${values[i]}</strong>` : ''}`;
        // If a value exists (i.e., it is not undefined), it is wrapped with <strong> tags to emphasize it
        // If no value exists (which can happen if the final string segment follows the last expression), nothing is added
    }, '');
}

let name = "Alice";
let age = 25;
// Use the 'highlight' tag function with a template literal to create formatted text
let text = highlight`My name is ${name} and I am ${age} years old.`;
// This will insert the values of 'name' and 'age' into the template and apply HTML strong tags to them

// The formatted string, now containing HTML tags, is stored in 'text'
console.log(text); 
// Output: My name is <strong>Alice</strong> and I am <strong>25</strong> years old.
```

## Conclusion

Template literals are **a significant improvement over previous string creation methods in JavaScript**, **providing** `more flexibility` **and** `functionality` for developers. They make it `easier to` `handle multiline strings`, `embed expressions`, **and** `extend functionality through` `tagged templates`, all of which are essential for modern JavaScript development.



<!-- start of 'essential' section -->
<details>
    <summary>Definition: essential</summary>

#
The word "essential" **means** `something` **that is** `very important` **or** `necessary`.

---
</details>
<!-- end of 'essential' section -->